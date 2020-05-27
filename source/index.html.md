---
title: API Documentation

language_tabs: # must be one of https://git.io/vQNgJ
  - shell


toc_footers:
  - <a href='mailto:contact@inokufu.com'>Ask a Developer Key 🔑 here</a>
  - <a href='http://www.inokufu.com/'>Made with ❤️ by Inokufu</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Inokufu API Cloud! This API documentation shows you how to access our API endpoints, which can get information about Learning Objects in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "x-api-key: SAY-FRIEND-AND-ENTER"
```

> Make sure to replace `SAY-FRIEND-AND-ENTER` with your own Developer API key.

Inokufu API Cloud uses API keys to allow access to the API. You can register for a Developer API key by sending us an email at [contact@inokufu.com](mailto:contact@inokufu.com).

For Demo purpose, you can use this API key : 'SAY-FRIEND-AND-ENTER'. 

Free Developer API keys are available on request and let you make up to 250 requests per month.

For higher request quota we offer paid usage plan starting at 100 $/month. Feel free to get in touch at [contact@inokufu.com](mailto:contact@inokufu.com) we are fully dedicated to the success of our customers and partners. Together we can make the education better. 😊

Inokufu API Cloud expects for the API key to be included in API requests to the server in a header that looks like the following:

`x-api-key: SAY-FRIEND-AND-ENTER`

<aside class="warning">
Replace <code>SAY-FRIEND-AND-ENTER</code> with your own Developer API key to make more requests.
</aside>

# Learning Objects (LO)

## Type


```shell
curl "https://api.inokufu.com/v1/type"
```

> The above command returns JSON structured like this:

```json
[
  {
    "type": "video",
    "description": "Educational videos from providers such as YouTube, Dailymotion, Vimeo, etc."
  },
  {
    "type": "mooc",
    "description": "Massive Open Online Course (MOOC) from providers such as edX, Coursera, OpenClassrooms, Linkedin Learning, etc."
  },
  {
    "type": "podcast",
    "description": "Educational audio file from providers such as ApplePodcasts, SoundCloud."
  },
  {
    "type": "training",
    "description": "Training include any formal set of courses and other learning activities in a coherent learning package, including final assesments and certification (certificate, diploma, degree). Major providers are MonCompteFormation, PÃ´le Emploi, etc."
  },
  {
    "type": "distance_learning",
    "description": "Distance learning encompass any distance education or training which does not require learners to be physically present in a specifi location (brick and mortar school, university, training center). This includes correspondence courses wherein the student corresponded with the school via post, online education or eLearning but doesn't include MOOC which have their own type. Major providers are MonCompteFormation, PÃ´le Emploi, etc."
  }
]
```

This endpoint retrieves a list of the types of LO currently supported.   

Type | Example of providers 
--------- | ------- 
`video` | YouTube, Dailymotion, Vimeo 
`mooc` | edX, Coursera, OpenClassrooms, Linkedin Learning 
`podcast` | ApplePodcasts, SoundCloud 
`training` | MonCompteFormation, Pôle Emploi 
`distance_learning` | MonCompteFormation, Pôle Emploi 

### HTTP Request

`GET https://api.inokufu.com/v1/type`

### Query Parameters

This endpoint does not require any query parameter.

## Bloom

```shell
curl "https://api.inokufu.com/v1/bloom"
```

> The above command returns JSON structured like this:

```json
[
  {
    "bloom": "discover",
    "description": "These LO are the first step to discover a job or a skill. You'll be able to talk about it, to know the basics. You'll have all the knowledge to decide wether it's for you or not.",
  },
  {
    "bloom": "understand",
    "description": "These LO help you better understand this job or skill, in details. You'll dive deeper in the theory. You'll be able to explain, estimate, At the end, you'll be a master of the theoretical aspects.",
  },
  {
    "bloom": "do",
    "description": "These LO help you put into practice what you have learned. You'll make, manipulate, simulate. You are applying what you learn.",
  },
  {
    "bloom": "curriculum",
    "description": "These LO train you to a specific job or skill at a professional level. From Discovery, Understanding to Doing, at the end you are a Pro.",
  }
]
```

