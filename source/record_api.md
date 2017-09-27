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
 https://test.cdemo.com/api/latest/records?access_token=xxxx&inspection_id=xxxx,xxxx&lang=EN,FR

The interface of BackEnd works with the principe RESTfull

| Route             | Method |
|-------------------|--------|
| http://[...]/item	| GET    |


| First Header  | Second Header |
| ------------- | ------------- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |