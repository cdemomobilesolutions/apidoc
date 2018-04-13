
=============
Record Detail
=============

Get Detail of a record.

.. sourcecode:: http

  GET /records/:inspection_id HTTP/1.1

+------------+--------------------------------------------------------------------------+
| Production | https://api.cdemo.com/v3/records/:inspection_id?access_token=<xxx>       |
+------------+--------------------------------------------------------------------------+

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

  {
    "inspection_id": "20180326ncxbjrhm",
    "title": "2014 Ford Focus SE Hatchback - Automatic, Alloy Wheels, SYNC",
    "status": 1,
    "staging_flag": 0,
    "store": {
        "id": 20114,
        "name": "Ride Time Certified"
    },
    "product": {
        "id": 1001,
        "description": "Automobiles"
    },
    "category": {
        "id": 3,
        "description": "Used Auto"
    },
    "item_condition": {
        "id": 2,
        "description": "Used"
    },
    "stocknumber": "18072",
    "style": {
        "id": 4,
        "description": "4 Door Station Wagon"
    },
    "dms_status": {
        "status": "0",
        "description": "Available For Sale (0)"
    },
    "record_type": {
        "id": 70,
        "description": "Quick"
    },
    "city": "Winnipeg",
    "region": "MB",
    "country_code": "CA",
    "photo_count": 39,
    "days_in_stock": 1,
    "detail_page_url": "http://live.cdemo.com/view-details/automobiles/used/2014-ford-focus-se-hatchback-automatic-alloy-wheels-sync/EPkyW88D",
    "inventory_date": "2018-03-26T22:31:16Z",
    "deficiency_flag": 0,
    "repair_info_flag": null,
    "whole_sale_price": "1.00",
    "invoice_price": null,
    "listing_currency": "CAD",
    "sale_price": null,
    "listing_price": "12500.00",
    "listing_comment": "",
    "wholesale_comment": null,
    "msrp": "19699.00",
    "financing_comment": "",
    "bi_weekly_finance_price": null,
    "monthly_finance_price": null,
    "weekly_finance_price": null,
    "down_payment": null,
    "monthly_period": null,
    "percent_apr": null,
    "sale_price_start_dt": null,
    "sale_price_end_dt": null,
    "youtube_video_id": "",
    "youtube_embed_url": "",
    "urls_for_360_image": "https://tours.motorstreet360.com/1FADP3K20EL365044",
    "primary_photo_url": "http://static.cdemo.com/65359357/1024/automobiles-used-2014-ford-focus-se-hatchback-automatic-alloy-wheels-sync-1729241-primary-listing-photo-Image.jpg",
    "primary_photo_thumbnail": "http://static.cdemo.com/65359357/150/automobiles-used-2014-ford-focus-se-hatchback-automatic-alloy-wheels-sync-1729241-primary-listing-photo-Image.jpg",
    "youtube_watch_url": "",
    "created_by": "alexmac",
    "created_date": "2018-03-26T21:53:13Z",
    "last_mod_date": "2018-03-27T08:15:28Z",
    "last_mod_by": "System",
    "detail": {
        "trim_level": "SE",
        "year_manufactured": "2014",
        "certified_program": null,
        "vin": "1FADP3K20EL365044",
        "engine_disp": "2.0",
        "package_codes": null,
        "additional_certified_program": "",
        "odometer_reading": 88770,
        "fuel_economy_hwy": null,
        "drivetrain": "Front Wheel Drive",
        "make": "Ford",
        "certified_program_flag": "No",
        "chrome_style_name": "5dr HB SE",
        "engine": "4 Cylinder Engine",
        "model_codes": null,
        "color_code": "UH",
        "interior_colour": "Charcoal Black w/Steel",
        "seating_capacity": "",
        "fuel_economy_unit": null,
        "option_codes": null,
        "number_passenger_doors": 4,
        "fuel_economy_city": null,
        "exterior_colour": "Black[Tuxedo Black Metallic]",
        "horse_power": null,
        "cylinders": "4",
        "odometer_type": "Kilometers",
        "transmission": "6-Speed A/T",
        "horse_power_rpm": null,
        "model": "Focus",
        "fuel_type": "Flex Fuel Capability"
    }
  }

.. note::
  - 1001: Automobile
  - 1009: Motorcycle
  - 1060: ATV/UTV
  - 1064: Snowmobile
  - 1061: Campers/RV
  - 1063: Trailers
