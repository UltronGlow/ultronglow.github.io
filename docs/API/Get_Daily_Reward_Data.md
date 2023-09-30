---
sidebar_position: 2
---

# Get Daily Reward Data

## Rate Limits

API calls are limited to 4 calls per minute

## Details

| Item            | Description                                                                      |
|:----------------|:---------------------------------------------------------------------------------|
| Request         | http GET/POST                                                                    |
| Encoding Format | UTF-8                                                                            |
| URL             | https://api.ultronscan.io/third/getRewards?address=ux....&datetime=1651334400000 |

## Request URL parameters

```json
address: "ux...", //Reward Address
startblock: 10000, //The starting block of the query
endblock: 20000, //The end block of the query
type: ""/1/2, //Reward type, optional 1: PoSR reward 2: PoTS 3: POS delegation reward Empty: All rewards for the address
```
## JSON response body

```json
{
  "result": {
    "address": "ux...", //Reward Address
    "startblock": 10000, //Statistics start block
    "endblock": 20000, //Statistics end block
    "rewards":[ //Reward list
      {
        "address": "ux...", //Storage node address / PoS node address
        "blocknumber": 3300, //Lock height
        "rewardAmount": 1000000000000, //Total amount of the locked rewards record (including released and burnt amount in the locked position)
        "releaseAmount": 1234000000, //released Amount
        "burntAmount": 0, //burnt Amount
        "lockPeriod": 259200, //lockPeriod
        "releasePeriod": 1555200, //releasePeriod
        "releaseInterval": 8640, //releaseInterval
        "type": 1/2/3, //Reward type, optional 1: PoSR reward 2: PoTS 3: PoS delegation reward
      }
    ]
  },
  "message": "successful",
  "statusCode": 0
}
```

:::note

The request parameter `datetime` is the date and time stamp (milliseconds), and returns the
time stamp `starttime` and `endtime` of the statistical time range.

For example, the time stamp of 2022-05-01 00:00:00 (UTC+8) is 1651334400000.  The returned
statistical time is 2022-04-30 13:00:00 (1651294800000) - 2022-05-01 13:00:00 (1651381200000).

:::
