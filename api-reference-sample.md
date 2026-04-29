# REST Countries API - Beginner's Guide
## Overview
The REST Countries API lets you retrive information about any country in the world, without sign-up, API key, or any expense.

Send a request with a country name and receive most details about that country. For example, you can check the country  details like the capital city, population, currency, and more.

**Base URL:** `https://restcountries.com/v3.1`

**Format:** JSON

## Authentication
None. No sign-up or API key needed.

## Endpoints

### Get Country by Name
Retrieve detailed information about a country.

**Method:** `GET`

**Endpoint:** `/name/{country}`

**Full URL:** `https://restcountries.com/v3.1/name/{country}`  
where *{country}* is a placeholder for any country name. For example, replace it with *France*, *Japan*, *India*, or any other.

> **Tip:** Use the full official country name for accurate results.
> For example, *america* returns United States of America, but
> *united states* returns unexpected results, like US Virgin Islands.

**Example:** `https://restcountries.com/v3.1/name/germany`

### Sample Response
Here is a partial response for *germany*:
```json
{
"name": {
"common": "Germany",
"official": "Federal Republic of Germany"
},
"capital": ["Berlin"],

"population": 83491249,

"region": "Europe",

"currencies": {
    "EUR": {
        "symbol": "€",
        "name": "euro"
        }
     },
"languages": {
    "deu": "German"
     }
}
```

### Response Fields
|Field|Type|Description|
|---|---|---|
|`name.common`|String|The commonly used name of the country|
|`name.official`|String|The official legal name of the country|
|`capital`|Array|List of capital cities|
|`population`|Number|Total population count|
|`region`|String|Geographic region, for example Europe or Asia|
|`currencies`|Object|Currency details including symbol and name|
|`languages`|Object|Official language spoken in the country|

## Error Codes
|Status Code|Meaning|Common Causes|
|---|---|---|
|`200`|Success|Request was valid and data was returned|
|`404`|Not Found|Country name not recognized or misspelled|
> **Tip:** If you receive a 404 error, check the spelling of your
> country name. Use the full official name, for example,
> *united kingdom* instead of *england*.