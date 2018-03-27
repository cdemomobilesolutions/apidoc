
========
Records
========

List records of a store.

.. sourcecode:: http

  GET /records HTTP/1.1

+------------+-----------------------------------------------------------+
| Production | https://api.cdemo.com/v3/records?access_token=<xxx>       |
+------------+-----------------------------------------------------------+

Parameters
==========

+-----------------------+---------------+---------------------------------------+
| Parameters            | Is Mandatory  | Notes                                 |
+=======================+===============+=======================================+
| access_token          | Yes           | API Token                             |
+-----------------------+---------------+---------------------------------------+
| date_from             | No            | format like 2017-11-16                |
+-----------------------+---------------+---------------------------------------+
| date_to               | No            | format like 2017-11-16                |
+-----------------------+---------------+---------------------------------------+
| price_from            | No            | listing_price range from, like 100.00 |
+-----------------------+---------------+---------------------------------------+
| price_to              | No            | listing_price range to, like 100.00   |
+-----------------------+---------------+---------------------------------------+
| has_comment           | No            | whether or not have comment,          |
|                       |               | value 'YES' or 'NO'                   |
+-----------------------+---------------+---------------------------------------+
| has_video             | No            | whether or not have video,            |
|                       |               | value 'YES' or 'NO'                   |
+-----------------------+---------------+---------------------------------------+
| has_price             | No            | whether or not have listing price,    |
|                       |               | value 'YES' or 'NO'                   |
+-----------------------+---------------+---------------------------------------+
| has_sale_price        | No            | whether or not have sale price,       |
|                       |               | value 'YES' or 'NO'                   |
+-----------------------+---------------+---------------------------------------+
| real_photo_count      | No            | whether or not have photos,           |
|                       |               | value 'YES' or 'NO'                   |
+-----------------------+---------------+---------------------------------------+
| is_certified          | No            | whether or not is certified,          |
|                       |               | value 'YES' or 'NO'                   |
+-----------------------+---------------+---------------------------------------+
| has_damage            | No            | whether or not is deficiency,         |
|                       |               | value 'YES' or 'NO'                   |
+-----------------------+---------------+---------------------------------------+
| is_staging            | No            | value 0 or 1                          |
+-----------------------+---------------+---------------------------------------+
| dms_status_id         | No            | dms_status_id                         |
+-----------------------+---------------+---------------------------------------+
| status                | No            | status code: 0 - In-Progress, 1 -     |
|                       |               | Available and 2 - Archived            |
+-----------------------+---------------+---------------------------------------+
| stocknumber           | No            | stock number of record.               |
+-----------------------+---------------+---------------------------------------+
| condition_id          | No            | item condition id.                    |
+-----------------------+---------------+---------------------------------------+
| make                  | No            | make of automobile records.           |
+-----------------------+---------------+---------------------------------------+
| model                 | No            | model of automobile records.          |
+-----------------------+---------------+---------------------------------------+
| year_manufactured     | No            | year_manufactured of automobile       |
|                       |               | records.                              |
+-----------------------+---------------+---------------------------------------+
| page                  | No            | default is 1                          |
+-----------------------+---------------+---------------------------------------+
| page_size             | No            | default is 10                         |
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
~~~~~~~~

.. +-----------------------+-------------------------------------------------------+
  | Field Name            | Notes                                                 |
  +=======================+=======================================================+
  | inspection_id         | inspection_id                                         |
  +-----------------------+-------------------------------------------------------+
  | title                 | inspection_id                                         |
  +-----------------------+-------------------------------------------------------+
  | status                | inspection_id                                         |
  +-----------------------+-------------------------------------------------------+
  | ...                   | ...                                                   |
  +-----------------------+-------------------------------------------------------+
  | detail                | detail                                                |
  +-----------------------+-------------------------------------------------------+
  | inspection_points     | inspection_points                                     |
  +-----------------------+-------------------------------------------------------+
  | chrome_equipments     | chrome_equipments                                     |
  +-----------------------+-------------------------------------------------------+
  | chrome_packages       | chrome_packages                                       |
  +-----------------------+-------------------------------------------------------+
  | chrome_consumer_info  | chrome_consumer_info                                  |
  +-----------------------+-------------------------------------------------------+

