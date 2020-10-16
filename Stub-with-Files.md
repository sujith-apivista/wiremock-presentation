# Stubbing with Files

## Example 1

Add a JSON file to the `mappings` folder.

```
{
  "id" : "170579e2-a0c8-45da-ad25-aa6ce092cf04",
  "request" : {
    "url" : "/seltzers",
    "method" : "GET"
  },
  "response" : {
    "status" : 200,
    "jsonBody" : {
      "flavors" : ["cranberry lime", "raspberry", "mandarin orange", "blackberry citrus"]
    },
    "headers" : {
      "Content-Type" : "application/json"
    }
  },
  "uuid" : "170579e2-a0c8-45da-ad25-aa6ce092cf04",
  "persistent" : true,
  "insertionIndex" : 2
}
```

Restart WireMock and test stub:
`curl -i http://localhost:8080/seltzers`

## Example 2

If the response body is large/complex, it can be sourced from a separate file in the `__files` folder.

File for the response body:
```
[{"used":false,"source":"user","type":"cat","deleted":false,"_id":"5b4909af0508220014ccfe8a","updatedAt":"2020-08-23T20:20:01.611Z","createdAt":"2018-07-24T20:20:01.874Z","user":"5a9ac18c7478810ea6c06381","text":"Cats have a layer called the tapetum lucidum just behind their retina which reflects light inside the eye, helping it capture more light. This reflected light is the glow you see when taking a photo of a cat with the flash on.","__v":0,"status":{"verified":true,"sentCount":1}},{"used":false,"source":"user","type":"cat","deleted":false,"_id":"5d38b5b50f1c57001592f131","user":"5a9ac18c7478810ea6c06381","text":"Andy Warhol amassed quite the collection of feline friends during his lifetime, beginning with a Siamese cat named Hester that was given to him by actress Gloria Swanson. By breeding Hester with a cat named Sam, Warhol ended up with multiple litters of kittens, at one point housing 25 cats in his Upper East Side townhouse in NYC.","createdAt":"2019-07-24T19:47:01.970Z","updatedAt":"2020-08-23T20:20:01.611Z","__v":0,"status":{"verified":true,"sentCount":1}},{"used":false,"source":"api","type":"cat","deleted":false,"_id":"591f98783b90f7150a19c1dc","__v":0,"text":"A domestic cat can run at speeds of 30 mph.","updatedAt":"2020-08-23T20:20:01.611Z","createdAt":"2018-01-04T01:10:54.673Z","status":{"verified":true,"sentCount":1},"user":"5a9ac18c7478810ea6c06381"},{"used":false,"source":"user","type":"cat","deleted":false,"_id":"5a4d75e46ef087002174c284","updatedAt":"2020-08-23T20:20:01.611Z","createdAt":"2018-04-05T20:20:05.171Z","user":"5a9ac18c7478810ea6c06381","text":"Cats have about 130,000 hairs per square inch (20,155 hairs per square centimeter).","__v":0,"status":{"verified":true,"sentCount":1}},{"used":false,"source":"api","type":"cat","deleted":false,"_id":"591f9890d369931519ce3552","__v":0,"text":"A steady diet of dog food may cause blindness in your cat - it lacks taurine.","updatedAt":"2020-08-23T20:20:01.611Z","createdAt":"2018-01-04T01:10:54.673Z","status":{"verified":true,"sentCount":1},"user":"5a9ac18c7478810ea6c06381"}]
```

File for the stub:
```
{
  "id" : "8FBE453F-7A60-4F8A-9542-120EAF8B8CB2",
  "request" : {
    "url" : "/cats/facts",
    "method" : "GET"
  },
  "response" : {
    "status" : 200,
    "bodyFileName" : "cat-facts-response.json",
    "headers" : {
      "Content-Type" : "application/json"
    }
  },
  "uuid" : "8FBE453F-7A60-4F8A-9542-120EAF8B8CB2",
  "persistent" : true,
  "insertionIndex" : 3
}
```

Restart WireMock and test stub:
`curl -i http://localhost:8080/cats/facts`

This response body can be passed in as a file through the API as well.

## Recommendation
It is better to avoid creating files from the scratch as elements like the ID and metadata can get out of sync. Instead, use the API to create placeholder stubs and then edit the files.