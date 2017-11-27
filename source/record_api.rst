=================
API Reference
=================

API End Points
=================
+------------+-----------------------------------------------------------+
| Production | https://api.cdemo.com/v3/records-export?access_token=<xxx>|
+------------+-----------------------------------------------------------+

Export Records API
=================

.. sourcecode:: http

  GET /records-export HTTP/1.1

Request
~~~~~~~

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
|                       |               | like chrome_equipments,chrome_packages|
+-----------------------+---------------+---------------------------------------+

Response
~~~~~~~~

+-----------------------+-------------------------------------------------------+
| Field Name            | Notes                                                 |
+=======================+=======================================================+
| inspection_id         | inspection_id                                         |
+-----------------------+-------------------------------------------------------+
| title                 | Vehicle Title                                         |
+-----------------------+-------------------------------------------------------+
| status                | Vehicle Status                                        |
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

Filter Querry Results
~~~~~~~~~~~~~~~~~~~~~~

To Filter querry results, use fields=<filter parameter> after the API token. Example:

- access_token<xxx>fields=chrome_equipments&status=1

This filter will only return the chrome equipments section and vehicles with status=1


Exclude Sections of JSON return
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Our API returns many data points, like inspection_points, chrome_equipments and so on. If you do not require a specific data point, you have the ability to exclude it from being sent.
Here is an example on how to use it:

After the API Token, use exclude_fields=<field name>
-exclude_fields=chrome_equipments,chrome_packages,chrome_consumer_info

This will prevent chrome_equipments, chrome_packages, and chrome_consumer_info sections from being sent.



