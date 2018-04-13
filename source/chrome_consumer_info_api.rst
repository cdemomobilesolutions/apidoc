
====================
Chrome Consumer Info
====================

Get chrome consumer info of a record.

.. warning::
    Only for Automobile product.

.. sourcecode:: http

  GET /records/:inspection_id/chrome_consumer_info HTTP/1.1

+------------+----------------------------------------------------------------------------------------+
| Production | https://api.cdemo.com/v3/records/:inspection_id/chrome_consumer_info?access_token=<xxx>|
+------------+----------------------------------------------------------------------------------------+

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
        "info_name": "Basic Years",
        "info_value": "3",
        "info_type": "Warranty"
    },
    {
        "info_name": "Basic Miles/km",
        "info_value": "60,000",
        "info_type": "Warranty"
    },
    {
        "info_name": "Drivetrain Years",
        "info_value": "5",
        "info_type": "Warranty"
    },
    {
        "info_name": "Drivetrain Miles/km",
        "info_value": "100,000",
        "info_type": "Warranty"
    },
    {
        "info_name": "Corrosion Years",
        "info_value": "5",
        "info_type": "Warranty"
    },
    {
        "info_name": "Corrosion Miles/km",
        "info_value": "Unlimited",
        "info_type": "Warranty"
    },
    {
        "info_name": "Roadside Assistance Years",
        "info_value": "5",
        "info_type": "Warranty"
    },
    {
        "info_name": "Roadside Assistance Miles/km",
        "info_value": "100,000",
        "info_type": "Warranty"
    },
    {
        "info_name": "NHTSA CAMPAIGN ID",
        "info_value": "14V525000",
        "info_type": "Recall"
    },
    {
        "info_name": "Mfg's Report Date",
        "info_value": "SEP 01, 2014",
        "info_type": "Recall"
    },
    {
        "info_name": "Component",
        "info_value": "FUEL SYSTEM, GASOLINE:DELIVERY",
        "info_type": "Recall"
    },
    {
        "info_name": "Potential Number of Units Affected",
        "info_value": "301",
        "info_type": "Recall"
    },
    {
        "info_name": "Summary",
        "info_value": "Ford Motor Company (Ford) is recalling certain model year 2014 Ford Focus vehicles manufactured May 1, 2014, to May 24, 2014, 2014 Ford Escape vehicles manufactured on June 6, 2014, and 2015 Lincoln MKC vehicles manufactured June 4, 2014, to July 7, 2014. In the affected vehicles, the Fuel Delivery Module (FDM) may crack between the filter body and the filter cap, possibly resulting in low fuel pressure.",
        "info_type": "Recall"
    }
  ]

.. note::
  - 1001: Automobile
  - 1009: Motorcycle
  - 1060: ATV/UTV
  - 1064: Snowmobile
  - 1061: Campers/RV
  - 1063: Trailers
