========
Webhook
========

Usage of cDemo Webhooks
================================

1. Get Supported Topics for Webhooks
2. Register a Webhook
3. Receive Webhook Notifications

If a webhook is configured, any time a record status is changed or record is updated, cdemo webhook will send an outgoing HTTP request to a your webhook receiver URL with a payload containing relevant information about the event.:

POST HTTP/1.1
host: <your-webhook-receiver-domain>
user-agent: cDemo Webhook Client/1.0
cdemo-webhook-uuid: <uuid of the webhook>
cdemo-webhook-signature-v1: <signature of the payload>
cdemo-webhook-request-timestamp: <timestamp of the request>

.. code-block:: python
    {
        "topic": "users.User/create",
        "data": {
            "record": {
                "inspection_id": "inspection id of the record"
            }
        },
        "webhook_uuid": "5e2ee3ba-905e-4360-94bf-18ef21c0e844"
    }

The signature is generated using HMAC with SHA256 hash function. The signing key is the secret token you provided when registering the webhook. The message to be signed is the concatenation of the timestamp and the payload JSON string.

Get Supported Topics
==========

.. sourcecode:: http

  GET /webhooks/topics HTTP/1.1 

+------------+-----------------------------------------------------------+
| Production | https://api.cdemo.com/webhooks/topics?access_token=<xxx>  |
+------------+-----------------------------------------------------------+

+-----------------------+---------------+---------------------------------------+
| Parameters            | Is Mandatory  | Notes                                 |
+=======================+===============+=======================================+
| access_token          | Yes           | API Token                             |
+-----------------------+---------------+---------------------------------------+

Response
---------

.. code-block:: json

    [
        {
            "name": "RECORD_COMPLETED"
        },
        {
            "name": "RECORD_ARCHIVED"
        },
        {
            "name": "RECORD_UNARCHIVED"
        },
        {
            "name": "RECORD_STAGED"
        },
        {
            "name": "RECORD_UNSTAGED"
        },
        {
            "name": "RECORD_DELETED"
        },
        {
            "name": "RECORD_UPDATED"
        }
    ]

Register a Webhook
====================

.. sourcecode:: http

  POST /webhooks/ HTTP/1.1
  Content-Type: application/json

+------------+-----------------------------------------------------------+
| Production | https://api.cdemo.com/webhooks/?access_token=<xxx>        |
+------------+-----------------------------------------------------------+

+-----------------------+---------------+---------------------------------------+
| Parameters            | Is Mandatory  | Notes                                 |
+=======================+===============+=======================================+
| access_token          | Yes           | API Token                             |
+-----------------------+---------------+---------------------------------------+

Payload
---------

.. code-block:: python
    
  {
    "stores": [1066737, 1067698], 
    "url": "https://webhook.site/05a80092-24e3-4cba-9276-ef3dd1da7806", 
    "secrets": ["mysecrettoken1"],
    "topics": ["RECORD_COMPLETED", "RECORD_ARCHIVED", "RECORD_UNARCHIVED", "RECORD_UPDATED"]
  }

Response
---------

.. code-block:: python

  {
    "url": "https://webhook.site/05a80092-24e3-4cba-9276-ef3dd1da7806",
    "uuid": "3ce10aa1-327d-45b1-bacc-7aeda1334b3b",
    "active": true,
    "secrets": [
        "mysecrettoken1"
    ],
    "topics": [
        "RECORD_COMPLETED",
        "RECORD_ARCHIVED",
        "RECORD_UNARCHIVED",
        "RECORD_DELETED"
    ],
    "stores": [
        1066737,
        1067698
    ],
    "created": "2025-12-25T07:12:36.154262Z",
    "modified": "2025-12-25T07:12:36.154303Z"
 }


Get All Registered Webhooks
==========================  

.. sourcecode:: http

  GET /webhooks/ HTTP/1.1

+------------+-----------------------------------------------------------+
| Production | https://api.cdemo.com/webhooks/?access_token=<xxx>        |  
+------------+-----------------------------------------------------------+

