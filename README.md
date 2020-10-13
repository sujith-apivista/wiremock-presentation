# Service Virtualization for Microservices Development

## A Typical Microservices Architecture 

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
  * Download JAR and run: `java -jar wiremock-jre8-standalone-2.27.2.jar`
  * Command line options: `--port`, `--https-port`, `--verbose`
  * Access: http://localhost:8080/__admin
  * Docker: https://github.com/rodolpheche/wiremock-docker

### Recording & playback 

 

### JUnit Integration 