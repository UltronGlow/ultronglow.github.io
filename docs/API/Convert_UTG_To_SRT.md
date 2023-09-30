---
sidebar_position: 7
---

# Convert UTG to SRT

## Rate Limits

API calls are limited to 4 calls per minute

## Details

| Item            | Description                |
|:----------------|:---------------------------|
| Request         | http POST                  |
| Encoding Format | UTF-8                      |
| RPC             | https://rpc.ultronglow.io/ |

## Parameter Format

Every conversion of SRT needs to initiate a transaction.  The transaction data parameter is UTG:1:Exch:SRT
receiving address: convert quantity.  See the below as an example:

```
ux7a4539ed8a0b8b4583ead1e5a3f604e83419f502 convert 10 SRT for ux7a4539ed8a0b8b4583ead1e5a3f604e83419f502
```

## Java

```javascript
String privatekey="64b87ff4dfe358dfbf54d9eeec538d8ea9e7e96b3d77cc48a7b441fced793be7";
String from="ux7a4539ed8a0b8b4583ead1e5a3f604e83419f502";
String to="ux7a4539ed8a0b8b4583ead1e5a3f604e83419f502";
BigInteger num=new BigInteger("10");//10 SRT
num=num.multiply(new BigInteger("10").pow(18));
String srtdev="ux7a4539ed8a0b8b4583ead1e5a3f604e83419f502";
String data=Numeric.toHexString(("UTG:1:Exch:"+srtdev+":"+num.toString(16)).getBytes(StandardCharsets.UTF_8));
sendTrace(privatekey,from,to,data,null,web3j);
```