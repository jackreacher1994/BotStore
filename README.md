# BotStore API Spec

## Overview

### The API can now be accessed at:

    http://45.32.117.24/api


### Request Headers:

| **Required** 	| **Key**              	| **Value**            	|
|----------	|------------------	|------------------	|
| Yes      	| Content-Type     	| application/json 	|
| Yes      	| X-Requested-With 	| XMLHttpRequest   	|
| Optional 	| Authorization    	| Token {JWT}      	|


### JSON Objects returned by API:

Make sure the right content type like `Content-Type: application/json; charset=utf-8` is correctly returned.


### Successes and Status Codes:

200 for Successful requests. The actual response will depend on the request method used. In a GET request, the response will contain an entity corresponding to the requested resource. In a POST request, the response will contain an entity describing or containing the result of the action.

201 for Fulfilled requests, resulting in the creation of a new resource. Example: registering user done and wait for account activation.

202 for the request has been accepted for processing, but the processing has not been completed. Example: login but user account has not been activated.

204 for No content requests. The server successfully processed the request and is not returning any content.


### Errors and Status Codes:

If a request fails any validations, expect a 422 and errors in the following format:

```JSON
{
  "errors":{
    "body": [
      "can't be empty"
    ]
  }
}
```

Other status codes:

401 for Unauthorized requests, when a request requires authentication but it isn't provided.

403 for Forbidden requests, when a request may be valid but the user doesn't have permissions to perform the action.

404 for Not found requests, when a resource can't be found to fulfill the request.

500 for Internal unknown server error. A generic error message, given when an unexpected condition was encountered and no more specific message is suitable.

## JSON Objects

### Message

```JSON
{
  "message": "You need to confirm your account. We sent you an activation request, please check your email inbox.",
}
```


### Users (for authentication)

```JSON
{
  "user": {
    "email": "jack@gmail.com",
    "token": "jwt.token.here",
  }
}
```


### Profile

```JSON
{
  "profile": {
    "username": "jack",
    "bio": "I work at statefarm",
    "image": "https://static.productionready.io/images/smiley-cyrus.jpg",
    "header": "https://static.productionready.io/images/smiley-cyrus.jpg",
    "name": "Jack Reacher",
    "website": "https://static.productionready.io",
    "twitter": "https://twitter.com/realdonaldtrump",
    "facebook": "https://www.facebook.com/POTUS",
    "following": false
  }
}
```


### Single bot

```JSON
{
  "bot": {
    "slug": "growth-bot",
    "name" : "Growth Bot",
    "title": "A chatbot to organize your visit to Tangier",
    "body": "Organize your circuit in the city of Tangier by the number of days you’re staying and rest assured about what you’re going to visit and how far is it from where you are or will be.",
    "views" : 97090,
    "image" : "https://static.productionready.io/images/smiley-cyrus.jpg",
    "url" : "https://botlist.co/bots/coin-prices-watcher",
    "categoryList": [
      {
        "slug" => "traveling",
        "name" => "Traveling", 
      },
      {
        "slug" => "life",
        "name => "Life"
      }
    ],
    "createdAt": "2016-02-18T03:22:56.637Z",
    "updatedAt": "2016-02-18T03:48:35.824Z",
    "liked": false,
    "likesCount": 1500,
    "voted": false,
    "votedStar": null,
    "votesCount": 1000,
    "averageStar": 4,
    "author": {
      "username": "Jack",
      "bio": "I work at statefarm",
      "image": "https://i.stack.imgur.com/xHWG8.jpg",
      "header": "https://static.productionready.io/images/smiley-cyrus.jpg",
      "name": "Jack Reacher",
      "website": "https://static.productionready.io",
      "twitter": "https://twitter.com/realdonaldtrump",
      "facebook": "https://www.facebook.com/POTUS",
      "following": false
    }
  }
}
```


### Multiple Bots

