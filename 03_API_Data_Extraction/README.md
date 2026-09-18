# API Data Extraction Assignment

## Objective

To understand REST APIs and JSON data and demonstrate how API data can be retrieved, inspected, converted into a Pandas DataFrame, and exported to CSV for analysis.

## API Used

**API:** JSONPlaceholder
**Endpoint:** `/posts`
**Request Method:** GET
**Authentication:** Not required

JSONPlaceholder is a free public API used for testing and learning API concepts.

## Concepts Covered

* REST API
* HTTP GET method
* JSON format
* API response
* Python requests library
* Pandas DataFrame
* CSV data export

## Process

The following workflow was performed:

1. Sent a GET request to the public API using Python.
2. Checked the HTTP response status code.
3. Converted the API response into JSON.
4. Inspected the JSON data structure.
5. Converted the JSON data into a Pandas DataFrame.
6. Examined the rows, columns, and data types.
7. Exported the DataFrame to a CSV file.
8. Loaded the CSV file again to verify the exported data.

## Python Libraries Used

```python
import requests
import pandas as pd
```

## API Request

```python
url = "https://jsonplaceholder.typicode.com/posts"

response = requests.get(url)

print(response.status_code)
```

The API returned HTTP status code **200**, indicating a successful request.

## JSON to DataFrame

```python
data = response.json()

df = pd.DataFrame(data)

df.head()
```

## Dataset

The API returned **100 records** with **4 columns**:

* `userId`
* `id`
* `title`
* `body`

## CSV Export

```python
df.to_csv("api_data.csv", index=False)
```

The resulting dataset was saved as:

`api_data.csv`

## Deliverables

* `API_Data_Extraction.ipynb` — Python notebook containing the API extraction process
* `api_data.csv` — Extracted API dataset
* `README.md` — Documentation of the API extraction process
