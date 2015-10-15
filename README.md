# weakrest
 A simple RESTful client for Activiti REST API
 {Sample Text}
 Use with your own risks!
  
 This utility is based on only Apache Http Client and Jackson Json libraries included in BXM.
 
 @author Nemo Hunjae Lee
 
 Usuage example:
 WeakRestClient.RestRespone respone = WeakRestClient.get(<URL>) // also delete for DELETE method
                                          .setConnectionTimeout(10000) // millis
                                          .setSocketTimeout(10000) // millis
                                          .basicAuth("auth user id", "auth password")
                                          .queryString("paramName", "paramValue")
                                          .execute();
WeakRestClient.RestRespone respone = WeakRestClient.post(<URL>) // also put for PUT method
                                         .setConnectionTimeout(10000) // millis
                                          .setSocketTimeout(10000) // millis
                                          .header("content-type", "application/json")
                                          .basicAuth("auth user id", "auth password")
                                          .bodyAsJsonNode(< a JsonNode object>) // or .body(String)
                                          .execute();
 response.statueCode => HTTP STATUS CODE
 response.responseBody => String
 response.asJsonNode() => return JsonNode object of the body string
