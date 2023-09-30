---
sidebar_position: 6
---

# Get Absent

## Rate Limits

API calls are limited to 4 calls per minute

## Details

| Item            | Description                                         |
|:----------------|:----------------------------------------------------|
| Request         | http POST                                           |
| Encoding Format | UTF-8                                               |
| URL             | https://api.ultronscan.io/platform/utg/getPunished  |

## Request URL parameters

```json
{
  "current": 1, //Current page number
  "size": 10, //Articles per page
  "address": "ux...", //absentee address
  "blockNumber": 100, //absentee height
}
```
## JSON response body

```json
{
  "result": {
    "records": [
      {
        "address": "ux...", //absentee address
        "blockNumber": 68381, //absentee height
        "fractions": 30, //penalty points
        "timeStamp": "2022-06-17 09:14:23" //time
      }
    ],
    "total": 13, //total number of absences
    "size": 10, //Articles per page
    "current": 1, //Current page number
    "pages": 2 //total pages
  },
  "message": "successful",
  "statusCode": 0
}
```