```JSON
{
  "bots":[{
    "slug": "growth-bot",
    "name" : "Growth Bot",
    "title": "A chatbot to organize your visit to Tangier",
    "body": "Organize your circuit in the city of Tangier by the number of days you’re staying and rest assured about what you’re going to visit and how far is it from where you are or will be.",
    "views" : 97090,
    "image" : "https://static.productionready.io/images/smiley-cyrus.jpg",
    "url" : "https://botlist.co/bots/coin-prices-watcher",
    "categoryList": [
      {
        "slug" => "traveling",
        "name" => "Traveling", 
      },
      {
        "slug" => "life",
        "name => "Life"
      }
    ],
    "createdAt": "2016-02-18T03:22:56.637Z",
    "updatedAt": "2016-02-18T03:48:35.824Z",
    "liked": false,
    "likesCount": 1500,
    "voted": false,
    "votedStar": null,
    "votesCount": 1000,
    "averageStar": 4,
    "author": {
      "username": "Jack",
      "bio": "I work at statefarm",
      "image": "https://i.stack.imgur.com/xHWG8.jpg",
      "header": "https://static.productionready.io/images/smiley-cyrus.jpg",
      "name": "Jack Reacher",
      "website": "https://static.productionready.io",
      "twitter": "https://twitter.com/realdonaldtrump",
      "facebook": "https://www.facebook.com/POTUS",
      "following": false
    }
  }, {
    "slug": "votum",
    "name" : "Votum",
    "title": "Polls and crowdsourcing for your Slack team",
    "body": "Votum enables you to:
            - Run quick polls
            - Collect questions for all hands/town hall/AMA meetings
            - Collect and prioritize meeting topics
            - Prepare retrospective agendas in advance
            - Collect ideas and run idea tournaments with your team",
    "views" : 4646,
    "image" : "https://static.productionready.io/images/smiley-cyrus.jpg",
    "url" : "https://botlist.co/bots/coin-prices-watcher",
    "categoryList": [
      {
        "slug" => "traveling",
        "name" => "Traveling", 
      },
      {
        "slug" => "life",
        "name => "Life"
      }
    ],
    "createdAt": "2016-02-18T03:22:56.637Z",
    "updatedAt": "2016-02-18T03:48:35.824Z",
    "liked": false,
    "likesCount": 4646,
    "voted": true,
    "votedStar": 3,
    "votesCount": 44564,
    "averageStar": 5,
    "author": {
      "username": "Jack",
      "bio": "I work at statefarm",
      "image": "https://i.stack.imgur.com/xHWG8.jpg",
      "header": "https://static.productionready.io/images/smiley-cyrus.jpg",
      "name": "Jack Reacher",
      "website": "https://static.productionready.io",
      "twitter": "https://twitter.com/realdonaldtrump",
      "facebook": "https://www.facebook.com/POTUS",
      "following": false
    }
  }],
  "botsCount": 2
}
```


### Single Review

```JSON
{
  "review": {
    "id": 1,
    "createdAt": "2016-02-18T03:22:56.637Z",
    "updatedAt": "2016-02-18T03:22:56.637Z",
    "body": "Either you are a teenager looking for help and support or a young woman trying to understand how your body changes, Lea can help you. Please notice Lea only talks french for now!",
    "author": {
      "username": "Jack",
      "bio": "I work at statefarm",
      "image": "https://i.stack.imgur.com/xHWG8.jpg",
      "header": "https://static.productionready.io/images/smiley-cyrus.jpg",
      "name": "Jack Reacher",
      "website": "https://static.productionready.io",
      "twitter": "https://twitter.com/realdonaldtrump",
      "facebook": "https://www.facebook.com/POTUS",
      "following": false
    }
  }
}
```


### Multiple Reviews

