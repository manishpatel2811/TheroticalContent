# A Introduction to Web services

## What is web services ?

```
software system designed to support interoperable machine-to-machine interaction over a network.
```

Three keys to build of web service 
• Designed for machine to machine ( or application to application ) interaction.
• should be interoperable. - not platform dependent.
• Should allow communication over a network.

## How does data exchange between application take place?

```
Data exchange takes place between application and web service in form of request(input to web service to app) and response(output from web service to app).
```

## How can we make web services  platform independent?

``` 
If a data exchange format is language independent then it's being a problem while communicating with different platform application. So there should be standard format used which is accepted by any platforms.
Standardized format are 
1. XML  - extensible markup language
2. JSON  javascript object notation

request and response follows either xml or json.
```
## How does the application A know the format of request and response? ( how does it know what request to send , where to send it , and what is the format of the response ? )

```
Every  web service provides the service definition. Service definition consist of Request & response structure , request & response format and endpoint. 
```
## Terminology used in web services

```
1. Request - Input to web service.
2. Response - Output from web service.
3. Message exchange format - XML , JSON
4. Service Provider - The one who is providing the service.
5. Service consumer - The one who is using the service provided by a service provider. 
6. Service Definition - It consist of Request & response structure , request & response format and endpoint. 
7. Transport - HTTP/Message queuing system.
```
##  WEB SERVICE GROUPS 

```
## It defines end point , all operation allowed , request and response strucuture.

There are two kinds of web service providing group 
1. SOAP (Simple Object access protocol) based

* Format used in request and response is xml based structure which contain a SOAP envolepe. SOAP envelope consist of header and body.
* Transort used - Either Queue or http.
* Service defintion - [ WSDL web serice defintion language ].

2. REST (Representational state transfer) based

* Format used in request and response - JSON , XML , HTML
* Interaction happens over http  [Transport].
* Http method used - POST , PUT , GET , DELETE
* Service Definition - WADL , Swagger
```
## key abstraction 

```
resource - It is anything  you would like to expose to outside world.

A resource has an URI ( Uniform resource identifier)
/getallbooks
/getbookbyid/1
/addbook

A resource can have different representations = XML ,  HTML , JSON

The thing that matter is you can use the resource by using whatever facilities that are provided by http. " POST , GET , PUT , DELETE , FETCH " ,  
```
