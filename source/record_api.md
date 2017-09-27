## Record API

### API End Point

+------------+-----------------------------------+ 
| Sandbox    | http://test.cdemo.com/api/latest/ | 
+============+===================================+
| Production | http://api.cdemo.com/api/latest/  |
+------------+-----------------------------------+


## API Methods

### Retrieve Record Details

All queries sent to backend:

- Method: records (HTTP METHOD: GET)
- Type of query: Record Data
- Return Type: JSON string of matched records.
- Example: 
-  https://test.cdemo.com/api/latest/records?access_token=xxxx&inspection_id=xxxx,xxxx&lang=EN,FR

The interface of BackEnd works with the principe RESTfull

+----------------+------------------+------------+-------------------+ 
| **Parameters** | **Is Mandatory** | **Notes**  | **Sample Usage**  |
+================+==================+============+===================+
| inspection_id  | No               | inspection_id of record. To pull multiple records on a single API call, concatenate inspection IDs with comma (,) such as inspection_id1,inspection_id2  | inspection_id=inspection_id=20140120cfwejboi,20140120bwtmncis         | 
+----------------+------------------+------------+-------------------+
| body row 1     | column 2         | column 3   | column 3          | 
+----------------+------------------+------------+-------------------+
