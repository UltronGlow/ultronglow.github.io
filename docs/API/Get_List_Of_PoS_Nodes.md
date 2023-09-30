---
sidebar_position: 8
---

# Get List of PoS Nodes

## Rate Limits

API calls are limited to 4 calls per minute

## Details

| Item            | Description                                 |
|:----------------|:--------------------------------------------|
| Request         | http GET/POST                               |
| Encoding Format | UTF-8                                       |
| URL             | https://api.ultronscan.io/third/getPosNodes |

## JSON response body

```json
{
  "result": {
    "list":[{ //pos node list
      "node_address": "ux...", //pos node address
      "revenue_address": "ux...", //reward address
      "manage_address": "ux...", //admin address
      "node_type": 2, //Node type 1: Pre-candidate node 2: Ultron node
      "pledge_amount": 16099000000000,//pledge amount
      "charge_rate": 100, //rate value percentage value
      "penalty_points": 0, //penalty points
      "active_height": 8400 //active height
    }]
  },
  "message": "successful",
  "statusCode": 0
}
```
:::note

All amounts have 18 digits.  For example, 1000000000000000000, which in this case = 1 UTG.

:::
