## Errors  

The General Putnam Motel Diner API follows standard HTTP status codes for success or failure of an API call.  

|Status | Code Description|
| --- | --- |--- |
|200 - Ok|Your meal was successfully ordered|
| 400 - Bad Request | Your order was unacceptable. Most likely, you made unsupported additions to the meal request.|
| 401 - Unauthorized | Your order could not be processed due to an invalid user or password. |
| 402 - Request Failed | Your order could not be processed due to payment failure. |
| 403- Forbidden | The requested meal is not valid due to restrictions of the burger meal options. | 
| 404 - Not Found |  Page not found. |
| 429 - Too Many Requests | The system is unable to process your ofer due to receiving too many requests. | 
