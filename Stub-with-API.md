# Stubbing with API

## Example 1
A simple stub:

`curl -v -X POST -d '{
  "request": {
    "method": "GET",
    "url": "/introduction"
  },
  "response": {
    "body": "Hello world!",
    "headers": {
      "Content-Type": "text/plain"
    },
    "status": 200
  }
}'
http://localhost:8080/__admin/mappings`

`curl -i http://localhost:8080/introduction`

## Example 2
Stub with JSON response:

`curl -v -X POST -d '{
  "request": {
    "method": "GET",
    "url": "/meaning/everything"
  },
  "response": {
    "jsonBody": {
        "answer": 42
    },
    "headers": {
      "Content-Type": "application/json"
    },
    "status": 200
  }
}'
http://localhost:8080/__admin/mappings`

`curl -i http://localhost:8080/meaning/everything`

## Example 3
Get all stubs:

`curl http://localhost:8080/__admin/mappings`

## Managing stubs
Admin API has other methods - GET by id, PUT, DELETE (all).

## Example 4
All stubs are lost when WireMock is shut down. To save stubs:

`curl -v -X POST http://localhost:8080/__admin/mappings/save`

The stubs are saved as files in the `mappings` folder.