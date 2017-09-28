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

 ==============  =======
 Request Header   Value
 ==============  =======
 St2-Api-Key      Y2YyYWJkOGFkNDgxYTdiZDI0ZDdjNzU1NmE0NzA2ZWJiYTBlNTE5YmJlOTg1ODU0MzNmNjc3MzcxNDE0MDFhZA
 content-type     application/json
 ==============  =======

================  ============
a short sentence  second cell
a much longer     bottom right
  sentence
================  ============
