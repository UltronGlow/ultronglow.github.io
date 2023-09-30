---
sidebar_position: 5
---

# Unbundle Reward and Storage Node Address

## Rate Limits

API calls are limited to 4 calls per minute

## Details

| Item            | Description                |
|:----------------|:---------------------------|
| Request         | http POST                  |
| Encoding Format | UTF-8                      |
| RPC             | https://rpc.ultronglow.io/ |

## Parameter Format

```
UTG:1:Unbind:Ple:1
```
Among the parameters, only the storage node address is a variable. Assemble
according to the specific storage node address. The unbinding operation can only
be performed on the reward address.

## Java

```javascript
public void testUnBind() throws Exception {
    String privatekey="a75267d9a92b26eb8802f89b55b7d23e5c49f9576023abd8749433bb1f34d8a3";//Private key of reward address
    String from="UX6737b3c9C69eA389A7Ba14A027a3c393a79a7584";//reward address
    String to="UX6737b3c9C69eA389A7Ba14A027a3c393a79a7584";//reward address
    String dev="uxc3b6D21b5eAa047956206c314a2dDB2685805f98";//storage node address
    String data=Numeric.toHexString(("UTG:1:Unbind:"+dev+":1").getBytes(StandardCharsets.UTF_8));
    sendTrace(privatekey,from,to,data,web3j);//sendTrace
}
```