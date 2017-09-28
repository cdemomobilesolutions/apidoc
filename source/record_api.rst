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
+=======================+===============+============================+
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
| vin_code              | No            | vin code of vehicle. To    |
|                       |               | pull multiple records on   |
|                       |               | a single API call,         |
|                       |               | concatenate vin codes with |
|                       |               | comma(,) such as vin_code_1|
|                       |               | ,vin_code_2                |
+-----------------------+---------------+----------------------------+
| lang                  | No            | language flag such as      |
|                       |               | lang=EN or lang=EN,FR      |
+-----------------------+---------------+----------------------------+


**Sample Usage**

+---------------+-------------------------------+
| Token         | token=xxxxxx                  |
+---------------+-------------------------------+
| inspection_id | inspection_id=inspection_id=  |
|               | 20140120cfwejboi,             |
|               | 20140120bwtmncis              |
+---------------+-------------------------------+
| vin_code      | vin_code=3C6TRVAG4EE103634,   |
|               | KM8JT3AB1DU752443             |
+---------------+-------------------------------+
| lang          | lang=EN,FR                    |
+---------------+-------------------------------+







Retrieve Unique Record ID's (Inspection ID's)
==============================================

+-----------------------+---------------+---------------------------------------+
| Parameters            | Is Mandatory  | Notes                                 |
+=======================+===============+=======================================+
| Token                 | Yes           | a access token is required            |
|                       |               | for all of the API's                  |
|                       |               | request                               |
+-----------------------+---------------+---------------------------------------+
| user_id               | No            | cDemo username                        |
+-----------------------+---------------+---------------------------------------+
| party_id              | No            | cDemo party_id                        |
+-----------------------+---------------+---------------------------------------+
| date_from             | No            | start date of record created in       |
|                       |               | milliseconds (the difference, measured|
|                       |               | in millisecond, between the current   |
|                       |               | time and midnight, January 1,1970 UTC)|
+-----------------------+---------------+---------------------------------------+
| date_to               | No            | start date of record created in       |
|                       |               | milliseconds (the difference, measured|
|                       |               | in millisecond, between the current   |
|                       |               | time and midnight, January 1,1970 UTC)|
+-----------------------+---------------+---------------------------------------+
| update_date_from      | No            | start date of record UPDATED date in  |
|                       |               | milliseconds (the difference, measured|
|                       |               | in millisecond, between the current   |
|                       |               | time and midnight, January 1,1970 UTC)|
+-----------------------+---------------+---------------------------------------+
| update_date_to        | No            | start date of record UPDATED date in  |
|                       |               | milliseconds (the difference, measured|
|                       |               | in millisecond, between the current   |
|                       |               | time and midnight, January 1,1970 UTC)|
+-----------------------+---------------+---------------------------------------+
| cat_id                | No            | cDemo category ID                     |
+-----------------------+---------------+---------------------------------------+
| type_id               | No            | cDemo record type ID                  |
+-----------------------+---------------+---------------------------------------+
| status                | No            | status code: 0 - In-Progress, 1 -     |
|                       |               | Available and 2 - Archived            |
+-----------------------+---------------+---------------------------------------+
| vin_decode_status     | No            |  See Below                            |
+-----------------------+---------------+---------------------------------------+

vin_decode_status
    Status and Explanation:

    I: Indicates VIN Decoding is in progress.
    ER: VIN was probably valid, but decoding failed for other reason (usually bad data return / unable to decode from Chrome)
    IV: Indicates non-Valid VIN and VIN-Decoding not used. This will occur if VIN is incorrect or if it is a pre-1981 VIN
    SC: Is normal status indicating valid-VIN and good Decode