+-----------------------+---------------+---------------------------------------+
| Parameters            | Is Mandatory  | Notes                                 |       
+=======================+===============+=======================================+
| access_token          | Yes           | API Token                             |
+-----------------------+---------------+---------------------------------------+

Response
---------

.. code-block:: python

  [
    {
        "url": "https://webhook.site/05a80092-24e3-4cba-9276-ef3dd1da7806",
        "uuid": "3ce10aa1-327d-45b1-bacc-7aeda1334b3b",
        "active": true,
        "secrets": [
            "mysecrettoken1"
        ],
        "topics": [
            "RECORD_COMPLETED",
            "RECORD_ARCHIVED",
            "RECORD_UNARCHIVED",
            "RECORD_DELETED"
        ],
        "stores": [
            1066737,
            1067698
        ],
        "created": "2025-12-25T07:12:36.154262Z",
        "modified": "2025-12-25T07:12:36.154303Z"
    }
  ]

Modify a Webhook
==========================  

.. sourcecode:: http
    
  PATCH /webhooks/:uuid HTTP/1.1
  Content-Type: application/json

+------------+-----------------------------------------------------------+
| Production | https://api.cdemo.com/webhooks/:uuid?access_token=<xxx>   |
+------------+-----------------------------------------------------------+

+-----------------------+---------------+---------------------------------------+
| Parameters            | Is Mandatory  | Notes                                 |       
+=======================+===============+=======================================+
| access_token          | Yes           | API Token                             |
+-----------------------+---------------+---------------------------------------+

Payload
---------

.. code-block:: python
    
  {
    "secrets": ["mysecrettoken1", "mysecrettoken2"],
    "stores": [1066737,1067698],
    "topics": ["RECORD_COMPLETED","RECORD_ARCHIVED","RECORD_UNARCHIVED"]
  }


Response
---------

.. code-block:: python
    
  {
    "url": "https://webhook.site/05a80092-24e3-4cba-9276-ef3dd1da7806",
    "uuid": "3ce10aa1-327d-45b1-bacc-7aeda1334b3b",
    "active": true,
    "secrets": [
        "mysecrettoken1",
        "mysecrettoken2"
    ],
    "topics": [
        "RECORD_COMPLETED",
        "RECORD_ARCHIVED",
        "RECORD_UNARCHIVED"
    ],
    "stores": [
        1066737,
        1067698
    ],
    "created": "2025-12-25T07:12:36Z",
    "modified": "2025-12-25T07:18:13.288375Z"
  }


Delete a Webhook
==========================

.. sourcecode:: http

  DELETE /webhooks/:uuid HTTP/1.1

+------------+-----------------------------------------------------------+
| Production | https://api.cdemo.com/webhooks/:uuid?access_token=<xxx>   |
+------------+-----------------------------------------------------------+

+-----------------------+---------------+---------------------------------------+
| Parameters            | Is Mandatory  | Notes                                 |       
+=======================+===============+=======================================+
| access_token          | Yes           | API Token                             |
+-----------------------+---------------+---------------------------------------+

Response
---------

.. sourcecode:: http

  HTTP/1.1 204 No Content


Test a Webhook
==========================

.. sourcecode:: http

  POST /webhooks/:uuid/test HTTP/1.1
  Content-Type: application/json

+------------+----------------------------------------------------------------+
| Production | https://api.cdemo.com/webhooks/:uuid/test?access_token=<xxx>   |
+------------+-------------------------------------------------------------+

+-----------------------+---------------+---------------------------------------+
| Parameters            | Is Mandatory  | Notes                                 |       
+=======================+===============+=======================================+
| access_token          | Yes           | API Token                             |
+-----------------------+---------------+---------------------------------------+

Payload
---------

.. code-block:: python
    
  {"foo": "bar"}


Response
---------

.. code-block:: python

  {
    "status": "Test webhook sent."
  }

Your webhook receiver should receive a POST request with the following payload:

.. code-block:: python
    
  {
    "data": {"foo": "bar"}, 
    "topic": "RECORD_UNARCHIVED", 
    "webhook_uuid": "a125048b-7f27-4ab3-9fdb-973378be6ed5"
 }
