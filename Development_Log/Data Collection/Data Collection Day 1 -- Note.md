On Day 1 of this project, I spent some time understanding the following methods to expand my knowledge of using the pandas and requests libraries.

- `pd.set_option()` allows configuration of pandas DataFrame display settings:
    
    - `pd.set_option('display.max_columns', None)` enables viewing all columns in the DataFrame.
        
    - `pd.set_option('display.max_colwidth', None)` enables viewing the entire content of each column, preventing truncation.
    
	- **Note:** Use `pd.reset_option('display.max_colwidth')` to reset this setting to the default value.
        
- `requests.get(URL)` retrieves data from a RESTful API using a specified URL.
    
    - The returned object from `requests.get(URL)` is typically assigned to a variable named `response`.
        
        - Use `response.status_code` to check the status of the API request.
            
        - If the response is a JSON object, use `response.json()` to convert it into a Python list or dictionary object.
            
        - To further flatten the JSON data into a DataFrame, use `pd.json_normalize(response.json())`.  
            This is useful when JSON data contains nested dictionaries, allowing these nested structures to be expanded into separate columns.
Example: (After Json)
```
import pandas as pd

data = response.json()
df_json = pd.DataFrame(data)
print(df_json)
```

| id  | name  | scores                        |
| --- | ----- | ----------------------------- |
| 1   | Alice | `{'math': 85, 'science': 90}` |
| 2   | Bob   | `{'math': 78, 'science': 88}` |
Example: (After Json Normalize)
```
import pandas as pd

data = response.json()
df_normalized = pd.json_normalize(data)
print(df_normalized)

```
 
|id|name|scores.math|scores.science|
|---|---|---|---|
|1|Alice|85|90|
|2|Bob|78|88|