```JSON
{
  "reviews": [{
    "id": 1,
    "createdAt": "2016-02-18T03:22:56.637Z",
    "updatedAt": "2016-02-18T03:22:56.637Z",
    "body": "Either you are a teenager looking for help and support or a young woman trying to understand how your body changes, Lea can help you. Please notice Lea only talks french for now!",
    "author": {
      "username": "Jack",
      "bio": "I work at statefarm",
      "image": "https://i.stack.imgur.com/xHWG8.jpg",
      "header": "https://static.productionready.io/images/smiley-cyrus.jpg",
      "name": "Jack Reacher",
      "website": "https://static.productionready.io",
      "twitter": "https://twitter.com/realdonaldtrump",
      "facebook": "https://www.facebook.com/POTUS",
      "following": false
    }
  }, {
    "id": 2,
    "createdAt": "2016-02-18T03:22:56.637Z",
    "updatedAt": "2016-02-18T03:22:56.637Z",
    "body": "Either you are a teenager looking for help and support or a young woman trying to understand how your body changes, Lea can help you. Please notice Lea only talks french for now!",
    "author": {
      "username": "Jack",
      "bio": "I work at statefarm",
      "image": "https://i.stack.imgur.com/xHWG8.jpg",
      "header": "https://static.productionready.io/images/smiley-cyrus.jpg",
      "name": "Jack Reacher",
      "website": "https://static.productionready.io",
      "twitter": "https://twitter.com/realdonaldtrump",
      "facebook": "https://www.facebook.com/POTUS",
      "following": false
    }
  }]
}
```


### List of Categories

```JSON
{
  "categories": [
    {
      "slug":"qui-voluptas",
      "name":"Qui & Voluptas"
    },
    {
      "slug":"maxime",
      "name":"Maxime"
    }
  ]
}
```


### Single collection

```JSON
{
  "collection": {
    "slug": "growth-collection",
    "name" : "Growth Collection",
    "description": "Itaque omnis tempora saepe vel rem alias.",
    "header" : "https://static.productionready.io/images/smiley-cyrus.jpg",
    "botList": [
    	{
    		"slug": "growth-bot",
    		"name" : "Growth Bot",
    		"title": "A chatbot to organize your visit to Tangier",
    		"body": "Organize your circuit in the city of Tangier by the number of days you’re staying and rest assured about what you’re going to visit and how far is it from where you are or will be.",
    		"views" : 97090,
    		"image" : "https://static.productionready.io/images/smiley-cyrus.jpg",
    		"url" : "https://botlist.co/bots/coin-prices-watcher",
        "liked" : false,
        "likesCount" : 5566,
        "voted": false,
        "votedStar": null,
        "votesCount": 1000,
        "averageStar": 4,
        "createdAt": "2016-02-18T03:22:56.637Z",
    		"updatedAt": "2016-02-18T03:48:35.824Z",
    		"categoryList": [
          {
            "slug" => "traveling",
            "name" => "Traveling", 
          },
          {
            "slug" => "life",
             "name => "Life"
          }
        ],
    		"author": {
      			"username": "Jack",
      			"bio": "I work at statefarm",
      			"image": "https://i.stack.imgur.com/xHWG8.jpg",
      			"header": "https://static.productionready.io/images/smiley-cyrus.jpg",
      			"name": "Jack Reacher",
      			"website": "https://static.productionready.io",
      			"twitter": "https://twitter.com/realdonaldtrump",
      			"facebook": "https://www.facebook.com/POTUS",
      			"following": false
    		}
    	}, 
        {
    		"slug": "votum",
    		"name" : "Votum",
    		"title": "Polls and crowdsourcing for your Slack team",
    		"body": "Votum enables you to:
            	- Run quick polls
            	- Collect questions for all hands/town hall/AMA meetings
            	- Collect and prioritize meeting topics
            	- Prepare retrospective agendas in advance
            	- Collect ideas and run idea tournaments with your team",
    		"views" : 4646,
    		"image" : "https://static.productionready.io/images/smiley-cyrus.jpg",
    		"url" : "https://botlist.co/bots/coin-prices-watcher",
        "liked" : true
        "likesCount" : 8998,
        "voted": false,
        "votedStar": null,
        "votesCount": 4700,
        "averageStar": 3,
        "createdAt": "2016-02-18T03:22:56.637Z",
    		"updatedAt": "2016-02-18T03:48:35.824Z",
    		"categoryList": [
          {
            "slug" => "traveling",
            "name" => "Traveling", 
          },
          {
            "slug" => "life",
            "name => "Life"
          }
        ],
    		"author": {
      			"username": "Jack",
      			"bio": "I work at statefarm",
      			"image": "https://i.stack.imgur.com/xHWG8.jpg",
      			"header": "https://static.productionready.io/images/smiley-cyrus.jpg",
      			"name": "Jack Reacher",
      			"website": "https://static.productionready.io",
      			"twitter": "https://twitter.com/realdonaldtrump",
      			"facebook": "https://www.facebook.com/POTUS",
      			"following": false
    		}
  		}
    ],
    "createdAt": "2016-02-18T03:22:56.637Z",
    "updatedAt": "2016-02-18T03:48:35.824Z",
    "author": {
      "username": "Jack",
      "bio": "I work at statefarm",
      "image": "https://i.stack.imgur.com/xHWG8.jpg",
      "header": "https://static.productionready.io/images/smiley-cyrus.jpg",
      "name": "Jack Reacher",
      "website": "https://static.productionready.io",
      "twitter": "https://twitter.com/realdonaldtrump",
      "facebook": "https://www.facebook.com/POTUS",
      "following": false
    }
  }
}
```

