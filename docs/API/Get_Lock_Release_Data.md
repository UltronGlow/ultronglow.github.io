---
sidebar_position: 4
---

# Get Lock Release Data

## Rate Limits

API calls are limited to 4 calls per minute

## Details

| Item            | Description                                               |
|:----------------|:----------------------------------------------------------|
| Request         | http GET/POST                                             |
| Encoding Format | UTF-8                                                     |
| URL             | https://api.ultronscan.io/third/getReleases?address=ux... |

## Request URL parameters

```json
address: "ux...", //reward address
type: ""/1/2, //Reward type, optional 1: PoSR reward 2: PoTS 3: POS delegation reward Empty: All rewards for the address
```
## JSON response body

```json
{
  "result": {
    "address": "ux...", //reward address
    "releases":[ //release list
      {
        "address": "ux...", //Storage node address / POS node address
        "releaseAmount": 1000000000000, //Total released amount (including burnt)
        "burntAmount": 0, //Total burnt Amount
        "type": 1/2/3, //Reward type, optional 1: PoSR reward 2: PoTS 3: POS delegation reward
      }
    ]
  },
  "message": "successful",
  "statusCode": 0
}
```