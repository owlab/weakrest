# WeakRestClient
## A simple RESTful client with minimum dependencies
  
This utility is based on Apache Http Client and Jackson Json libraries, but older versions of those, intentionally. 

### Usuage example:
#### For GET
```
 WeakRestClient.RestRespone respone = WeakRestClient.get(<URL>) // also delete for DELETE method
                                          .setConnectionTimeout(10000) // millis
                                          .setSocketTimeout(10000) // millis
                                          .basicAuth("auth user id", "auth password")
                                          .queryString("paramName", "paramValue")
                                          .execute();
```
#### For POST
```
WeakRestClient.RestRespone respone = WeakRestClient.post(<URL>) // also put for PUT method
                                          .setConnectionTimeout(10000) // millis
                                          .setSocketTimeout(10000) // millis
                                          .header("content-type", "application/json")
                                          .basicAuth("auth user id", "auth password")
                                          .bodyAsJsonNode(<a JsonNode object>) // or .body(String)
                                          .execute();
```
#### Use of Response
* response.statueCode => HTTP STATUS CODE
* response.responseBody => String
* response.asJsonNode() => return JsonNode object of the body string