### Multiple Collections

```JSON
{
  "collections":[{
    "slug": "growth-collection",
    "name" : "Growth Collection",
    "description": "Itaque omnis tempora saepe vel rem alias.",
    "header" : "https://static.productionready.io/images/smiley-cyrus.jpg",
    "botList": [
    	{
    		"slug": "growth-bot",
    		"name" : "Growth Bot",
    		"title": "A chatbot to organize your visit to Tangier",
    		"body": "Organize your circuit in the city of Tangier by the number of days you’re staying and rest assured about what you’re going to visit and how far is it from where you are or will be.",
    		"views" : 97090,
    		"image" : "https://static.productionready.io/images/smiley-cyrus.jpg",
    		"url" : "https://botlist.co/bots/coin-prices-watcher",
        "liked" : true,
        "likesCount" : 8998,
        "voted": false,
        "votedStar": null,
        "votesCount": 1000,
        "averageStar": 4,
        "createdAt": "2016-02-18T03:22:56.637Z",
    		"updatedAt": "2016-02-18T03:48:35.824Z",
    		"categoryList": [
          {
            "slug" => "traveling",
             "name" => "Traveling", 
          },
          {
            "slug" => "life",
            "name => "Life"
          }
        ],
    		"author": {
      			"username": "Jack",
      			"bio": "I work at statefarm",
      			"image": "https://i.stack.imgur.com/xHWG8.jpg",
      			"header": "https://static.productionready.io/images/smiley-cyrus.jpg",
      			"name": "Jack Reacher",
      			"website": "https://static.productionready.io",
      			"twitter": "https://twitter.com/realdonaldtrump",
      			"facebook": "https://www.facebook.com/POTUS",
      			"following": false
    		}
    	}, 
        {
    		"slug": "votum",
    		"name" : "Votum",
    		"title": "Polls and crowdsourcing for your Slack team",
    		"body": "Votum enables you to:
            	- Run quick polls
            	- Collect questions for all hands/town hall/AMA meetings
            	- Collect and prioritize meeting topics
            	- Prepare retrospective agendas in advance
            	- Collect ideas and run idea tournaments with your team",
    		"views" : 4646,
    		"image" : "https://static.productionready.io/images/smiley-cyrus.jpg",
    		"url" : "https://botlist.co/bots/coin-prices-watcher",
        "liked" : true,
        "likesCount" : 8998,
        "voted": false,
        "votedStar": null,
        "votesCount": 1000,
        "averageStar": 4,
        "createdAt": "2016-02-18T03:22:56.637Z",
    		"updatedAt": "2016-02-18T03:48:35.824Z",
    		"categoryList": [
          {
            "slug" => "traveling",
             "name" => "Traveling", 
          },
          {
            "slug" => "life",
            "name => "Life"
          }
        ],
    		"author": {
      			"username": "Jack",
      			"bio": "I work at statefarm",
      			"image": "https://i.stack.imgur.com/xHWG8.jpg",
      			"header": "https://static.productionready.io/images/smiley-cyrus.jpg",
      			"name": "Jack Reacher",
      			"website": "https://static.productionready.io",
      			"twitter": "https://twitter.com/realdonaldtrump",
      			"facebook": "https://www.facebook.com/POTUS",
      			"following": false
    		}
  		}
    ],
    "createdAt": "2016-02-18T03:22:56.637Z",
    "updatedAt": "2016-02-18T03:48:35.824Z",
    "author": {
      "username": "Jack",
      "bio": "I work at statefarm",
      "image": "https://i.stack.imgur.com/xHWG8.jpg",
      "header": "https://static.productionready.io/images/smiley-cyrus.jpg",
      "name": "Jack Reacher",
      "website": "https://static.productionready.io",
      "twitter": "https://twitter.com/realdonaldtrump",
      "facebook": "https://www.facebook.com/POTUS",
      "following": false
    }
  }, {
    "slug": "mr-conrad-senger",
    "name" : "Mr Conrad Senger",
    "description": "Itaque omnis tempora saepe vel rem alias.",
    "header" : "https://static.productionready.io/images/smiley-cyrus.jpg",
    "botList": [
    	{
    		"slug": "growth-bot",
    		"name" : "Growth Bot",
    		"title": "A chatbot to organize your visit to Tangier",
    		"body": "Organize your circuit in the city of Tangier by the number of days you’re staying and rest assured about what you’re going to visit and how far is it from where you are or will be.",
    		"views" : 97090,
    		"image" : "https://static.productionready.io/images/smiley-cyrus.jpg",
    		"url" : "https://botlist.co/bots/coin-prices-watcher",
        "liked" : true,
        "likesCount" : 8998,
        "voted": false,
        "votedStar": null,
        "votesCount": 1000,
        "averageStar": 4,
        "createdAt": "2016-02-18T03:22:56.637Z",
    		"updatedAt": "2016-02-18T03:48:35.824Z",
    		"categoryList": [
          {
            "slug" => "traveling",
             "name" => "Traveling", 
          },
          {
            "slug" => "life",
            "name => "Life"
          }
        ],
    		"author": {
      			"username": "Jack",
      			"bio": "I work at statefarm",
      			"image": "https://i.stack.imgur.com/xHWG8.jpg",
      			"header": "https://static.productionready.io/images/smiley-cyrus.jpg",
      			"name": "Jack Reacher",
      			"website": "https://static.productionready.io",
      			"twitter": "https://twitter.com/realdonaldtrump",
      			"facebook": "https://www.facebook.com/POTUS",
      			"following": false
    		}
    	}, 
        {
    		"slug": "votum",
    		"name" : "Votum",
    		"title": "Polls and crowdsourcing for your Slack team",
    		"body": "Votum enables you to:
            	- Run quick polls
            	- Collect questions for all hands/town hall/AMA meetings
            	- Collect and prioritize meeting topics
            	- Prepare retrospective agendas in advance
            	- Collect ideas and run idea tournaments with your team",
    		"views" : 4646,
    		"image" : "https://static.productionready.io/images/smiley-cyrus.jpg",
    		"url" : "https://botlist.co/bots/coin-prices-watcher",
        "liked" : true,
        "likesCount" : 8998,
        "voted": false,
        "votedStar": null,
        "votesCount": 1000,
        "averageStar": 4,
        "createdAt": "2016-02-18T03:22:56.637Z",
    		"updatedAt": "2016-02-18T03:48:35.824Z",
    		"categoryList": [
          {
            "slug" => "traveling",
             "name" => "Traveling", 
          },
          {
            "slug" => "life",
            "name => "Life"
          }
        ],
    		"author": {
      			"username": "Jack",
      			"bio": "I work at statefarm",
      			"image": "https://i.stack.imgur.com/xHWG8.jpg",
      			"header": "https://static.productionready.io/images/smiley-cyrus.jpg",
      			"name": "Jack Reacher",
      			"website": "https://static.productionready.io",
      			"twitter": "https://twitter.com/realdonaldtrump",
      			"facebook": "https://www.facebook.com/POTUS",
      			"following": false
    		}
  		}
    ],
    "createdAt": "2016-02-18T03:22:56.637Z",
    "updatedAt": "2016-02-18T03:48:35.824Z",
    "author": {
      "username": "Jack",
      "bio": "I work at statefarm",
      "image": "https://i.stack.imgur.com/xHWG8.jpg",
      "header": "https://static.productionready.io/images/smiley-cyrus.jpg",
      "name": "Jack Reacher",
      "website": "https://static.productionready.io",
      "twitter": "https://twitter.com/realdonaldtrump",
      "facebook": "https://www.facebook.com/POTUS",
      "following": false
    }
  }],
  "collectionsCount": 2
}
```

