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