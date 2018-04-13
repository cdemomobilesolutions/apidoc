
=================
Chrome Equipments
=================

Get chrome equipments of a record.

.. warning::
    Only for Automobile product.

.. sourcecode:: http

  GET /records/:inspection_id/chrome_equipments HTTP/1.1

+------------+-------------------------------------------------------------------------------------+
| Production | https://api.cdemo.com/v3/records/:inspection_id/chrome_equipments?access_token=<xxx>|
+------------+-------------------------------------------------------------------------------------+

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
        "standard_header_name": "MECHANICAL",
        "description": "Engine: 2.0L I-4 GDI Ti-VCT Flex Fuel"
    },
    {
        "standard_header_name": "MECHANICAL",
        "description": "Transmission: 5-Speed Manual"
    },
    {
        "standard_header_name": "MECHANICAL",
        "description": "Front-Wheel Drive"
    },
    {
        "standard_header_name": "MECHANICAL",
        "description": "3.82 Axle Ratio"
    },
    {
        "standard_header_name": "MECHANICAL",
        "description": "590CCA Maintenance-Free Battery w/Run Down Protection"
    },
    {
        "standard_header_name": "MECHANICAL",
        "description": "3990# Gvwr 827# Maximum Payload"
    },
    {
        "standard_header_name": "MECHANICAL",
        "description": "Gas-Pressurized Shock Absorbers"
    },
    {
        "standard_header_name": "MECHANICAL",
        "description": "Front And Rear Anti-Roll Bars"
    },
    {
        "standard_header_name": "MECHANICAL",
        "description": "Electric Power-Assist Steering"
    },
    {
        "standard_header_name": "MECHANICAL",
        "description": "46.9 L Fuel Tank"
    },
    {
        "standard_header_name": "MECHANICAL",
        "description": "Single Stainless Steel Exhaust"
    },
    {
        "standard_header_name": "MECHANICAL",
        "description": "Strut Front Suspension w/Coil Springs"
    },
    {
        "standard_header_name": "MECHANICAL",
        "description": "Short And Long Arm Rear Suspension w/Coil Springs"
    }
  ]

.. note::
  - 1001: Automobile
  - 1009: Motorcycle
  - 1060: ATV/UTV
  - 1064: Snowmobile
  - 1061: Campers/RV
  - 1063: Trailers
