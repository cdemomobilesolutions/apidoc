===========
Record API
===========

Setup API Account
=================
- Please contact cDemo support

API End Points
=================
+------------+-----------------------------------+ 
| Sandbox    | http://test.cdemo.com/api/latest/ | 
+============+===================================+
| Production | http://api.cdemo.com/api/latest/  |
+------------+-----------------------------------+

API Methods
=================

Retrieve Record Details
-----------------------

All queries sent to backend:

:Method:
    records **(HTTP METHOD: GET)**
:Type of query:
    Record Data
:Return Type:
    JSON string of matched records.
:Example:
    https://test.cdemo.com/api/latest/records?access_token=xxxx&inspection_id=xxxx,xxxx&lang=EN,FR

The interface of BackEnd works with the principe RESTfull

+-----------------------+---------------+----------------------------+
| Parameters            | Is Mandatory  | Notes                      |
+-----------------------+---------------+----------------------------+
| Token                 | Yes           | a access token is required |
|                       |               | for all of the API's       |
|                       |               | request                    |
+-----------------------+---------------+----------------------------+
| inspection_id         | No            | inspection_id of record.   |
|                       |               | To pull multiple records   |
|                       |               | on a single API call,      |
|                       |               | concatenate inspection ID's|
|                       |               | with comma such as         |
|                       |               | inspection_id1,            |
|                       |               | inspection_id2             |
+-----------------------+---------------+----------------------------+
| vin_code              | No            | inspection_id              |
+-----------------------+---------------+----------------------------+
| lang                  | No            | inspection_id              |
+-----------------------+---------------+----------------------------+