## Endpoints

### Normal Authentication

`POST /api/users/login`

Example request body:
```JSON
{
  "user":{
    "email": "jack@gmail.com",
    "password": "123456"
  }
}
```

No authentication required, returns a [User](#users-for-authentication)

Required fields: `email`, `password`

If user account has not been activated, returns a [Message](#message) with 202 status code

Example response payload:
```JSON
{
  "message": "You need to confirm your account. We have sent you an activation code, please check your email.",
}
```


### Social Authentication

`GET /api/users/login/facebook`

or

`GET /api/users/login/twitter`

No authentication required, returns a [User](#users-for-authentication)


### Registration

`POST /api/users`

Example request body:
```JSON
{
  "user":{
    "username": "jack",
    "email": "jack@gmail.com",
    "password": "123456"
  }
}
```

No authentication required, returns a [Message](#message) with 201 status code

Required fields: `email`, `username`, `password`

Example response payload:
```JSON
{
  "message": "We sent you an activation request. Please check your email inbox.",
}
```


### Request Password Reset

`POST /api/users/password/reset`

Example request body:
```JSON
{
  "user":{
    "email": "jack@gmail.com",
  }
}
```

No authentication required, returns a [Message](#message) with 201 or 404 status code

Required fields: `email`

Example response payload:
```JSON
{
  "message": "We sent you an password reset instruction. Please check your email inbox.",
}
```


### Reset Password

`PUT /api/users/password/reset/{token}`

Example request body:
```JSON
{
  "user":{
    "email": "jack@gmail.com",
    "password": "123456",
    "password_confirmation": "123456",
  }
}
```

No authentication required, returns a [Message](#message) with 200 or 404 status code

Required fields: `email`, `password`, `password_confirmation`


### Upload Image

`POST /api/upload-image`

Authentication required, returns a String that's the uploaded image url

Make sure the request content type is `Content-Type: multipart/form-data`

Returned URL is `http://45.32.117.24/images/{uploaded-image-name}`


### Get Current User

`GET /api/user`

Authentication required, returns a [User](#users-for-authentication) that's the current user


### Update User

`PUT /api/user`

Example request body:
```JSON
{
  "user":{
    "username": "jack",
    "email": "jack@gmail.com",
    "password": "123456"
    "bio": "I like to skateboard",
    "image": "https://i.stack.imgur.com/xHWG8.jpg",
    "header": "https://static.productionready.io/images/smiley-cyrus.jpg",
    "name": "Jack Reacher",
    "website": "https://static.productionready.io",
    "twitter": "https://twitter.com/realdonaldtrump",
    "facebook": "https://www.facebook.com/POTUS",
  }
}
```

Authentication required, returns the [User](#users-for-authentication)

Accepted fields: `email`, `username`, `password`, `image`, `bio`, ...


### Get Profile

`GET /api/profiles/:username`

Authentication optional, returns a [Profile](#profile)


### Follow user

`POST /api/profiles/:username/follow`

Authentication required, returns a [Profile](#profile)

No additional parameters required


### Unfollow user

`DELETE /api/profiles/:username/follow`

Authentication required, returns a [Profile](#profile)

No additional parameters required


### List Bots

`GET /api/bots`

Returns most recent bots globally by default, provide `category`, `author` or `liked` query parameter to filter results

Query Parameters:

Filter by category:

`?category=traveling`

Filter by author:

`?author=jack`

Liked by user:

`?liked=jack`

Limit number of bots (default is 20):

`?limit=10`

Offset/skip number of bots (default is 0):

`?offset=10`

Authentication optional, will return [multiple bots](#multiple-bots), ordered by most recent first


### Hungry Bots

`GET /api/bots/hungry`

Can also take `limit` and `offset` query parameters like [List Bots](#list-bots)

Authentication required, will return [multiple bots](#multiple-bots) created by followed users, ordered by most recent first.


### Get Bot

`GET /api/bots/:slug`

No authentication required, will return [single bot](#single-bot)


### Create Bot

`POST /api/bots`

Example request body:

```JSON
{
  "bot": {
    "name" : "Growth Bot",
    "title": "A chatbot to organize your visit to Tangier",
    "body": "Organize your circuit in the city of Tangier by the number of days you’re staying and rest assured about what you’re going to visit and how far is it from where you are or will be.",
    "image" : "https://static.productionready.io/images/smiley-cyrus.jpg",
    "url" : "https://botlist.co/bots/coin-prices-watcher",
    "categoryList": ["Traveling", "Life"]
  }
}
```

Authentication required, will return an [Bot](#single-bot)

Required fields: `name`, `title`, `body`, `image`, `url`

Optional fields: `categoryList` as an array of Strings


### Update Bot

`PUT /api/bots/:slug`

Example request body:

```JSON
{
  "bot": {
    "name" : "Growth Bot",
    "title": "A chatbot to organize your visit to Tangier",
    "body": "Organize your circuit in the city of Tangier by the number of days you’re staying and rest assured about what you’re going to visit and how far is it from where you are or will be.",
    "image" : "https://static.productionready.io/images/smiley-cyrus.jpg",
    "url" : "https://botlist.co/bots/coin-prices-watcher",
    "categoryList": ["Traveling", "Life"]
  }
}
```

Authentication required, returns the updated [Bot](#single-bot)

Optional fields: `name`, `title`, `body`, `image`, `categoryList`, `url`

The `slug` also gets updated when the `name` is changed


### Delete Bot

`DELETE /api/bots/:slug`

Authentication required


### Add Review to an Bot

`POST /api/bots/:slug/reviews`

Example request body:

```JSON
{
  "review": {
    "body": "Don't forget to subscribe to stay in touch with Lea and receive exclusive messages from her!"
  }
}
```

Authentication required, returns the created [Review](#single-review)

Required field: `body`


### Get Reviews from an Bot

`GET /api/bots/:slug/reviews`

Authentication optional, returns [multiple reviews](#multiple-reviews)


### Delete Review

`DELETE /api/bots/:slug/reviews/:id`

Authentication required


### Like Bot

`POST /api/bots/:slug/like`

Authentication required, returns the [Bot](#single-bot)

No additional parameters required


### Unlike Bot

`DELETE /api/bots/:slug/like`

Authentication required, returns the [Bot](#single-bot)

No additional parameters required


### Vote Bot

`POST /api/bots/:slug/vote`

Example request body:

```JSON
{
  "vote": {
    "star": 4
  }
}
```

Authentication required, returns the [Bot](#single-bot)

Required field: `star`


### Get Categories

`GET /api/categories`

No authentication required, returns a [List of Categories](#list-of-categories)


### List Collections

`GET /api/collections`

Returns most recent collections globally by default, provide `author` query parameter to filter results

Filter by author:

`?author=jack`

Limit number of collections (default is 20):

`?limit=10`

Offset/skip number of collections (default is 0):

`?offset=10`

Authentication optional, will return [multiple collections](#multiple-collections), ordered by most recent first


### Get Collection

`GET /api/collections/:slug`

No authentication required, will return [single collection](#single-collection)


### Create Collection

`POST /api/collections`

Example request body:

```JSON
{
  "collection": {
    "name":"Mr Conrad Senger",
    "description":"Itaque omnis tempora saepe vel rem alias.",
    "header":"https:\/\/cdn.worldvectorlogo.com\/logos\/laravel.svg",
    "botList": ["Traveling Bot", "Life Bot"]
  }
}
```

Authentication required, will return an [Collection](#single-collection)

Required fields: `name`, `description`, `header`

Optional fields: `botList` as an array of Strings


### Update Collection

`PUT /api/collections/:slug`

Example request body:

```JSON
{
  "collection": {
    "name":"Mr Conrad Senger",
    "description":"Itaque omnis tempora saepe vel rem alias.",
    "header":"https:\/\/cdn.worldvectorlogo.com\/logos\/laravel.svg",
    "botList": ["Traveling Bot", "Life Bot"]
  }
}
```

Authentication required, returns the updated [Collection](#single-collection)

Optional fields: `name`, `description`, `header`, `botList`

The `slug` also gets updated when the `name` is changed


### Delete Collection

`DELETE /api/collections/:slug`

Authentication required
