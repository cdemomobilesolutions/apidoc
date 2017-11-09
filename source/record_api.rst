===========
Record API
===========

Setup API Account
=================
- Please contact cDemo support

API End Points
=================
+------------+-----------------------------------+
| Production | http://api.cdemo.com/api/latest/  |
+------------+-----------------------------------+

API Methods
=================


Retrieve Unique Record ID's (Inspection ID's)
==============================================

:Method:
    records **(HTTP METHOD: GET)**
:Type of query:
    inspection_ids
:Return Type:
    JSON string of matched inspection IDs
:Example:
    https://test.cdemo.com/api/latest/records/inspection-ids?access_token=xxxxx&status=1


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
| cat_id                | No            | See Below                             |
+-----------------------+---------------+---------------------------------------+
| status                | No            | status code: 0 - In-Progress, 1 -     |
|                       |               | Available and 2 - Archived            |
+-----------------------+---------------+---------------------------------------+
| vin_decode_status     | No            |  See Below                            |
+-----------------------+---------------+---------------------------------------+
| make                  | No            | make of automobile record.            |
+-----------------------+---------------+---------------------------------------+
| model                 | No            | model of automobile record.           |
+-----------------------+---------------+---------------------------------------+
| year                  | No            | manufactured year of automobile record|
+-----------------------+---------------+---------------------------------------+

vin_decode_status
    Status and Explanation:

    - I: Indicates VIN Decoding is in progress.
    - ER: VIN was probably valid, but decoding failed for other reason (usually bad data return / unable to decode from Chrome)
    - IV: Indicates non-Valid VIN and VIN-Decoding not used. This will occur if VIN is incorrect or if it is a pre-1981 VIN
    - SC: Is normal status indicating valid-VIN and good Decode

cat_id
    Status and Explanation:

    - 2: New Automobile
    - 3: Used Automobile
    - 1009: Motorcycle
    - 1060: ATVs & UTVs
    - 1061: Campers
    - 1062: RVs
    - 1063: Trailers
    - 1064: Snowmobiles


**Sample Usage**

+------------------+-------------------------------+
| Token            | token=xxxxxx                  |
+------------------+-------------------------------+
| user_id          | user_id=cdemotest             |
+------------------+-------------------------------+
| party_id         | party_id=10                   |
+------------------+-------------------------------+
| date_from        | date_from=1372060916          |
+------------------+-------------------------------+
| date_to          | date_to=1372061234            |
+------------------+-------------------------------+
| update_date_from | update_date_from=1372060916   |
+------------------+-------------------------------+
| update_date_to   | update_date_to=1372061234     |
+------------------+-------------------------------+
| cat_id           | cat_id=2                      |
+------------------+-------------------------------+
| type_id          | type_id=3                     |
+------------------+-------------------------------+
| status           | status=1,2                    |
+------------------+-------------------------------+
| vin_decode_status| vin_decode_status=SC          |
+------------------+-------------------------------+
| make             | make=Mitsubishi               |
+------------------+-------------------------------+
| model            | model=Outlander               |
+------------------+-------------------------------+
| year             | year=2016                     |
+------------------+-------------------------------+

Query for inspection_ids:
    If  inspection_id parameter is missing from the request, Records APIs will try to query inspections IDs as defined by other query parameters.
        You can pass one or more of these query parameters to cDemo system. The default filter is the party_id associated with the access token. Currently cDemo system has limited the returned inspection_ids to 1,000 for each query (latest records first).  To use this query API efficiently, please supply as much parameters as you can.



Retrieve Record Details
========================

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

Retrieve Records (Single Call)
==============================================

:Method:
    records **(HTTP METHOD: GET)**
:Type of query:
    paginated records.
:Return Type:
    JSON string of matched records.
:Example:
    https://test.cdemo.com/api/latest/inventories?access_token=xxxxx

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
| cat_id                | No            | See Below                             |
+-----------------------+---------------+---------------------------------------+
| status                | No            | status code: 0 - In-Progress, 1 -     |
|                       |               | Available and 2 - Archived            |
+-----------------------+---------------+---------------------------------------+
| vin_decode_status     | No            |  See Below                            |
+-----------------------+---------------+---------------------------------------+
| make                  | No            | make of automobile record.            |
+-----------------------+---------------+---------------------------------------+
| model                 | No            | model of automobile record.           |
+-----------------------+---------------+---------------------------------------+
| year                  | No            | manufactured year of automobile record|
+-----------------------+---------------+---------------------------------------+
| page                  | No            | the page of paginated records. default|
|                       |               | is 1. pagesize is 10.                                 |
+-----------------------+---------------+---------------------------------------+

vin_decode_status
    Status and Explanation:

    - I: Indicates VIN Decoding is in progress.
    - ER: VIN was probably valid, but decoding failed for other reason (usually bad data return / unable to decode from Chrome)
    - IV: Indicates non-Valid VIN and VIN-Decoding not used. This will occur if VIN is incorrect or if it is a pre-1981 VIN
    - SC: Is normal status indicating valid-VIN and good Decode

cat_id
    Status and Explanation:

    - 2: New Automobile
    - 3: Used Automobile
    - 1009: Motorcycle
    - 1060: ATVs & UTVs
    - 1061: Campers
    - 1062: RVs
    - 1063: Trailers
    - 1064: Snowmobiles


**Sample Usage**

+------------------+-------------------------------+
| Token            | token=xxxxxx                  |
+------------------+-------------------------------+
| user_id          | user_id=cdemotest             |
+------------------+-------------------------------+
| party_id         | party_id=10                   |
+------------------+-------------------------------+
| date_from        | date_from=1372060916          |
+------------------+-------------------------------+
| date_to          | date_to=1372061234            |
+------------------+-------------------------------+
| update_date_from | update_date_from=1372060916   |
+------------------+-------------------------------+
| update_date_to   | update_date_to=1372061234     |
+------------------+-------------------------------+
| cat_id           | cat_id=2                      |
+------------------+-------------------------------+
| type_id          | type_id=3                     |
+------------------+-------------------------------+
| status           | status=1,2                    |
+------------------+-------------------------------+
| vin_decode_status| vin_decode_status=SC          |
+------------------+-------------------------------+
| make             | make=Mitsubishi               |
+------------------+-------------------------------+
| model            | model=Outlander               |
+------------------+-------------------------------+
| year             | year=2016                     |
+------------------+-------------------------------+
| page             | page=1                        |
+------------------+-------------------------------+
