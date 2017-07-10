# @datafire/apitore_twitterapis
Call Twitter APIs.<BR />[Endpoint] https://api.apitore.com/api/23

## Operation: myTimelineUsingGET
Get my timeline tweets.<BR />Response<BR />&nbsp; Github: <a href="https://github.com/keigohtr/apitore-response-parent/tree/master/twitter-response">twitter-response</a><BR />&nbsp; Class: com.apitore.banana.response.twitter.TwitterResponseEntity<BR />

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "access_token": {
      "type": "string",
      "description": "Access Token"
    },
    "sinceId": {
      "type": "integer",
      "format": "int64",
      "description": "Get after this id."
    },
    "maxId": {
      "type": "integer",
      "format": "int64",
      "description": "Get before this id."
    },
    "iter": {
      "type": "integer",
      "format": "int32",
      "description": "Numof requests. Return up to 200 x iter tweets."
    }
  },
  "additionalProperties": false,
  "required": [
    "access_token"
  ]
}
```
### Output Schema
```json
{
  "$ref": "#/definitions/TwitterResponseEntity"
}
```
## Operation: myTweetUsingGET
Get my tweets.<BR />Response<BR />&nbsp; Github: <a href="https://github.com/keigohtr/apitore-response-parent/tree/master/twitter-response">twitter-response</a><BR />&nbsp; Class: com.apitore.banana.response.twitter.TwitterResponseEntity<BR />

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "access_token": {
      "type": "string",
      "description": "Access Token"
    },
    "sinceId": {
      "type": "integer",
      "format": "int64",
      "description": "Get after this id."
    },
    "maxId": {
      "type": "integer",
      "format": "int64",
      "description": "Get before this id."
    },
    "iter": {
      "type": "integer",
      "format": "int32",
      "description": "Numof requests. Return up to 200 x iter tweets."
    }
  },
  "additionalProperties": false,
  "required": [
    "access_token"
  ]
}
```
### Output Schema
```json
{
  "$ref": "#/definitions/TwitterResponseEntity"
}
```
## Operation: searchUsingGET
Tweets search API.<BR />Response<BR />&nbsp; Github: <a href="https://github.com/keigohtr/apitore-response-parent/tree/master/twitter-response">twitter-response</a><BR />&nbsp; Class: com.apitore.banana.response.twitter.TwitterResponseEntity<BR />

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "access_token": {
      "type": "string",
      "description": "Access Token"
    },
    "q": {
      "type": "string",
      "description": "Search query"
    },
    "sinceId": {
      "type": "integer",
      "format": "int64",
      "description": "Search after this id."
    },
    "maxId": {
      "type": "integer",
      "format": "int64",
      "description": "Search before this id."
    },
    "iter": {
      "type": "integer",
      "format": "int32",
      "description": "Numof search requests. Return up to 100 x iter tweets."
    }
  },
  "additionalProperties": false,
  "required": [
    "access_token",
    "q"
  ]
}
```
### Output Schema
```json
{
  "$ref": "#/definitions/TwitterResponseEntity"
}
```