JSON Return Example:
~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: python

  {
      "links": {
          "next": "https://api.cdemo.com/v3/records-export?access_token=xxx&page=2&page_size=2",
          "prev": null,
          "total_results": 506
      },
      "paginated_results": [
          {
              "inspection_id": "20171122ngbwkmep",
              "title": "2018 Jeep Cherokee",
              "status": 1,
              "staging_flag": 0,
              "store": {
                  "id": 1031366,
                  "name": "Great West Chrysler"
              },
              "product": {
                  "id": 1001,
                  "description": "Automobiles"
              },
              "category": {
                  "id": 2,
                  "description": "New Auto"
              },
              "item_condition": {
                  "id": 1,
                  "description": "New"
              },
              "style": {
                  "id": 6,
                  "description": "4 Door Sport Utility"
              },
              "dms_status": {
                  "status": "Available",
                  "description": "Available"
              },
              "record_type": {
                  "id": 20,
                  "description": "Auto-Generated"
              },
              "city": "Edmonton",
              "region": "AB",
              "country_code": "CA",
              "photo_count": 0,
              "days_in_stock": 1,
              "detail_page_url": "http://live.cdemo.com/view-details/automobiles/new/2018-jeep-cherokee/1eGjnaVD",
              "inventory_date": "2017-11-22T12:53:49Z",
              "deficiency_flag": null,
              "repair_info_flag": null,
              "whole_sale_price": null,
              "invoice_price": null,
              "listing_currency": "CAD",
              "sale_price": null,
              "listing_price": "48260.00",
              "listing_comment": "",
              "wholesale_comment": null,
              "msrp": null,
              "financing_comment": null,
              "bi_weekly_finance_price": null,
              "monthly_finance_price": null,
              "weekly_finance_price": null,
              "down_payment": null,
              "monthly_period": null,
              "percent_apr": null,
              "sale_price_start_dt": null,
              "sale_price_end_dt": null,
              "youtube_video_id": null,
              "youtube_embed_url": "",
              "urls_for_360_image": null,
              "primary_photo_url": "http://static.cdemo.com/65339522/1024/automobiles-new-2018-jeep-cherokee-1417868-primary-listing-photo-Image.jpg",
              "primary_photo_thumbnail": "http://static.cdemo.com/65339522/150/automobiles-new-2018-jeep-cherokee-1417868-primary-listing-photo-Image.jpg",
              "youtube_watch_url": "",
              "created_by": "system",
              "created_date": "2017-11-22T12:53:48Z",
              "last_mod_date": "2017-11-22T12:55:01Z",
              "last_mod_by": "System",
              "detail": {
                  "trim_level": null,
                  "year_manufactured": "2018",
                  "certified_program": null,
                  "vin": "1C4PJMBX1JD558463",
                  "engine_disp": "3.2",
                  "package_codes": null,
                  "additional_certified_program": null,
                  "odometer_reading": 10,
                  "fuel_economy_hwy": "9.4 - 9.9",
                  "drivetrain": "4WD",
                  "make": "Jeep",
                  "certified_program_flag": null,
                  "chrome_style_name": "Trailhawk Leather Plus 4x4",
                  "engine": "V6 Cylinder Engine",
                  "model_codes": null,
                  "color_code": null,
                  "interior_colour": "NAPPA LTHR",
                  "seating_capacity": null,
                  "fuel_economy_unit": "L/100 km",
                  "option_codes": null,
                  "number_passenger_doors": 4,
                  "fuel_economy_city": "12.1 - 12.9",
                  "exterior_colour": "PWY/BRIGHT WHT",
                  "horse_power": "271.0",
                  "cylinders": "6",
                  "odometer_type": "Kilometers",
                  "transmission": "9-Speed A/T",
                  "horse_power_rpm": "6500",
                  "model": "Cherokee",
                  "fuel_type": "Gasoline Fuel"
              },
              "inspection_points": [
                  {
                      "stage_text": "Vehicle Info",
                      "question_text": "Select if ODOMETER READING is in MILES or KILOMETERS",
                      "question_text_short": "Odometer Type",
                      "answer": "Kilometers",
                      "answer_parent": null,
                      "photo_url": null,
                      "photo_point_flag": 0,
                      "damage_flag": false,
                      "option_flag": false,
                      "stock_photo_flag": 0,
                      "severity_descriptor": null,
                      "wear_tear_flag": 0,
                      "chargeable_flag": 0,
                      "photo_available_flag": false,
                      "last_mod_date": "2017-11-22T12:53:48Z"
                  },
                  {
                      "stage_text": "Vehicle Info",
                      "question_text": "Select the fuel type for this vehicle.\r\n(Single Choice Answer)",
                      "question_text_short": "Vehicle Fuel Type",
                      "answer": "Gasoline",
                      "answer_parent": null,
                      "photo_url": null,
                      "photo_point_flag": 0,
                      "damage_flag": false,
                      "option_flag": true,
                      "stock_photo_flag": 0,
                      "severity_descriptor": null,
                      "wear_tear_flag": 0,
                      "chargeable_flag": 0,
                      "photo_available_flag": false,
                      "last_mod_date": "2017-11-22T12:54:12Z"
                  }
              ],
              "chrome_equipments": {
                  "SAFETY": [
                      "Electronic Stability Control (ESC) And Roll Stability Control (RSC)",
                      "Selec-Terrain ABS And Driveline Traction Control",
                      "Side Impact Beams",
                      "Dual Stage Driver And Passenger Seat-Mounted Side Airbags",
                      "Tire Specific Low Tire Pressure Warning",
                      "Dual Stage Driver And Passenger Front Airbags",
                      "Curtain 1st And 2nd Row Airbags",
                      "Airbag Occupancy Sensor",
                      "Driver And Passenger Knee Airbag and Rear Side-Impact Airbag",
                      "Rear Child Safety Locks",
                      "Outboard Front Lap And Shoulder Safety Belts -inc: Rear Centre 3 Point, Height Adjusters and Pretensioners",
                      "ParkView Back-Up Camera"
                  ],
                  "EXTERIOR": [
                      "Wheels: 17\" x 7.5\" Off-Road Aluminum",
                      "Tires: P245/65R17 OWL AT",
                      "Steel Spare Wheel",
                      "Full-Size Spare Tire Mounted Inside Under Cargo",
                      "Paint w/Badging",
                      "Black Front Bumper w/Coloured Bumper Insert and 2 Tow Hooks",
                      "Black Rear Bumper w/Metal-Look Rub Strip/Fascia Accent and 1 Tow Hook",
                      "Black Bodyside Cladding and Black Fender Flares",
                      "Body-Coloured Door Handles",
                      "Black Side Windows Trim",
                      "Fixed Rear Window w/Fixed Interval Wiper and Defroster",
                      "Deep Tinted Glass",
                      "Variable Intermittent Wipers",
                      "Composite/Galvanized Steel Panels",
                      "Lip Spoiler",
                      "Front License Plate Bracket",
                      "Black Grille w/Metal-Look Surround",
                      "Tailgate/Rear Door Lock Included w/Power Door Locks",
                      "Roof Rack Rails Only",
                      "Fully Automatic Projector Beam High Intensity Low/High Beam Daytime Running Headlamps w/Delay-Off",
                      "Front Fog Lamps",
                      "LED Brakelights"
                  ]
              },
              "chrome_packages": [],
              "chrome_consumer_info": [
                  {
                      "info_name": "Basic Years",
                      "info_value": "3",
                      "info_type": "Warranty"
                  },
                  {
                      "info_name": "Basic Miles/km",
                      "info_value": "60,000",
                      "info_type": "Warranty"
                  }
              ]
          },
          {
              "inspection_id": "20171122lbdmdyry",
              "title": "2018 Ram 1500",
              "status": 1,
              "staging_flag": 0,
              "store": {
                  "id": 1031366,
                  "name": "Great West Chrysler"
              },
              "product": {
                  "id": 1001,
                  "description": "Automobiles"
              },
              "category": {
                  "id": 2,
                  "description": "New Auto"
              },
              "item_condition": {
                  "id": 1,
                  "description": "New"
              },
              "style": {
                  "id": 9,
                  "description": "4 Door Pickup"
              },
              "dms_status": {
                  "status": "Available",
                  "description": "Available"
              },
              "record_type": {
                  "id": 20,
                  "description": "Auto-Generated"
              },
              "city": "Edmonton",
              "region": "AB",
              "country_code": "CA",
              "photo_count": 0,
              "days_in_stock": 1,
              "detail_page_url": "http://live.cdemo.com/view-details/automobiles/new/2018-ram-1500/DlxwdakD",
              "inventory_date": "2017-11-22T12:53:47Z",
              "deficiency_flag": null,
              "repair_info_flag": null,
              "whole_sale_price": null,
              "invoice_price": null,
              "listing_currency": "CAD",
              "sale_price": null,
              "listing_price": "66675.00",
              "listing_comment": "",
              "wholesale_comment": null,
              "msrp": null,
              "financing_comment": null,
              "bi_weekly_finance_price": null,
              "monthly_finance_price": null,
              "weekly_finance_price": null,
              "down_payment": null,
              "monthly_period": null,
              "percent_apr": null,
              "sale_price_start_dt": null,
              "sale_price_end_dt": null,
              "youtube_video_id": null,
              "youtube_embed_url": "",
              "urls_for_360_image": null,
              "primary_photo_url": "http://static.cdemo.com/65339521/1024/automobiles-new-2018-ram-1500-1492797-primary-listing-photo-Image.jpg",
              "primary_photo_thumbnail": "http://static.cdemo.com/65339521/150/automobiles-new-2018-ram-1500-1492797-primary-listing-photo-Image.jpg",
              "youtube_watch_url": "",
              "created_by": "system",
              "created_date": "2017-11-22T12:53:46Z",
              "last_mod_date": "2017-11-22T12:55:05Z",
              "last_mod_by": "System",
              "detail": {
                  "trim_level": null,
                  "year_manufactured": "2018",
                  "certified_program": null,
                  "vin": "1C6RR7NT2JS187635",
                  "engine_disp": "5.7",
                  "package_codes": null,
                  "additional_certified_program": null,
                  "odometer_reading": 10,
                  "fuel_economy_hwy": "11.5 - 11.5",
                  "drivetrain": "4WD",
                  "make": "Ram",
                  "certified_program_flag": null,
                  "chrome_style_name": "Laramie 4x4 Crew Cab 5'7\" Box",
                  "engine": "8 Cylinder Engine",
                  "model_codes": null,
                  "color_code": "PW7",
                  "interior_colour": "Leather",
                  "seating_capacity": null,
                  "fuel_economy_unit": "L/100 km",
                  "option_codes": null,
                  "number_passenger_doors": 4,
                  "fuel_economy_city": "16.1 - 16.1",
                  "exterior_colour": "White[Bright White]",
                  "horse_power": "395.0",
                  "cylinders": "8",
                  "odometer_type": "Kilometers",
                  "transmission": "8-Speed A/T",
                  "horse_power_rpm": "5600",
                  "model": "1500",
                  "fuel_type": "Gasoline Fuel"
              },
              "inspection_points": [
                  {
                      "stage_text": "Vehicle Info",
                      "question_text": "Select if ODOMETER READING is in MILES or KILOMETERS",
                      "question_text_short": "Odometer Type",
                      "answer": "Kilometers",
                      "answer_parent": null,
                      "photo_url": null,
                      "photo_point_flag": 0,
                      "damage_flag": false,
                      "option_flag": false,
                      "stock_photo_flag": 0,
                      "severity_descriptor": null,
                      "wear_tear_flag": 0,
                      "chargeable_flag": 0,
                      "photo_available_flag": false,
                      "last_mod_date": "2017-11-22T12:53:46Z"
                  },
                  {
                      "stage_text": "Vehicle Info",
                      "question_text": "Select the fuel type for this vehicle.\r\n(Single Choice Answer)",
                      "question_text_short": "Vehicle Fuel Type",
                      "answer": "Gasoline",
                      "answer_parent": null,
                      "photo_url": null,
                      "photo_point_flag": 0,
                      "damage_flag": false,
                      "option_flag": true,
                      "stock_photo_flag": 0,
                      "severity_descriptor": null,
                      "wear_tear_flag": 0,
                      "chargeable_flag": 0,
                      "photo_available_flag": false,
                      "last_mod_date": "2017-11-22T12:54:14Z"
                  }
              ],
              "chrome_equipments": {
                  "SAFETY": [
                      "Electronic Stability Control (ESC)",
                      "ABS And Driveline Traction Control",
                      "Side Impact Beams",
                      "Dual Stage Driver And Passenger Seat-Mounted Side Airbags",
                      "ParkSense Rear Parking Sensors",
                      "Tire Specific Low Tire Pressure Warning",
                      "Dual Stage Driver And Passenger Front Airbags",
                      "Airbag Occupancy Sensor",
                      "Curtain 1st And 2nd Row Airbags",
                      "Rear Child Safety Locks",
                      "Outboard Front Lap And Shoulder Safety Belts -inc: Rear Centre 3 Point, Height Adjusters and Pretensioners",
                      "ParkView Back-Up Camera"
                  ],
                  "EXTERIOR": [
                      "Wheels: 20\" x 9\" Chrome-Clad Aluminum",
                      "Tires: P275/60R20 BSW All-Season",
                      "Regular Box Style",
                      "Goodyear Brand Tires",
                      "Steel Spare Wheel",
                      "Full-Size Spare Tire Stored Underbody w/Crankdown",
                      "Clearcoat Paint",
                      "Chrome Front Bumper w/Body-Coloured Rub Strip/Fascia Accent",
                      "Chrome Rear Step Bumper",
                      "Black Side Windows Trim and Black Front Windshield Trim",
                      "Chrome Door Handles",
                      "Body-Coloured Fender Flares",
                      "Chrome Power w/Tilt Down Heated Auto Dimming Side Mirrors w/Power Folding and Turn Signal Indicator",
                      "Power Rear Window",
                      "Variable Intermittent Wipers",
                      "Deep Tinted Glass",
                      "Galvanized Steel/Aluminum Panels",
                      "Chrome Grille",
                      "Front License Plate Bracket",
                      "Tailgate Rear Cargo Access",
                      "Tailgate/Rear Door Lock Included w/Power Door Locks",
                      "Cargo Lamp w/High Mount Stop Light",
                      "Fully Automatic Projector Beam Halogen Daytime Running Headlamps w/Delay-Off",
                      "Front Fog Lamps",
                      "Perimeter/Approach Lights",
                      "LED Brakelights"
                  ]
              },
              "chrome_packages": [],
              "chrome_consumer_info": [
                  {
                      "info_name": "Basic Years",
                      "info_value": "3",
                      "info_type": "Warranty"
                  },
                  {
                      "info_name": "Basic Miles/km",
                      "info_value": "60,000",
                      "info_type": "Warranty"
                  }
              ]
          }
      ]
  }
