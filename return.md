# Return codes for Coins
Return info consist of three parts: an system error code, a system message and business info. Business info consist of three parts:an business error code, a business message and data. Codes are universal,
 but messages can vary. Here is the return JSON payload:
```javascript
{
 "sysCd":"00000000",
         "sysMsg":"OK"
 "biz":{
  "bizCd":"00000000", "bizMsg":"OK", "data":{
   "serverTime": 1499827319559
  }
 }
}
```
The format for the successful system return code is 00000000. The composition rule for unsuccessful system return codes is a 4-digit assignor+system code (variable digits).Among them, the encoding values of the three assigned values are as follows:
#### assignor
| assignor             | code |
|----------------------|------|
| Platform             | ES00 |
| Payment institutions | IS09 |

#### system return code(this is only an example, not all of them. Please add code whenever you need it)
| return code          | explain |
|----------------------|---------|
| ES001001             | Internal error; unable to process your request. Please try again.     |
| ES001002             | You are not authorized to execute this request. |

The format for the successful business return code is 00000000. The composition rule for unsuccessful business return codes is a 4-digit assignor+system code (variable digits).Among them, the encoding values of the three assigned values are as follows:
#### assignor
| assignor             | code |
|----------------------|------|
| Platform             | EB00 |
| Payment institutions | IB09 |

#### business return code(this is only an example, not all of them. Please add code whenever you need it)
| return code | explain |
|-------------|---------|
| EB001001    | Insufficient balance  |
| EB001002    | Affected by risk control|
