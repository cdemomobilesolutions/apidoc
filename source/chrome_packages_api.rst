
=================
Chrome Packages
=================

Get chrome packages of a record.

.. warning::
    Only for Automobile product.

.. sourcecode:: http

  GET /records/:inspection_id/chrome_packages HTTP/1.1

+------------+-----------------------------------------------------------------------------------+
| Production | https://api.cdemo.com/v3/records/:inspection_id/chrome_packages?access_token=<xxx>|
+------------+-----------------------------------------------------------------------------------+

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
        "category": "OPTION PACKAGE",
        "description": "ACCESSORY GRP 1",
        "msrp": 500.00,
        "include_equipments": "-inc: Popular Equipment Pkg w/AM/FM ETR stereo radio w/CD player & (6) speakers, pwr windows/mirrors/door locks",
        "other_info": ""
    }
  ]

.. note::
  - 1001: Automobile
  - 1009: Motorcycle
  - 1060: ATV/UTV
  - 1064: Snowmobile
  - 1061: Campers/RV
  - 1063: Trailers