This endpoint retrieves a list of the levels of learning objectives associated to a LO and currently supported. These levels are adapted from those of [Bloom's taxonomy](https://en.wikipedia.org/wiki/Bloom%27s_taxonomy). `discover` is used as a synonym of knowledge, `understand` for comprehension and `do` for application. Curriculum was added as a compound level for LO that include the three other levels (`discover`, `understand`, `do`) in a coherent way (e.g. University degree).  

Bloom | Learning objective 
--------- | ------- 
`discover` | First step to discover a job or a skill. Memorize knowledge.
`understand` | Understanding a job or skill, in details. Being able to explain, estimate.
`do` | Put into practice what has been learned. Make, manipulate, simulate.
`curriculum` | Complete training to a specific job or skill at a professional level.

### HTTP Request

`GET https://api.inokufu.com/v1/bloom`

### Query Parameters

This endpoint does not require any query parameter.

<aside class="success">Higher levels of learning objectives are not yet implemented (analysis, synthesis, evaluation) but are definitely on our roadmap.</aside>
## Language

```shell
curl "https://api.inokufu.com/v1/lang"
```

> The above command returns JSON structured like this:

```json
[
  {
    "lang": "en",
    "description": "Use this code for LO in english language."
  },
  {
    "lang": "fr",
    "description": "Use this code for LO in french language (franÃ§ais)."
  }
]
```

This endpoint retrieves a list of the languages currently supported. Inokufu API cloud uses ISO 2 Letter Language Codes for every endpoints with `lang` as a query parameter.  

Lang code | Language 
--------- | ------- 
`en` | english
`fr` | french 

### HTTP Request

`GET https://api.inokufu.com/v1/lang`

### Query Parameters

This endpoint does not require any query parameter.


<aside class="success">
More languages will be added in the upcoming months!
</aside>

## Search

```shell
curl "https://api.inokufu.com/v1/search?keywords=python&bloom=understand&type=mooc&lang=en&max=2
  -H "x-api-key: SAY-FRIEND-AND-ENTER"
```

> The above command returns JSON structured like this:

```json
{
    "statusCode": 200,
    "request": {
        "keywords": "python",
        "lang": "en",
        "type": "mooc",
        "sort": "best",
        "max": 2,
        "bloom": "understand"
    },
    "response": [
        {
            "item": 0,
            "title": "Using Python for Research",
            "url": "https://www.edx.org/course/using-python-for-research-2",
            "pictureFullwidth": "https://prod-discovery.edx-cdn.org/media/course/image/c9d14131-a515-462b-82e2-6eaec5bc1c17-f7c5de2ca2ae.small.jpg",
            "pictureSquare": "nan",
            "provider": "\"Harvard University , edX\"",
            "learningTimeUnit": "h",
            "learningTimeValue": 480.0
        },
        {
            "item": 1,
            "title": "Python Basics for Data Science",
            "url": "https://www.edx.org/course/python-basics-for-data-science-2",
            "pictureFullwidth": "https://prod-discovery.edx-cdn.org/media/course/image/381a0046-5d78-4790-8776-74620d59f48e-48611c7ca556.small.png",
            "pictureSquare": "nan",
            "provider": "\"IBM , edX\"",
            "learningTimeUnit": "h",
            "learningTimeValue": 40.0
        }
    ]
}
```

This endpoint retrieves a list of LO based on the query parameters. 

LO can be filtered by keywords, type, bloom step and language (english or french for now).

### HTTP Request

`GET https://api.inokufu.com/v1/search`

### Query Parameters

Query parameters must be included in URL.

Parameter | Default | Required | Description
--------- | ------- | ----------- | -----------
`keywords` | | No | Keywords to be searched in LO title. Must be URL encoded (e.g. replacing spaces by `%20`). If empty, response will include LO of any title.
`type` | | No | Currently supported types are `video`, `mooc`,`podcast`,`training` or `distance_learning`. If empty, response will include LO of any type.
`bloom` | | No | Currently supported Bloom levels are `discover`, `understand`,`do` or `curriculum`. If empty, response will include LO of any Bloom level.
`lang` |  | No | Currently supported languages are `en` or `fr`. If empty, response will include LO of any language.
`sort` | `random` | No | Currently supported sorting order are `random` or `best`. If empty, response will be sorted in random order.
`max` |  | Yes | The maximum number of LO in response. Limited to 10.

API key must be included in a header that looks like the following:

`x-api-key: SAY-FRIEND-AND-ENTER`

<aside class="warning">
Replace <code>SAY-FRIEND-AND-ENTER</code> with your own Developer API key to make more requests.</aside>

### Response Parameters

Parameter |  Description
--------- | -----------
`title` | Complete title of the LO.
`url` | Link to the LO webpage.
`pictureFullwidth` | Link to the picture of the LO in landscape format.
`pictureSquare` | Link to the picture of the LO in square or portrait format.
`provider` | Entity providing or hosting the LO.
`learningTimeUnit` | Unit of time associated to the learning time of the LO.
`learningTimeValue` | Learning time of the LO.

<aside class="success">
More API endpoints are under development. Feel free to reach us at contact@inokufu.com if you have specific need or idea. </aside>

# Credits

This API documentation page was created with [Slate](https://github.com/slatedocs/slate). Feel free to check their awesome repo on Github!

