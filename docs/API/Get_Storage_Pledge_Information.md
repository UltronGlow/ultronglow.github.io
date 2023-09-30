---
sidebar_position: 1
---

# Get Storage Pledge Information

## Rate Limits

API calls are limited to 4 calls per minute

## Details

| Item            | Description                                            |
|:----------------|:-------------------------------------------------------|
| Request         | http GET/POST                                          |
| Encoding Format | UTF-8                                                  |
| URL             | https://api.ultronscan.io/third/getRevenue?address=ux  |

## Request URL parameters

```json
address: "ux...",          //Reward Address
```

## JSON response body

```json
{
  "result": {
    "address": "ux...", //Reward Address
    "stratio": 0.8, //Storage Factor
    "storages":[ //Storage List
      {
        "address": "ux...", //Storage node address
        "blocknumber": 1000, //Pledge height
        "capacity": 10995116277800, //Storage capacity (unit: B)
        "bandwidth": 1024, //Upload bandwidth
        "bwratio": 1.5, //Bandwidth reward factor
        "pledgeStatus": 0, //Pledge status 0: normal 1:abnormal
        "vaildNumber": 1000, //Storage the last verified height
        "succNumber": 1000, //Storage the height of the last authentication success
        "pledgeAmount": 30000000000000, //pledgeAmount
        "leases":[ //leases list
            {
                "hash": "ux...", //rent hash
                "address": "ux...", //rental address
                "blocknumber": 2000, //Rental pledge height
                "leaseStatus": 1, //leaseStatus 0: normal 1: abnormal
                "capacity": 1100585369600, //Storage capacity (unit: B)
                "price": 1000000000000000, //rental price
                "duration": 30, //rental duration (unit: day)
                "vaildNumber": 1000, //Lease Last Verified Altitude
                "succNumber": 1000, //Height of the last successful authentication of the lease
                "pledgeAmount": 30000000000000, //pledgeAmount
            }
        ]
      }
    ]
  },
  "message": "successful",
  "statusCode": 0
}
```
:::note

All amounts have 18 digits.  For example, 1000000000000000000, which in this case = 1 UTG.

:::


