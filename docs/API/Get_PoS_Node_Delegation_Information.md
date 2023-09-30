---
sidebar_position: 9
---

# Get PoS Node Delegation Information

## Rate Limits

API calls are limited to 4 calls per minute

## Details

| Item            | Description                                                    |
|:----------------|:---------------------------------------------------------------|
| Request         | http GET/POST                                                  |
| Encoding Format | UTF-8                                                          |
| URL             | https://api.ultronscan.io/third/getPosNodePledge?address=ux... |

## Request URL parameters

```json
address: "ux..."
```

## JSON response body

```json
{
  "result": {
    "node_address": "ux...", //pos node address
    "revenue_address": "ux...", //reward address
    "manage_address": "ux...", //admin address
    "node_type": 2, //Node type 1: Pre-candidate node 2: Ultron node
    "pledge_amount": 1600000000000000, //pledge amount
    "charge_rate": 100, //rate value percentage value
    "penalty_points": 0, //penalty points
    "active_height": 8400, //active height
    "pledge_list": [{ //pledge list
      "pledge_address": "ux...", //Pledge Address
      "pledge_hash": "ux...", //Pledge Hash
      "pledge_status": 1, //Pledge Status 1-Staking 0-Staking Exit
      "pledge_amount": 160000000000000, //pledge amount
      "pledge_number": 17382, //pledge height
      "unpledge_hash": null, //unpledge hash
      "unpledge_number": null //unpledge number
    }]
  },
  "message": "successful",
  "statusCode": 0
}
```
:::note

All amounts have 18 digits.  For example, 1000000000000000000, which in this case = 1 UTG.

:::
