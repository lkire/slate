---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - javascript
  - python
  - cpp
  - go

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the lkire.com demos API! You can use this API to embed interactive and live-data demos in your own site. Additionally, some of the demos provide API endpoints of their own, which are documented here. You will find language bindings in JavaScript, Python, C++, and go! 


# Authorization

> To obtain access to protected demos, please fill out the request form on the Contact page. If you would like to embed protected resources or access protected APIs please indicate so on the request form.



```python
import lkire-api

api = lkire-api.authorize('youraccesstocken')
```

```javascript
const lkire-api = require('lkire-api');

let api = lkire-api.authorize('youraccesstoken');
```

> Make sure to replace `youraccesstoken` with your API key.

lkire.com uses API keys to allow access to restricted APIs. You can register a new lkire.com API key at the [Contact Page](http://lkire.com/contact).

lkire.com expects for the API key to be included in all restricted API requests to the server in a header that looks like the following:

`Authorization: youraccesstoken`

<aside class="notice">
You must replace <code>youraccesstoken</code> with your personal API key.
</aside>


# Demos

## Get All Demos

```python
import lkire-api

api = lkire-api.authorize('youraccesstoken')
api.demos.get()
```

```javascript
const lkire-api = require('lkire-api');

let api = lkire-api.authorize('youraccesstoken');
let demos = lkire-api.demos.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "category": "stat",
    "title": "Wavelet Time Series Analysis",
    "frame": "http://api.lkire.com/wavelet",
    "description": "Wavelets provide a complete orthonormal 
    decomposition of a function with both..."
  },
  {
    "id": 2,
    "category": "ml",
    "title": "Convolutional Neural Network Playground",
    "frame": "http://api.lkire.com/cnn",
    "description": "Convolutional neural networks embed layers 
    for the discovery of convolutionally tiled feature sets..."
  }
]
```

This endpoint retrieves all demos with your level of authentication.

### HTTP Request

`GET http://api.lkire.com/cnn`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
category | all | May be set to a category in the set {ml, phys, stat} to limit topic. 

<aside class="success">
Remember — some demos may not be visible without authentication!
</aside>
