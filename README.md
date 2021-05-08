# API Spec

## Authentication

All API must use this authentication

Request :

- Header
  - API-Key : "your secret api key"

## Get Traffic Light List

Request :

- Method : GET
- Endpoint : `/api/traffics`
- Header
  - Content-Type : applicatication/json
  - Accept: application/json
- Query Params :
  - radius: <"radius in number">

Response :

```json
{
  "status": "string",
  "message": "string",
  "data": [
    {
      "id": "number, unique",
      "name": "string",
      "address": "string"
    }
  ]
}
```

## Get Traffic Light Details

Request :

- Method : GET
- Endpoint : `/api/traffics/{traffic_light_id}`
- Header
  - Accept: application/json

Response :

```json
{
  "status": "string",
  "message": "string",
  "data": {
    "id": "number, unique",
    "name": "string",
    "address": "string",
    "vehiclesDensityInMinutes": "number",
    "intersections": [
      {
        "name": "string",
        "waitingTimeInSeconds": "number",
        "currentStatus": "enum(RED, YELLOW, GREEN)"
      }
    ]
  }
}
```
