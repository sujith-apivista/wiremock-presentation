# Service Virtualization for Microservices Development

## An Example Microservices Architecture 

## Challenges of developing and testing microservices 
  * Modifying state 
  * Independent development
  * Integration testing – Availability, Version 
  * Latency 
  * Rate limits 
  * Usage fees 
  * Deterministic responses 
  * Edge cases 
  * Error scenarios – Timeouts, 503 etc 

## Potential solutions 
  * Mocking frameworks – Mockito, Sinon 
  * Run images in a cluster 
  * Stubs – WireMock, Mountebank 

## WireMock 

### Overview 
  * Official site: https://www.wiremock.org
  * GitHub: https://github.com/tomakehurst/wiremock
  * Usage as a standalone component
    * Download JAR
        * Run: `java -jar wiremock-jre8-standalone-2.27.2.jar`
        * Command line options: `--port`, `--https-port`, `--verbose` and many more
        * Access: http://localhost:8080/__admin
    * Docker: https://github.com/rodolpheche/wiremock-docker

### Stubbing
  * Using the API
    * Specs: http://wiremock.org/docs/api/
    * [Examples](Stub-with-API.md)
  * Using flat files
    * [Examples](Stub-with-Files.md)

### Request Matching

### Response Templating

### Recording & playback 

 

### JUnit Integration 