.. code-block:: python

  {
    "links": {
        "next": "https://api.cdemo.com/v3/records?access_token=xxxxxxxxxxx",
        "prev": null,
        "total_results": 117
    },
    "paginated_results": [
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
            "last_mod_date": "2018-03-26T23:02:46Z",
            "last_mod_by": "System",
            "detail": {
                "trim_level": "SE",
                "year_manufactured": "2014",
                "certified_program": null,
                "vin": "1FADP3K20EL365044",
                "engine_disp": "2.0",
                "package_codes": null,
                "additional_certified_program": "",
                "odometer_reading": 88800,
                "fuel_economy_hwy": null,
                "drivetrain": "Front Wheel Drive",
                "make": "Ford",
                "certified_program_flag": "",
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
        },
        {
            "inspection_id": "20180324jfwvyhjl",
            "title": "2015 Jeep Cherokee Trailhawk 4WD - Mango Tango Pearl, UConnect, Backup Camera, Navigation",
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
            "stocknumber": "18078",
            "style": {
                "id": 6,
                "description": "4 Door Sport Utility"
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
            "detail_page_url": "http://live.cdemo.com/view-details/automobiles/used/2015-jeep-cherokee-trailhawk-4wd-mango-tango-pearl-uconnect-backup-camera-navigation/D4VGNaj1",
            "inventory_date": "2018-03-26T15:24:37Z",
            "deficiency_flag": 0,
            "repair_info_flag": null,
            "whole_sale_price": "1.00",
            "invoice_price": null,
            "listing_currency": "CAD",
            "sale_price": null,
            "listing_price": "27000.00",
            "listing_comment": "",
            "wholesale_comment": null,
            "msrp": "32545.00",
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
            "urls_for_360_image": "https://tours.motorstreet360.com/1C4PJMBB7FW576711",
            "primary_photo_url": "http://static.cdemo.com/65359248/1024/automobiles-used-2015-jeep-cherokee-trailhawk-4wd-mango-tango-pearl-uconnect-backup-camera-1547238-primary-listing-photo-Image.jpg",
            "primary_photo_thumbnail": "http://static.cdemo.com/65359248/150/automobiles-used-2015-jeep-cherokee-trailhawk-4wd-mango-tango-pearl-uconnect-backup-camera-1547238-primary-listing-photo-Image.jpg",
            "youtube_watch_url": "",
            "created_by": "alexmac",
            "created_date": "2018-03-24T22:44:03Z",
            "last_mod_date": "2018-03-27T04:31:25Z",
            "last_mod_by": "System",
            "detail": {
                "trim_level": "Trailhawk",
                "year_manufactured": "2015",
                "certified_program": null,
                "vin": "1C4PJMBB7FW576711",
                "engine_disp": "2.4",
                "package_codes": null,
                "additional_certified_program": "",
                "odometer_reading": 84205,
                "fuel_economy_hwy": "9.4 - 9.4",
                "drivetrain": "Four Wheel Drive",
                "make": "Jeep",
                "certified_program_flag": "",
                "chrome_style_name": "4WD 4dr Trailhawk",
                "engine": "4 Cylinder Engine",
                "model_codes": null,
                "color_code": "PVG",
                "interior_colour": "Black",
                "seating_capacity": "",
                "fuel_economy_unit": "L/100 km",
                "option_codes": null,
                "number_passenger_doors": 4,
                "fuel_economy_city": "12.1 - 12.1",
                "exterior_colour": "Orange[Mango Tango Pearl]",
                "horse_power": "184.0",
                "cylinders": "4",
                "odometer_type": "Kilometers",
                "transmission": "9-Speed A/T",
                "horse_power_rpm": "6400",
                "model": "Cherokee",
                "fuel_type": "Gasoline Fuel"
            }
        },
        {
            "inspection_id": "20180324dncnvhsu",
            "title": "2014 Chevrolet Cruze 2LT - RS Package, Leather, Sunroof, Alloy Wheels, Heated Seats",
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
            "stocknumber": "18063",
            "style": {
                "id": 2,
                "description": "4 Door Car"
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
            "days_in_stock": 3,
            "detail_page_url": "http://live.cdemo.com/view-details/automobiles/used/2014-chevrolet-cruze-2lt-rs-package-leather-sunroof-alloy-wheels-heated-seats/1Lz8ly5D",
            "inventory_date": "2018-03-24T20:17:59Z",
            "deficiency_flag": 0,
            "repair_info_flag": null,
            "whole_sale_price": "1.00",
            "invoice_price": null,
            "listing_currency": "CAD",
            "sale_price": null,
            "listing_price": "13500.00",
            "listing_comment": "Meet our stellar 2014 Chevrolet Cruze 2LT Automatic Sedan with a fluid style and sporty substance as displayed in Silver Ice Metallic! Powered by a 1.4 Liter TurboCharged 4 Cylinder that offers 138hp while paired with a smooth shifting 6 Speed Automatic transmission that does its job seamlessly and with perfection. Enjoy the way the tight suspension of this Front Wheel Drive Cruze grabs the curves while it delivers an incredible 6.2L/100km on the open road! You will love the sweet aerodynamics and distinct alloy wheels!\n\nOur 2LT Automatic is designed for the driver with features like a leather-wrapped shift knob, heated seating, a sunroof and steering wheel with audio controls. You will also enjoy the full-color MyLink touchscreen infotainment center that integrates wireless connectivity through Bluetooth to safely and quickly access your smartphone apps while on the go!\n\nThis Cruze from Chevrolet provides you with the security, performance, and affordability you are looking for. Some of the safety features include StabiliTrak, an army of airbags, and more to make Our Cruze one of the safest machines out there. Print this page and call us Now... We Know You Will Enjoy Your Test Drive Towards Ownership! We are Family Owned and here to make your car buying and ownership enjoyable!",
            "wholesale_comment": null,
            "msrp": "21395.00",
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
            "urls_for_360_image": "https://tours.motorstreet360.com/1G1PE5SB6E7156627",
            "primary_photo_url": "http://static.cdemo.com/65359243/1024/automobiles-used-2014-chevrolet-cruze-2lt-rs-package-leather-sunroof-alloy-wheels-heated-seats-1370298-primary-listing-photo-Image.jpg",
            "primary_photo_thumbnail": "http://static.cdemo.com/65359243/150/automobiles-used-2014-chevrolet-cruze-2lt-rs-package-leather-sunroof-alloy-wheels-heated-seats-1370298-primary-listing-photo-Image.jpg",
            "youtube_watch_url": "",
            "created_by": "alexmac",
            "created_date": "2018-03-24T19:40:04Z",
            "last_mod_date": "2018-03-26T15:44:06Z",
            "last_mod_by": "dealerassistnow",
            "detail": {
                "trim_level": "2LT",
                "year_manufactured": "2014",
                "certified_program": null,
                "vin": "1G1PE5SB6E7156627",
                "engine_disp": "1.4",
                "package_codes": null,
                "additional_certified_program": "",
                "odometer_reading": 97493,
                "fuel_economy_hwy": "5.2 - 5.2",
                "drivetrain": "Front Wheel Drive",
                "make": "Chevrolet",
                "certified_program_flag": "No",
                "chrome_style_name": "4dr Sdn 2LT",
                "engine": "4 Cylinder Engine",
                "model_codes": null,
                "color_code": "GAN",
                "interior_colour": "Jet Black",
                "seating_capacity": "",
                "fuel_economy_unit": "L/100 km",
                "option_codes": null,
                "number_passenger_doors": 4,
                "fuel_economy_city": "7.8 - 7.8",
                "exterior_colour": "Silver[Silver Ice Metallic]",
                "horse_power": "138.0",
                "cylinders": "4",
                "odometer_type": "Kilometers",
                "transmission": "6-Speed A/T",
                "horse_power_rpm": "4900",
                "model": "Cruze",
                "fuel_type": "Gasoline Fuel"
            }
        }
    ]
  }

.. .. note::
    test
