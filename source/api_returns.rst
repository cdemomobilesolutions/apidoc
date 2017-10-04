===================
API Returns (JSON)
===================

Sample Returns
===============

Sample Return for querying inspection IDs:

.. code-block:: json

    {
    "status":0,"message":"","content":
    ["20131126kwsgnnis","20131126lxhmobvx","20131125gguuulwg","20131122pbrjcrii",
    "20131122uumxpitu","20131121nffiosmx","20131121uxntydkq","20131121yeudydnp","20131121ywlswcod","20131119ycdkfoyq",
    "20131119bevlkucl","20131119sgqkbdey","20131118owootgmb","20131115fycqfndt","20131114grfnulmv","20131112pmmwutyb",
    "20131107jkpiokjy","20131106nmiykxjl","20131106njjlwwgo"]
    }


Sample Return for Record Details
==========================================

Record Attributes
-------------------

.. code-block:: json

    {
    "attribute_key": "VIN",
    "language": "EN",
    "attribute_value": "1GCEC14W1VZ159730"
    },




+---------------------+-------------------------------+-------------------------------+
| **Attribute**       | **Map**                       | **Key**                       |
+---------------------+-------------------------------+-------------------------------+
| VIN                 | record_attribute              | VIN                           |
+---------------------+-------------------------------+-------------------------------+
| Stock Number        | record_attribute              | STOCK_NUMBER                  |
+---------------------+-------------------------------+-------------------------------+
| Vehicle Year        | record_attribute              | VEH_YEAR                      |
+---------------------+-------------------------------+-------------------------------+
| Vehicle Make        | record_attribute              | VEH_MAKE                      |
+---------------------+-------------------------------+-------------------------------+
| Vehicle Model       | record_attribute              | VEH_MODEL                     |
+---------------------+-------------------------------+-------------------------------+
| Engine              | record_attribute              | VEH_ENGINE                    |
+---------------------+-------------------------------+-------------------------------+
| Transmission Spd    | record_attribute              | VEH_TRANS                     |
+---------------------+-------------------------------+-------------------------------+
| Drivetrain          | record_attribute              | VEH_DRIVETRAIN                |
+---------------------+-------------------------------+-------------------------------+
| Exterior Color      | record_attribute              | VEH_EXT_COLOR                 |
+---------------------+-------------------------------+-------------------------------+
| Interoir Color      | record_attribute              | VEH_INT_COLOR                 |
+---------------------+-------------------------------+-------------------------------+