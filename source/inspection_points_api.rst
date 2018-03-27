
=================
Inspection Points
=================

Get inspection points of a record.

.. sourcecode:: http

  GET /records/:inspection_id/inspection_points HTTP/1.1

+------------+--------------------------------------------------------------------------------------+
| Production | https://api.cdemo.com/v3/records/:inspection_id/inspection_points?access_token=<xxx> |
+------------+--------------------------------------------------------------------------------------+

Parameters
==========

+-----------------------+---------------+---------------------------------------+
| Parameters            | Is Mandatory  | Notes                                 |
+=======================+===============+=======================================+
| access_token          | Yes           | API Token                             |
+-----------------------+---------------+---------------------------------------+
| exclude_fields        | No            | fields do not want to return.         |
|                       |               | separate by ','.                      |
|                       |               | like store,category                   |
+-----------------------+---------------+---------------------------------------+
| fields                | No            | fields want to return.                |
|                       |               | separate by ','.                      |
|                       |               | like store,category                   |
+-----------------------+---------------+---------------------------------------+

Response
========

.. code-block:: python

  [
    {
        "stage_text": "Left Front Door",
        "question_text": "Select the type of upholstery material? (SINGLE CHOICE QUESTION)",
        "question_text_short": "Upholstery Material",
        "answer": "Cloth Upholstery",
        "answer_parent": "",
        "photo_url": null,
        "photo_point_flag": 0,
        "damage_flag": false,
        "option_flag": true,
        "stock_photo_flag": 0,
        "severity_descriptor": "",
        "wear_tear_flag": 0,
        "chargeable_flag": 0,
        "photo_available_flag": false,
        "last_mod_date": "2018-03-26T22:56:16Z"
    },
    {
        "stage_text": "Left Front Door",
        "question_text": "Choose a \"Generic\" Color that best describes the Interior Color",
        "question_text_short": "Interior Generic Color",
        "answer": "Black",
        "answer_parent": "",
        "photo_url": null,
        "photo_point_flag": 0,
        "damage_flag": false,
        "option_flag": false,
        "stock_photo_flag": 0,
        "severity_descriptor": "",
        "wear_tear_flag": 0,
        "chargeable_flag": 0,
        "photo_available_flag": false,
        "last_mod_date": "2018-03-26T22:56:16Z"
    },
    {
        "stage_text": "Left Front Door",
        "question_text": "Select the Type of Roof (MULTIPLE CHOICE QUESTION)",
        "question_text_short": "Roof Type and Equipment",
        "answer": "Hard Top",
        "answer_parent": "",
        "photo_url": null,
        "photo_point_flag": 0,
        "damage_flag": false,
        "option_flag": true,
        "stock_photo_flag": 0,
        "severity_descriptor": "",
        "wear_tear_flag": 0,
        "chargeable_flag": 0,
        "photo_available_flag": false,
        "last_mod_date": "2018-03-26T22:56:16Z"
    }
  ]


.. note::
  - 1001: Automobile
  - 1009: Motorcycle
  - 1060: ATV/UTV
  - 1064: Snowmobile
  - 1061: Campers/RV

