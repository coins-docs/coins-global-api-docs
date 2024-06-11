---
title: COINS Brazil Public Spot API v1.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="coins-brazil-public-spot-api">COINS Brazil Public Spot API v1.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

OpenAPI Specifications for the COINS Brazil Public Spot API

API documents:

Base URLs:

* <a href="https://api.brazil-qa.coins.xyz">https://api.brazil-qa.coins.xyz</a>

* <a href="https://api.brazil.coins.xyz">https://api.brazil.coins.xyz</a>

# Authentication

* API Key (ApiKeyAuth)
    - Parameter Name: **X-COINS-APIKEY**, in: header. COINS Public API Key

<h1 id="coins-brazil-public-spot-api-users">Users</h1>

Users Management

## post__users

> Code samples

```shell
# You can also use wget
curl -X POST https://api.brazil-qa.coins.xyz/users?referenceUserId=0000000000012909&email=marciosfalsin%40gmail.com \
  -H 'Accept: application/json' \
  -H 'X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f' \
  -H 'timestamp: 0' \
  -H 'signature: string' \
  -H 'X-COINS-APIKEY: API_KEY'

```

```http
POST https://api.brazil-qa.coins.xyz/users?referenceUserId=0000000000012909&email=marciosfalsin%40gmail.com HTTP/1.1
Host: api.brazil-qa.coins.xyz
Accept: application/json
X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f
timestamp: 0
signature: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'X-COINS-TRACE-ID':'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp':'0',
  'signature':'string',
  'X-COINS-APIKEY':'API_KEY'
};

fetch('https://api.brazil-qa.coins.xyz/users?referenceUserId=0000000000012909&email=marciosfalsin%40gmail.com',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp' => '0',
  'signature' => 'string',
  'X-COINS-APIKEY' => 'API_KEY'
}

result = RestClient.post 'https://api.brazil-qa.coins.xyz/users',
  params: {
  'referenceUserId' => 'string',
'email' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-COINS-TRACE-ID': 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp': '0',
  'signature': 'string',
  'X-COINS-APIKEY': 'API_KEY'
}

r = requests.post('https://api.brazil-qa.coins.xyz/users', params={
  'referenceUserId': '0000000000012909',  'email': 'marciosfalsin@gmail.com'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
    'timestamp' => '0',
    'signature' => 'string',
    'X-COINS-APIKEY' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://api.brazil-qa.coins.xyz/users', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.brazil-qa.coins.xyz/users?referenceUserId=0000000000012909&email=marciosfalsin%40gmail.com");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-COINS-TRACE-ID": []string{"coins.xyz-9be3-4c8d-8cda-0f9334468c3f"},
        "timestamp": []string{"0"},
        "signature": []string{"string"},
        "X-COINS-APIKEY": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.brazil-qa.coins.xyz/users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /users`

*Creates a simple user (USER_DATA)*

Creates a simple user

<h3 id="post__users-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|X-COINS-TRACE-ID|header|string|true|The value should start with the partner ID (e.g. coins.br), and end with UUID|
|referenceUserId|query|string|true|Your own user Id, used for your systems|
|email|query|string|true|The user email|
|timestamp|header|integer(int64)|true|UTC timestamp in ms|
|signature|header|string|true|Signature|

> Example responses

> 200 Response

```json
{
  "sysCd": "BS000000",
  "sysMsg": "OK",
  "biz": {
    "bizCd": "BS000000",
    "bizMsg": "OK",
    "data": {
      "userId": "a9fcb833-29fe-4206-b39c-c427614663ee",
      "referenceUserId": "0000000000012909",
      "email": "marciosfalsin@gmail.com"
    }
  }
}
```

<h3 id="post__users-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|kyc start|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[error](#schemaerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized Request|[error](#schemaerror)|

<h3 id="post__users-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» sysCd|string|false|none|none|
|» sysMsg|string|false|none|none|
|» biz|object|false|none|none|
|»» bizCd|string|false|none|none|
|»» bizMsg|string|false|none|none|
|»» data|object|false|none|none|
|»»» userId|string|false|none|none|
|»»» referenceUserId|string|false|none|none|
|»»» email|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## get__users

> Code samples

```shell
# You can also use wget
curl -X GET https://api.brazil-qa.coins.xyz/users?referenceUserId=0000000000012909 \
  -H 'Accept: application/json' \
  -H 'X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f' \
  -H 'timestamp: 0' \
  -H 'signature: string' \
  -H 'X-COINS-APIKEY: API_KEY'

```

```http
GET https://api.brazil-qa.coins.xyz/users?referenceUserId=0000000000012909 HTTP/1.1
Host: api.brazil-qa.coins.xyz
Accept: application/json
X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f
timestamp: 0
signature: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'X-COINS-TRACE-ID':'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp':'0',
  'signature':'string',
  'X-COINS-APIKEY':'API_KEY'
};

fetch('https://api.brazil-qa.coins.xyz/users?referenceUserId=0000000000012909',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp' => '0',
  'signature' => 'string',
  'X-COINS-APIKEY' => 'API_KEY'
}

result = RestClient.get 'https://api.brazil-qa.coins.xyz/users',
  params: {
  'referenceUserId' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-COINS-TRACE-ID': 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp': '0',
  'signature': 'string',
  'X-COINS-APIKEY': 'API_KEY'
}

r = requests.get('https://api.brazil-qa.coins.xyz/users', params={
  'referenceUserId': '0000000000012909'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
    'timestamp' => '0',
    'signature' => 'string',
    'X-COINS-APIKEY' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://api.brazil-qa.coins.xyz/users', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.brazil-qa.coins.xyz/users?referenceUserId=0000000000012909");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-COINS-TRACE-ID": []string{"coins.xyz-9be3-4c8d-8cda-0f9334468c3f"},
        "timestamp": []string{"0"},
        "signature": []string{"string"},
        "X-COINS-APIKEY": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.brazil-qa.coins.xyz/users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /users`

*Gets user data by referenceUserId (USER_DATA)*

Gets user data by referenceUserId 

<h3 id="get__users-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|X-COINS-TRACE-ID|header|string|true|The value should start with the partner ID (e.g. coins.br), and end with UUID|
|referenceUserId|query|string|true|Your own user Id, used for your systems|
|timestamp|header|integer(int64)|true|UTC timestamp in ms|
|signature|header|string|true|Signature|

> Example responses

> 200 Response

```json
{
  "sysCd": "BS000000",
  "sysMsg": "OK",
  "biz": {
    "bizCd": "BS000000",
    "bizMsg": "OK",
    "data": {
      "userId": "a9fcb833-29fe-4206-b39c-c427614663ee",
      "referenceUserId": "0000000000012909",
      "email": "marciosfalsin@gmail.com"
    }
  }
}
```

<h3 id="get__users-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|kyc query by tax id|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[error](#schemaerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized Request|[error](#schemaerror)|

<h3 id="get__users-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» sysCd|string|false|none|none|
|» sysMsg|string|false|none|none|
|» biz|object|false|none|none|
|»» bizCd|string|false|none|none|
|»» bizMsg|string|false|none|none|
|»» data|object|false|none|none|
|»»» userId|string|false|none|none|
|»»» referenceUserId|string|false|none|none|
|»»» email|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## patch__users

> Code samples

```shell
# You can also use wget
curl -X PATCH https://api.brazil-qa.coins.xyz/users?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b&email=marciosfalsin%40gmail.com \
  -H 'Accept: application/json' \
  -H 'X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f' \
  -H 'timestamp: 0' \
  -H 'signature: string' \
  -H 'X-COINS-APIKEY: API_KEY'

```

```http
PATCH https://api.brazil-qa.coins.xyz/users?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b&email=marciosfalsin%40gmail.com HTTP/1.1
Host: api.brazil-qa.coins.xyz
Accept: application/json
X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f
timestamp: 0
signature: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'X-COINS-TRACE-ID':'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp':'0',
  'signature':'string',
  'X-COINS-APIKEY':'API_KEY'
};

fetch('https://api.brazil-qa.coins.xyz/users?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b&email=marciosfalsin%40gmail.com',
{
  method: 'PATCH',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp' => '0',
  'signature' => 'string',
  'X-COINS-APIKEY' => 'API_KEY'
}

result = RestClient.patch 'https://api.brazil-qa.coins.xyz/users',
  params: {
  'userId' => 'string',
'email' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-COINS-TRACE-ID': 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp': '0',
  'signature': 'string',
  'X-COINS-APIKEY': 'API_KEY'
}

r = requests.patch('https://api.brazil-qa.coins.xyz/users', params={
  'userId': '8d65891d-3143-4a1e-9cba-ea3a662e121b',  'email': 'marciosfalsin@gmail.com'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
    'timestamp' => '0',
    'signature' => 'string',
    'X-COINS-APIKEY' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','https://api.brazil-qa.coins.xyz/users', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.brazil-qa.coins.xyz/users?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b&email=marciosfalsin%40gmail.com");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-COINS-TRACE-ID": []string{"coins.xyz-9be3-4c8d-8cda-0f9334468c3f"},
        "timestamp": []string{"0"},
        "signature": []string{"string"},
        "X-COINS-APIKEY": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://api.brazil-qa.coins.xyz/users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /users`

*Change the user email (USER_DATA)*

Change the user email

<h3 id="patch__users-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|X-COINS-TRACE-ID|header|string|true|The value should start with the partner ID (e.g. coins.br), and end with UUID|
|userId|query|string|true|Our user Id, generated for us|
|email|query|string|true|The user email|
|timestamp|header|integer(int64)|true|UTC timestamp in ms|
|signature|header|string|true|Signature|

> Example responses

> 200 Response

```json
{
  "sysCd": "BS000000",
  "sysMsg": "OK",
  "biz": {
    "bizCd": "BS000000",
    "bizMsg": "OK",
    "data": {
      "userId": "a9fcb833-29fe-4206-b39c-c427614663ee",
      "referenceUserId": "0000000000012909",
      "email": "marciosfalsin@gmail.com"
    }
  }
}
```

<h3 id="patch__users-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|kyc query by tax id|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[error](#schemaerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized Request|[error](#schemaerror)|

<h3 id="patch__users-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» sysCd|string|false|none|none|
|» sysMsg|string|false|none|none|
|» biz|object|false|none|none|
|»» bizCd|string|false|none|none|
|»» bizMsg|string|false|none|none|
|»» data|object|false|none|none|
|»»» userId|string|false|none|none|
|»»» referenceUserId|string|false|none|none|
|»»» email|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="coins-brazil-public-spot-api-kyc">KYC</h1>

KYC tools for Brazilian users

## post__kyc

> Code samples

```shell
# You can also use wget
curl -X POST https://api.brazil-qa.coins.xyz/kyc?taxId=41345605781&userId=8d65891d-3143-4a1e-9cba-ea3a662e121b \
  -H 'Accept: application/json' \
  -H 'X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f' \
  -H 'timestamp: 0' \
  -H 'signature: string' \
  -H 'X-COINS-APIKEY: API_KEY'

```

```http
POST https://api.brazil-qa.coins.xyz/kyc?taxId=41345605781&userId=8d65891d-3143-4a1e-9cba-ea3a662e121b HTTP/1.1
Host: api.brazil-qa.coins.xyz
Accept: application/json
X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f
timestamp: 0
signature: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'X-COINS-TRACE-ID':'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp':'0',
  'signature':'string',
  'X-COINS-APIKEY':'API_KEY'
};

fetch('https://api.brazil-qa.coins.xyz/kyc?taxId=41345605781&userId=8d65891d-3143-4a1e-9cba-ea3a662e121b',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp' => '0',
  'signature' => 'string',
  'X-COINS-APIKEY' => 'API_KEY'
}

result = RestClient.post 'https://api.brazil-qa.coins.xyz/kyc',
  params: {
  'taxId' => 'string',
'userId' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-COINS-TRACE-ID': 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp': '0',
  'signature': 'string',
  'X-COINS-APIKEY': 'API_KEY'
}

r = requests.post('https://api.brazil-qa.coins.xyz/kyc', params={
  'taxId': '41345605781',  'userId': '8d65891d-3143-4a1e-9cba-ea3a662e121b'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
    'timestamp' => '0',
    'signature' => 'string',
    'X-COINS-APIKEY' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://api.brazil-qa.coins.xyz/kyc', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.brazil-qa.coins.xyz/kyc?taxId=41345605781&userId=8d65891d-3143-4a1e-9cba-ea3a662e121b");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-COINS-TRACE-ID": []string{"coins.xyz-9be3-4c8d-8cda-0f9334468c3f"},
        "timestamp": []string{"0"},
        "signature": []string{"string"},
        "X-COINS-APIKEY": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.brazil-qa.coins.xyz/kyc", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /kyc`

*Starts KYC of a brazilian user (USER_DATA)*

Starts KYC of a brazilian user

<h3 id="post__kyc-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|X-COINS-TRACE-ID|header|string|true|The value should start with the partner ID (e.g. coins.br), and end with UUID|
|taxId|query|string|true|11 digits including zeroes, as string (brazilian CPF)|
|userId|query|string|true|Our user Id, generated for us|
|name|query|string|false|the complete name of the user|
|birthDate|query|string|false|birthDate in string format YYYY-MM-DD|
|timestamp|header|integer(int64)|true|UTC timestamp in ms|
|signature|header|string|true|Signature|

> Example responses

> 200 Response

```json
{
  "sysCd": "BS000000",
  "sysMsg": "OK",
  "biz": {
    "bizCd": "BS000000",
    "bizMsg": "OK",
    "data": {
      "userId": "a9fcb833-29fe-4206-b39c-c427614663ee",
      "taxId": "41345605781",
      "name": "Jean Vlaude Fan Daime",
      "status": "WAITING",
      "level": 0
    }
  }
}
```

<h3 id="post__kyc-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|kyc start|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[error](#schemaerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized Request|[error](#schemaerror)|

<h3 id="post__kyc-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» sysCd|string|false|none|none|
|» sysMsg|string|false|none|none|
|» biz|object|false|none|none|
|»» bizCd|string|false|none|none|
|»» bizMsg|string|false|none|none|
|»» data|object|false|none|none|
|»»» userId|string|false|none|none|
|»»» taxId|string|false|none|none|
|»»» name|string|false|none|none|
|»»» status|string|false|none|none|
|»»» level|integer|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|WAITING|
|status|APPROVED|
|status|REPROVED|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## get__kyc

> Code samples

```shell
# You can also use wget
curl -X GET https://api.brazil-qa.coins.xyz/kyc?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b \
  -H 'Accept: application/json' \
  -H 'X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f' \
  -H 'timestamp: 0' \
  -H 'signature: string' \
  -H 'X-COINS-APIKEY: API_KEY'

```

```http
GET https://api.brazil-qa.coins.xyz/kyc?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b HTTP/1.1
Host: api.brazil-qa.coins.xyz
Accept: application/json
X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f
timestamp: 0
signature: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'X-COINS-TRACE-ID':'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp':'0',
  'signature':'string',
  'X-COINS-APIKEY':'API_KEY'
};

fetch('https://api.brazil-qa.coins.xyz/kyc?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp' => '0',
  'signature' => 'string',
  'X-COINS-APIKEY' => 'API_KEY'
}

result = RestClient.get 'https://api.brazil-qa.coins.xyz/kyc',
  params: {
  'userId' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-COINS-TRACE-ID': 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp': '0',
  'signature': 'string',
  'X-COINS-APIKEY': 'API_KEY'
}

r = requests.get('https://api.brazil-qa.coins.xyz/kyc', params={
  'userId': '8d65891d-3143-4a1e-9cba-ea3a662e121b'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
    'timestamp' => '0',
    'signature' => 'string',
    'X-COINS-APIKEY' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://api.brazil-qa.coins.xyz/kyc', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.brazil-qa.coins.xyz/kyc?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-COINS-TRACE-ID": []string{"coins.xyz-9be3-4c8d-8cda-0f9334468c3f"},
        "timestamp": []string{"0"},
        "signature": []string{"string"},
        "X-COINS-APIKEY": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.brazil-qa.coins.xyz/kyc", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /kyc`

*Query the KYC of a brazilian user situation (USER_DATA)*

Query the KYC of a brazilian user situation 

<h3 id="get__kyc-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|X-COINS-TRACE-ID|header|string|true|The value should start with the partner ID (e.g. coins.br), and end with UUID|
|userId|query|string|true|Our user Id, generated for us|
|timestamp|header|integer(int64)|true|UTC timestamp in ms|
|signature|header|string|true|Signature|

> Example responses

> 200 Response

```json
{
  "sysCd": "BS000000",
  "sysMsg": "OK",
  "biz": {
    "bizCd": "BS000000",
    "bizMsg": "OK",
    "data": {
      "userId": "a9fcb833-29fe-4206-b39c-c427614663ee",
      "taxId": "41345605781",
      "name": "Jean Vlaude Fan Daime",
      "status": "APPROVED",
      "level": 1
    }
  }
}
```

<h3 id="get__kyc-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|kyc query by tax id|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[error](#schemaerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized Request|[error](#schemaerror)|

<h3 id="get__kyc-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» sysCd|string|false|none|none|
|» sysMsg|string|false|none|none|
|» biz|object|false|none|none|
|»» bizCd|string|false|none|none|
|»» bizMsg|string|false|none|none|
|»» data|object|false|none|none|
|»»» userId|string|false|none|none|
|»»» taxId|string|false|none|none|
|»»» name|string|false|none|none|
|»»» status|string|false|none|none|
|»»» level|integer|false|none|The user can be approved, but no levels while him does not send documento images|

#### Enumerated Values

|Property|Value|
|---|---|
|status|WAITING|
|status|APPROVED|
|status|REPROVED|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## patch__kyc

> Code samples

```shell
# You can also use wget
curl -X PATCH https://api.brazil-qa.coins.xyz/kyc?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b \
  -H 'Accept: application/json' \
  -H 'X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f' \
  -H 'timestamp: 0' \
  -H 'signature: string' \
  -H 'X-COINS-APIKEY: API_KEY'

```

```http
PATCH https://api.brazil-qa.coins.xyz/kyc?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b HTTP/1.1
Host: api.brazil-qa.coins.xyz
Accept: application/json
X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f
timestamp: 0
signature: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'X-COINS-TRACE-ID':'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp':'0',
  'signature':'string',
  'X-COINS-APIKEY':'API_KEY'
};

fetch('https://api.brazil-qa.coins.xyz/kyc?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b',
{
  method: 'PATCH',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp' => '0',
  'signature' => 'string',
  'X-COINS-APIKEY' => 'API_KEY'
}

result = RestClient.patch 'https://api.brazil-qa.coins.xyz/kyc',
  params: {
  'userId' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-COINS-TRACE-ID': 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp': '0',
  'signature': 'string',
  'X-COINS-APIKEY': 'API_KEY'
}

r = requests.patch('https://api.brazil-qa.coins.xyz/kyc', params={
  'userId': '8d65891d-3143-4a1e-9cba-ea3a662e121b'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
    'timestamp' => '0',
    'signature' => 'string',
    'X-COINS-APIKEY' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','https://api.brazil-qa.coins.xyz/kyc', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.brazil-qa.coins.xyz/kyc?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-COINS-TRACE-ID": []string{"coins.xyz-9be3-4c8d-8cda-0f9334468c3f"},
        "timestamp": []string{"0"},
        "signature": []string{"string"},
        "X-COINS-APIKEY": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://api.brazil-qa.coins.xyz/kyc", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /kyc`

*Complete the user KYC data (USER_DATA)*

Complete the user KYC data 

<h3 id="patch__kyc-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|X-COINS-TRACE-ID|header|string|true|The value should start with the partner ID (e.g. coins.br), and end with UUID|
|userId|query|string|true|Our user Id, generated for us|
|proofOfAddress|query|string|false|base64 from an proof of address image as Energy Bill, Water Bill or Phone Bill|
|documentFrontBack|query|string|false|base64 from a document front and back image as Driver's license|
|documentBack|query|string|false|base64 from a document back image as ID Card|
|documentFront|query|string|false|base64 from a document front image as ID Card|
|selfie|query|string|false|base64 from a selfie image|
|timestamp|header|integer(int64)|true|UTC timestamp in ms|
|signature|header|string|true|Signature|

> Example responses

> 200 Response

```json
{
  "sysCd": "BS000000",
  "sysMsg": "OK",
  "biz": {
    "bizCd": "BS000000",
    "bizMsg": "OK",
    "data": {
      "userId": "a9fcb833-29fe-4206-b39c-c427614663ee",
      "taxId": 41345605781,
      "name": "Jean Vlaude Fan Daime",
      "status": "APPROVED",
      "level": 1
    }
  }
}
```

<h3 id="patch__kyc-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|kyc query by tax id|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[error](#schemaerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized Request|[error](#schemaerror)|

<h3 id="patch__kyc-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» sysCd|string|false|none|none|
|» sysMsg|string|false|none|none|
|» biz|object|false|none|none|
|»» bizCd|string|false|none|none|
|»» bizMsg|string|false|none|none|
|»» data|object|false|none|none|
|»»» userId|string|false|none|none|
|»»» taxId|string|false|none|none|
|»»» name|string|false|none|none|
|»»» status|string|false|none|none|
|»»» level|integer|false|none|The user can be approved, but no levels while him does not send documento images|

#### Enumerated Values

|Property|Value|
|---|---|
|status|WAITING|
|status|APPROVED|
|status|REPROVED|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="coins-brazil-public-spot-api-fiat">FIAT</h1>

FIAT tools for Brazil (PIX)

## get__balance

> Code samples

```shell
# You can also use wget
curl -X GET https://api.brazil-qa.coins.xyz/balance \
  -H 'Accept: application/json' \
  -H 'X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f' \
  -H 'timestamp: 0' \
  -H 'signature: string' \
  -H 'X-COINS-APIKEY: API_KEY'

```

```http
GET https://api.brazil-qa.coins.xyz/balance HTTP/1.1
Host: api.brazil-qa.coins.xyz
Accept: application/json
X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f
timestamp: 0
signature: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'X-COINS-TRACE-ID':'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp':'0',
  'signature':'string',
  'X-COINS-APIKEY':'API_KEY'
};

fetch('https://api.brazil-qa.coins.xyz/balance',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp' => '0',
  'signature' => 'string',
  'X-COINS-APIKEY' => 'API_KEY'
}

result = RestClient.get 'https://api.brazil-qa.coins.xyz/balance',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-COINS-TRACE-ID': 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp': '0',
  'signature': 'string',
  'X-COINS-APIKEY': 'API_KEY'
}

r = requests.get('https://api.brazil-qa.coins.xyz/balance', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
    'timestamp' => '0',
    'signature' => 'string',
    'X-COINS-APIKEY' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://api.brazil-qa.coins.xyz/balance', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.brazil-qa.coins.xyz/balance");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-COINS-TRACE-ID": []string{"coins.xyz-9be3-4c8d-8cda-0f9334468c3f"},
        "timestamp": []string{"0"},
        "signature": []string{"string"},
        "X-COINS-APIKEY": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.brazil-qa.coins.xyz/balance", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /balance`

*Query partner balance*

Query Partner Balance

<h3 id="get__balance-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|X-COINS-TRACE-ID|header|string|true|The value should start with the partner ID (e.g. coins.br), and end with UUID|
|timestamp|header|integer(int64)|true|UTC timestamp in ms|
|signature|header|string|true|Signature|

> Example responses

> 200 Response

```json
{
  "sysCd": "BS000000",
  "sysMsg": "OK",
  "biz": {
    "bizCd": "BS000000",
    "bizMsg": "OK",
    "data": {
      "updateTime": 1624529919000,
      "balance": 0.01
    }
  }
}
```

<h3 id="get__balance-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|user balance|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[error](#schemaerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized Request|[error](#schemaerror)|

<h3 id="get__balance-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» sysCd|string|false|none|none|
|» sysMsg|string|false|none|none|
|» biz|object|false|none|none|
|»» bizCd|string|false|none|none|
|»» bizMsg|string|false|none|none|
|»» data|object|false|none|none|
|»»» updateTime|integer(int64)|false|none|epoch date time|
|»»» balance|number|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## get__order_history

> Code samples

```shell
# You can also use wget
curl -X GET https://api.brazil-qa.coins.xyz/order/history \
  -H 'Accept: application/json' \
  -H 'X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f' \
  -H 'timestamp: 0' \
  -H 'signature: string' \
  -H 'X-COINS-APIKEY: API_KEY'

```

```http
GET https://api.brazil-qa.coins.xyz/order/history HTTP/1.1
Host: api.brazil-qa.coins.xyz
Accept: application/json
X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f
timestamp: 0
signature: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'X-COINS-TRACE-ID':'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp':'0',
  'signature':'string',
  'X-COINS-APIKEY':'API_KEY'
};

fetch('https://api.brazil-qa.coins.xyz/order/history',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp' => '0',
  'signature' => 'string',
  'X-COINS-APIKEY' => 'API_KEY'
}

result = RestClient.get 'https://api.brazil-qa.coins.xyz/order/history',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-COINS-TRACE-ID': 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp': '0',
  'signature': 'string',
  'X-COINS-APIKEY': 'API_KEY'
}

r = requests.get('https://api.brazil-qa.coins.xyz/order/history', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
    'timestamp' => '0',
    'signature' => 'string',
    'X-COINS-APIKEY' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://api.brazil-qa.coins.xyz/order/history', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.brazil-qa.coins.xyz/order/history");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-COINS-TRACE-ID": []string{"coins.xyz-9be3-4c8d-8cda-0f9334468c3f"},
        "timestamp": []string{"0"},
        "signature": []string{"string"},
        "X-COINS-APIKEY": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.brazil-qa.coins.xyz/order/history", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /order/history`

*Query partner transactions*

Query partner Transcactions

<h3 id="get__order_history-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|X-COINS-TRACE-ID|header|string|true|The value should start with the partner ID (e.g. coins.br), and end with UUID|
|timestamp|header|integer(int64)|true|UTC timestamp in ms|
|signature|header|string|true|Signature|

> Example responses

> 200 Response

```json
{
  "sysCd": "BS000000",
  "sysMsg": "OK",
  "biz": {
    "bizCd": "BS000000",
    "bizMsg": "OK",
    "total": 200,
    "pageNum": 2,
    "pageSize": 100,
    "data": [
      {
        "referenceId": "100000000000022221",
        "orderId": "5a43sd2-4a5s3-d254as32-as3452a-3455as431",
        "channelReferenceId": "00000012121212",
        "createTime": 1624529919000,
        "transactionType": "CASH-IN",
        "status": "RECEIVED",
        "transactionValue": 1,
        "orderExtendedInfo": {
          "bankName": "",
          "accountNumber": "",
          "branch": "",
          "ispb": "",
          "taxId": "121029810921",
          "name": "joleene@smith.com",
          "BrCode": "00020101021126580014br.gov.bcb.pix0136122ec0ff-9784-4cad-8f96-6044b7eb17385204000053039865802BR5908Account16009SAO PAULO622905257288a47b1b822bdb796f5a4b86304DF34",
          "pixKey": "",
          "pixEndToEndId": "as4d354a3sd543as5d43asd"
        }
      },
      {
        "referenceId": "100000000000022222",
        "orderId": "5a43sd2-4a5s3-d254as32-as3452a-3455as432",
        "channelReferenceId": "00000012121212",
        "createTime": 1624529919000,
        "transactionType": "CASH-OUT",
        "status": "SENT",
        "transactionValue": 1,
        "orderExtendedInfo": {
          "bankName": "",
          "accountNumber": "",
          "branch": "",
          "ispb": "",
          "taxId": "121029810921",
          "name": "joleene@smith.com",
          "BrCode": "",
          "pixKey": "",
          "pixEndToEndId": "as4d354a3sd543as5d43asd"
        }
      }
    ]
  }
}
```

<h3 id="get__order_history-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|user transactions|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[error](#schemaerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized Request|[error](#schemaerror)|

<h3 id="get__order_history-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» sysCd|string|false|none|none|
|» sysMsg|string|false|none|none|
|» biz|object|false|none|none|
|»» bizCd|string|false|none|none|
|»» bizMsg|string|false|none|none|
|»» total|integer|false|none|none|
|»» pageNum|integer|false|none|none|
|»» pageSize|integer|false|none|none|
|»» data|[object]|false|none|none|
|»»» referenceId|string|false|none|Your own order id|
|»»» orderId|string|false|none|Our order id|
|»»» channelReferenceId|string|false|none|Vendor channel|
|»»» createTime|integer(int64)|false|none|epoch date time|
|»»» transactionType|string|false|none|CASH-IN or CASH-OUT|
|»»» status|string|false|none|CASH-IN or CASH-OUT|
|»»» transactionValue|number|false|none|none|
|»»» orderExtendedInfo|object|false|none|none|
|»»»» bankName|string|false|none|The name of bank|
|»»»» accountNumber|string|false|none|Account number of the bank origin or target|
|»»»» branch|string|false|none|branch number of bank origin or target|
|»»»» ispb|string|false|none|SPI number (Brazilian bank GOV id)|
|»»»» taxId|string|false|none|TaxId of sender or receiver|
|»»»» name|string|false|none|Name of sender or receiver|
|»»»» BrCode|string|false|none|BRCode to cash-in ou payed cash-out|
|»»»» pixKey|string|false|none|Pix key to cash-out|
|»»»» pixEndToEndId|string|false|none|End2End cash-in or cash-out (from SPI)|

#### Enumerated Values

|Property|Value|
|---|---|
|transactionType|CASH-IN|
|transactionType|CASH-OUT|
|status|WAITING|
|status|SENT|
|status|RECEIVED|
|status|CANCELED|
|status|FAILED|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## post__order_cash-in

> Code samples

```shell
# You can also use wget
curl -X POST https://api.brazil-qa.coins.xyz/order/cash-in?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b&referenceOrderId=0000000000012909&amount=0 \
  -H 'Accept: application/json' \
  -H 'X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f' \
  -H 'timestamp: 0' \
  -H 'signature: string' \
  -H 'X-COINS-APIKEY: API_KEY'

```

```http
POST https://api.brazil-qa.coins.xyz/order/cash-in?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b&referenceOrderId=0000000000012909&amount=0 HTTP/1.1
Host: api.brazil-qa.coins.xyz
Accept: application/json
X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f
timestamp: 0
signature: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'X-COINS-TRACE-ID':'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp':'0',
  'signature':'string',
  'X-COINS-APIKEY':'API_KEY'
};

fetch('https://api.brazil-qa.coins.xyz/order/cash-in?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b&referenceOrderId=0000000000012909&amount=0',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp' => '0',
  'signature' => 'string',
  'X-COINS-APIKEY' => 'API_KEY'
}

result = RestClient.post 'https://api.brazil-qa.coins.xyz/order/cash-in',
  params: {
  'userId' => 'string',
'referenceOrderId' => 'string',
'amount' => 'number'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-COINS-TRACE-ID': 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp': '0',
  'signature': 'string',
  'X-COINS-APIKEY': 'API_KEY'
}

r = requests.post('https://api.brazil-qa.coins.xyz/order/cash-in', params={
  'userId': '8d65891d-3143-4a1e-9cba-ea3a662e121b',  'referenceOrderId': '0000000000012909',  'amount': '0'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
    'timestamp' => '0',
    'signature' => 'string',
    'X-COINS-APIKEY' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://api.brazil-qa.coins.xyz/order/cash-in', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.brazil-qa.coins.xyz/order/cash-in?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b&referenceOrderId=0000000000012909&amount=0");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-COINS-TRACE-ID": []string{"coins.xyz-9be3-4c8d-8cda-0f9334468c3f"},
        "timestamp": []string{"0"},
        "signature": []string{"string"},
        "X-COINS-APIKEY": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.brazil-qa.coins.xyz/order/cash-in", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /order/cash-in`

*Generates a BRCode for cash in (USER_DATA)*

Generates a BRCode for cash in

<h3 id="post__order_cash-in-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|X-COINS-TRACE-ID|header|string|true|The value should start with the partner ID (e.g. coins.br), and end with UUID|
|userId|query|string|true|Our user Id, generated for us|
|referenceOrderId|query|string|true|Reference partner unique id for orders|
|amount|query|number|true|set 0 if wants to be open for any value|
|timestamp|header|integer(int64)|true|UTC timestamp in ms|
|signature|header|string|true|Signature|

> Example responses

> 200 Response

```json
{
  "sysCd": "BS000000",
  "sysMsg": "OK",
  "biz": {
    "bizCd": "BS000000",
    "bizMsg": "OK",
    "total": 200,
    "pageNum": 2,
    "pageSize": 100,
    "data": {
      "referenceId": "string",
      "orderId": "string",
      "channelReferenceId": "string",
      "createTime": 0,
      "transactionType": "CASH-IN",
      "status": "RECEIVED",
      "transactionValue": 1.3,
      "orderExtendedInfo": {
        "bankName": "GENIAL BANK",
        "accountNumber": "12312233",
        "branch": "0001",
        "ispb": "123123",
        "taxId": "07832426758",
        "name": "Marcos Blauzer",
        "BrCode": "...",
        "pixKey": "",
        "pixEndToEndId": ""
      }
    }
  }
}
```

<h3 id="post__order_cash-in-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|brcode generated|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[error](#schemaerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized Request|[error](#schemaerror)|

<h3 id="post__order_cash-in-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» sysCd|string|false|none|none|
|» sysMsg|string|false|none|none|
|» biz|object|false|none|none|
|»» bizCd|string|false|none|none|
|»» bizMsg|string|false|none|none|
|»» total|integer|false|none|none|
|»» pageNum|integer|false|none|none|
|»» pageSize|integer|false|none|none|
|»» data|object|false|none|none|
|»»» referenceId|string|false|none|Your own order id|
|»»» orderId|string|false|none|Our order id|
|»»» channelReferenceId|string|false|none|Vendor channel|
|»»» createTime|integer(int64)|false|none|epoch date time|
|»»» transactionType|string|false|none|CASH-IN or CASH-OUT|
|»»» status|string|false|none|Status of order|
|»»» transactionValue|number|false|none|none|
|»»» orderExtendedInfo|object|false|none|none|
|»»»» bankName|string|false|none|The name of bank|
|»»»» accountNumber|string|false|none|Account number of the bank origin or target|
|»»»» branch|string|false|none|branch number of bank origin or target|
|»»»» ispb|string|false|none|SPI number (Brazilian bank GOV id)|
|»»»» taxId|string|false|none|TaxId of sender or receiver|
|»»»» name|string|false|none|Name of sender or receiver|
|»»»» BrCode|string|false|none|BRCode to cash-in ou payed cash-out|
|»»»» pixKey|string|false|none|Pix key to cash-out|
|»»»» pixEndToEndId|string|false|none|End2End cash-in or cash-out (from SPI)|

#### Enumerated Values

|Property|Value|
|---|---|
|transactionType|CASH-IN|
|transactionType|CASH-OUT|
|status|WAITING|
|status|SENT|
|status|RECEIVED|
|status|CANCELED|
|status|FAILED|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## get__order_details

> Code samples

```shell
# You can also use wget
curl -X GET https://api.brazil-qa.coins.xyz/order/details?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b&orderId=7288a47b1b822bdb796f5a4b9 \
  -H 'Accept: application/json' \
  -H 'X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f' \
  -H 'timestamp: 0' \
  -H 'signature: string' \
  -H 'X-COINS-APIKEY: API_KEY'

```

```http
GET https://api.brazil-qa.coins.xyz/order/details?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b&orderId=7288a47b1b822bdb796f5a4b9 HTTP/1.1
Host: api.brazil-qa.coins.xyz
Accept: application/json
X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f
timestamp: 0
signature: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'X-COINS-TRACE-ID':'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp':'0',
  'signature':'string',
  'X-COINS-APIKEY':'API_KEY'
};

fetch('https://api.brazil-qa.coins.xyz/order/details?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b&orderId=7288a47b1b822bdb796f5a4b9',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp' => '0',
  'signature' => 'string',
  'X-COINS-APIKEY' => 'API_KEY'
}

result = RestClient.get 'https://api.brazil-qa.coins.xyz/order/details',
  params: {
  'userId' => 'string',
'orderId' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-COINS-TRACE-ID': 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp': '0',
  'signature': 'string',
  'X-COINS-APIKEY': 'API_KEY'
}

r = requests.get('https://api.brazil-qa.coins.xyz/order/details', params={
  'userId': '8d65891d-3143-4a1e-9cba-ea3a662e121b',  'orderId': '7288a47b1b822bdb796f5a4b9'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
    'timestamp' => '0',
    'signature' => 'string',
    'X-COINS-APIKEY' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://api.brazil-qa.coins.xyz/order/details', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.brazil-qa.coins.xyz/order/details?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b&orderId=7288a47b1b822bdb796f5a4b9");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-COINS-TRACE-ID": []string{"coins.xyz-9be3-4c8d-8cda-0f9334468c3f"},
        "timestamp": []string{"0"},
        "signature": []string{"string"},
        "X-COINS-APIKEY": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.brazil-qa.coins.xyz/order/details", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /order/details`

*Order details (USER_DATA)*

Order details

<h3 id="get__order_details-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|X-COINS-TRACE-ID|header|string|true|The value should start with the partner ID (e.g. coins.br), and end with UUID|
|userId|query|string|true|Our user Id, generated for us|
|orderId|query|string|true|Generated id in BRCode generation time|
|timestamp|header|integer(int64)|true|UTC timestamp in ms|
|signature|header|string|true|Signature|

> Example responses

> 200 Response

```json
{
  "sysCd": "BS000000",
  "sysMsg": "OK",
  "biz": {
    "bizCd": "BS000000",
    "bizMsg": "OK",
    "total": 200,
    "pageNum": 2,
    "pageSize": 100,
    "data": {
      "referenceId": "string",
      "orderId": "string",
      "channelReferenceId": "string",
      "createTime": 0,
      "transactionType": "CASH-OUT",
      "status": "WAITING",
      "transactionValue": 1.3,
      "orderExtendedInfo": {
        "bankName": "GENIAL BANK",
        "accountNumber": "12312233",
        "branch": "0001",
        "ispb": "123123",
        "taxId": "07832426758",
        "name": "Marcos Blauzer",
        "BrCode": "...",
        "pixKey": "",
        "pixEndToEndId": ""
      }
    }
  }
}
```

<h3 id="get__order_details-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|brcode generated|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[error](#schemaerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized Request|[error](#schemaerror)|

<h3 id="get__order_details-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» sysCd|string|false|none|none|
|» sysMsg|string|false|none|none|
|» biz|object|false|none|none|
|»» bizCd|string|false|none|none|
|»» bizMsg|string|false|none|none|
|»» total|integer|false|none|none|
|»» pageNum|integer|false|none|none|
|»» pageSize|integer|false|none|none|
|»» data|object|false|none|none|
|»»» referenceId|string|false|none|Your own order id|
|»»» orderId|string|false|none|Our order id|
|»»» channelReferenceId|string|false|none|Vendor channel|
|»»» createTime|integer(int64)|false|none|epoch date time|
|»»» transactionType|string|false|none|CASH-IN or CASH-OUT|
|»»» status|string|false|none|Status of order|
|»»» transactionValue|number|false|none|none|
|»»» orderExtendedInfo|object|false|none|none|
|»»»» bankName|string|false|none|The name of bank|
|»»»» accountNumber|string|false|none|Account number of the bank origin or target|
|»»»» branch|string|false|none|branch number of bank origin or target|
|»»»» ispb|string|false|none|SPI number (Brazilian bank GOV id)|
|»»»» taxId|string|false|none|TaxId of sender or receiver|
|»»»» name|string|false|none|Name of sender or receiver|
|»»»» BrCode|string|false|none|BRCode to cash-in ou payed cash-out|
|»»»» pixKey|string|false|none|Pix key to cash-out|
|»»»» pixEndToEndId|string|false|none|End2End cash-in or cash-out (from SPI)|

#### Enumerated Values

|Property|Value|
|---|---|
|transactionType|CASH-IN|
|transactionType|CASH-OUT|
|status|WAITING|
|status|SENT|
|status|RECEIVED|
|status|CANCELED|
|status|FAILED|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## post__order_cash-out

> Code samples

```shell
# You can also use wget
curl -X POST https://api.brazil-qa.coins.xyz/order/cash-out?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b&referenceOrderId=0000000000012909&amount=0&pixKey=joleene%40smith.com \
  -H 'Accept: application/json' \
  -H 'X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f' \
  -H 'timestamp: 0' \
  -H 'signature: string' \
  -H 'X-COINS-APIKEY: API_KEY'

```

```http
POST https://api.brazil-qa.coins.xyz/order/cash-out?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b&referenceOrderId=0000000000012909&amount=0&pixKey=joleene%40smith.com HTTP/1.1
Host: api.brazil-qa.coins.xyz
Accept: application/json
X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f
timestamp: 0
signature: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'X-COINS-TRACE-ID':'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp':'0',
  'signature':'string',
  'X-COINS-APIKEY':'API_KEY'
};

fetch('https://api.brazil-qa.coins.xyz/order/cash-out?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b&referenceOrderId=0000000000012909&amount=0&pixKey=joleene%40smith.com',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp' => '0',
  'signature' => 'string',
  'X-COINS-APIKEY' => 'API_KEY'
}

result = RestClient.post 'https://api.brazil-qa.coins.xyz/order/cash-out',
  params: {
  'userId' => 'string',
'referenceOrderId' => 'string',
'amount' => 'number',
'pixKey' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-COINS-TRACE-ID': 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp': '0',
  'signature': 'string',
  'X-COINS-APIKEY': 'API_KEY'
}

r = requests.post('https://api.brazil-qa.coins.xyz/order/cash-out', params={
  'userId': '8d65891d-3143-4a1e-9cba-ea3a662e121b',  'referenceOrderId': '0000000000012909',  'amount': '0',  'pixKey': 'joleene@smith.com'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
    'timestamp' => '0',
    'signature' => 'string',
    'X-COINS-APIKEY' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://api.brazil-qa.coins.xyz/order/cash-out', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.brazil-qa.coins.xyz/order/cash-out?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b&referenceOrderId=0000000000012909&amount=0&pixKey=joleene%40smith.com");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-COINS-TRACE-ID": []string{"coins.xyz-9be3-4c8d-8cda-0f9334468c3f"},
        "timestamp": []string{"0"},
        "signature": []string{"string"},
        "X-COINS-APIKEY": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.brazil-qa.coins.xyz/order/cash-out", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /order/cash-out`

*Cash out to a PIX key (USER_DATA)*

Cash out to a PIX key

<h3 id="post__order_cash-out-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|X-COINS-TRACE-ID|header|string|true|The value should start with the partner ID (e.g. coins.br), and end with UUID|
|userId|query|string|true|Our user Id, generated for us|
|referenceOrderId|query|string|true|Reference partner unique id for orders|
|amount|query|number|true|set 0 if wants to be open for any value|
|pixKey|query|string|true|PIX key (email, tax id, phone number, EMV)|
|timestamp|header|integer(int64)|true|UTC timestamp in ms|
|signature|header|string|true|Signature|

> Example responses

> 200 Response

```json
{
  "sysCd": "BS000000",
  "sysMsg": "OK",
  "biz": {
    "bizCd": "BS000000",
    "bizMsg": "OK",
    "total": 200,
    "pageNum": 2,
    "pageSize": 100,
    "data": {
      "referenceId": "string",
      "orderId": "string",
      "channelReferenceId": "string",
      "createTime": 0,
      "transactionType": "CASH-OUT",
      "status": "WAITING",
      "transactionValue": 1.3,
      "orderExtendedInfo": {
        "bankName": "GENIAL BANK",
        "accountNumber": "12312233",
        "branch": "0001",
        "ispb": "123123",
        "taxId": "07832426758",
        "name": "Marcos Blauzer",
        "BrCode": "...",
        "pixKey": "",
        "pixEndToEndId": ""
      }
    }
  }
}
```

<h3 id="post__order_cash-out-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|brcode generated|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[error](#schemaerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized Request|[error](#schemaerror)|

<h3 id="post__order_cash-out-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» sysCd|string|false|none|none|
|» sysMsg|string|false|none|none|
|» biz|object|false|none|none|
|»» bizCd|string|false|none|none|
|»» bizMsg|string|false|none|none|
|»» total|integer|false|none|none|
|»» pageNum|integer|false|none|none|
|»» pageSize|integer|false|none|none|
|»» data|object|false|none|none|
|»»» referenceId|string|false|none|Your own order id|
|»»» orderId|string|false|none|Our order id|
|»»» channelReferenceId|string|false|none|Vendor channel|
|»»» createTime|integer(int64)|false|none|epoch date time|
|»»» transactionType|string|false|none|CASH-IN or CASH-OUT|
|»»» status|string|false|none|Status of order|
|»»» transactionValue|number|false|none|none|
|»»» orderExtendedInfo|object|false|none|none|
|»»»» bankName|string|false|none|The name of bank|
|»»»» accountNumber|string|false|none|Account number of the bank origin or target|
|»»»» branch|string|false|none|branch number of bank origin or target|
|»»»» ispb|string|false|none|SPI number (Brazilian bank GOV id)|
|»»»» taxId|string|false|none|TaxId of sender or receiver|
|»»»» name|string|false|none|Name of sender or receiver|
|»»»» BrCode|string|false|none|BRCode to cash-in ou payed cash-out|
|»»»» pixKey|string|false|none|Pix key to cash-out|
|»»»» pixEndToEndId|string|false|none|End2End cash-in or cash-out (from SPI)|

#### Enumerated Values

|Property|Value|
|---|---|
|transactionType|CASH-IN|
|transactionType|CASH-OUT|
|status|WAITING|
|status|SENT|
|status|RECEIVED|
|status|CANCELED|
|status|FAILED|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## get__pix_key

> Code samples

```shell
# You can also use wget
curl -X GET https://api.brazil-qa.coins.xyz/pix/key?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b&pixKey=joleene%40smith.com \
  -H 'Accept: application/json' \
  -H 'X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f' \
  -H 'timestamp: 0' \
  -H 'signature: string' \
  -H 'X-COINS-APIKEY: API_KEY'

```

```http
GET https://api.brazil-qa.coins.xyz/pix/key?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b&pixKey=joleene%40smith.com HTTP/1.1
Host: api.brazil-qa.coins.xyz
Accept: application/json
X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f
timestamp: 0
signature: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'X-COINS-TRACE-ID':'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp':'0',
  'signature':'string',
  'X-COINS-APIKEY':'API_KEY'
};

fetch('https://api.brazil-qa.coins.xyz/pix/key?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b&pixKey=joleene%40smith.com',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp' => '0',
  'signature' => 'string',
  'X-COINS-APIKEY' => 'API_KEY'
}

result = RestClient.get 'https://api.brazil-qa.coins.xyz/pix/key',
  params: {
  'userId' => 'string',
'pixKey' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-COINS-TRACE-ID': 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp': '0',
  'signature': 'string',
  'X-COINS-APIKEY': 'API_KEY'
}

r = requests.get('https://api.brazil-qa.coins.xyz/pix/key', params={
  'userId': '8d65891d-3143-4a1e-9cba-ea3a662e121b',  'pixKey': 'joleene@smith.com'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
    'timestamp' => '0',
    'signature' => 'string',
    'X-COINS-APIKEY' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://api.brazil-qa.coins.xyz/pix/key', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.brazil-qa.coins.xyz/pix/key?userId=8d65891d-3143-4a1e-9cba-ea3a662e121b&pixKey=joleene%40smith.com");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-COINS-TRACE-ID": []string{"coins.xyz-9be3-4c8d-8cda-0f9334468c3f"},
        "timestamp": []string{"0"},
        "signature": []string{"string"},
        "X-COINS-APIKEY": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.brazil-qa.coins.xyz/pix/key", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /pix/key`

*Check a external pix key data for cash out (USER_DATA)*

Check a pix key data

<h3 id="get__pix_key-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|X-COINS-TRACE-ID|header|string|true|The value should start with the partner ID (e.g. coins.br), and end with UUID|
|userId|query|string|true|Our user Id, generated for us|
|pixKey|query|string|true|PIX key (email, tax id, phone number, EMV)|
|timestamp|header|integer(int64)|true|UTC timestamp in ms|
|signature|header|string|true|Signature|

> Example responses

> 200 Response

```json
{
  "sysCd": "BS000000",
  "sysMsg": "OK",
  "biz": {
    "bizCd": "BS000000",
    "bizMsg": "OK",
    "data": {
      "keyType": "EMAIL",
      "key": "marciosfalsin@gmail.com",
      "accountHolderName": "Marcio Sfalsin",
      "accountHoldertaxId": "07832428759",
      "status": "ACTIVE"
    }
  }
}
```

<h3 id="get__pix_key-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|brcode status|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[error](#schemaerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized Request|[error](#schemaerror)|

<h3 id="get__pix_key-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» sysCd|string|false|none|none|
|» sysMsg|string|false|none|none|
|» biz|object|false|none|none|
|»» bizCd|string|false|none|none|
|»» bizMsg|string|false|none|none|
|»» data|object|false|none|none|
|»»» keyType|string|false|none|EMV,EMAIL,TAX_ID,PHONE_NUMBER|
|»»» key|string|false|none|receiver key|
|»»» accountHolderName|string|false|none|name from account holder|
|»»» accountHoldertaxId|string|false|none|tax id from account holder|
|»»» status|string|false|none|ACTIVE or INACTIVE|

#### Enumerated Values

|Property|Value|
|---|---|
|keyType|EMV|
|keyType|EMAIL|
|keyType|TAX_ID|
|keyType|PHONE_NUMBER|
|status|ACTIVE|
|status|INACTIVE|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="coins-brazil-public-spot-api-webhook">WebHook</h1>

WebHooks management

## post__webhook_confirm

> Code samples

```shell
# You can also use wget
curl -X POST https://api.brazil-qa.coins.xyz/webhook/confirm?webHookType=APPROVED_KYC&orderId=7288a47b1b822bdb796f5a4b9 \
  -H 'Accept: application/json' \
  -H 'X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f' \
  -H 'timestamp: 0' \
  -H 'signature: string' \
  -H 'X-COINS-APIKEY: API_KEY'

```

```http
POST https://api.brazil-qa.coins.xyz/webhook/confirm?webHookType=APPROVED_KYC&orderId=7288a47b1b822bdb796f5a4b9 HTTP/1.1
Host: api.brazil-qa.coins.xyz
Accept: application/json
X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f
timestamp: 0
signature: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'X-COINS-TRACE-ID':'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp':'0',
  'signature':'string',
  'X-COINS-APIKEY':'API_KEY'
};

fetch('https://api.brazil-qa.coins.xyz/webhook/confirm?webHookType=APPROVED_KYC&orderId=7288a47b1b822bdb796f5a4b9',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp' => '0',
  'signature' => 'string',
  'X-COINS-APIKEY' => 'API_KEY'
}

result = RestClient.post 'https://api.brazil-qa.coins.xyz/webhook/confirm',
  params: {
  'webHookType' => 'string',
'orderId' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-COINS-TRACE-ID': 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp': '0',
  'signature': 'string',
  'X-COINS-APIKEY': 'API_KEY'
}

r = requests.post('https://api.brazil-qa.coins.xyz/webhook/confirm', params={
  'webHookType': 'APPROVED_KYC',  'orderId': '7288a47b1b822bdb796f5a4b9'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
    'timestamp' => '0',
    'signature' => 'string',
    'X-COINS-APIKEY' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://api.brazil-qa.coins.xyz/webhook/confirm', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.brazil-qa.coins.xyz/webhook/confirm?webHookType=APPROVED_KYC&orderId=7288a47b1b822bdb796f5a4b9");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-COINS-TRACE-ID": []string{"coins.xyz-9be3-4c8d-8cda-0f9334468c3f"},
        "timestamp": []string{"0"},
        "signature": []string{"string"},
        "X-COINS-APIKEY": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.brazil-qa.coins.xyz/webhook/confirm", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /webhook/confirm`

*Confirm an event*

As you can, confirm the event receveid to stop the retries

<h3 id="post__webhook_confirm-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|X-COINS-TRACE-ID|header|string|true|The value should start with the partner ID (e.g. coins.br), and end with UUID|
|webHookType|query|string|true|webhook types|
|orderId|query|string|true|Generated id in BRCode generation time|
|timestamp|header|integer(int64)|true|UTC timestamp in ms|
|signature|header|string|true|Signature|

#### Enumerated Values

|Parameter|Value|
|---|---|
|webHookType|NEW_KYC|
|webHookType|APPROVED_KYC|
|webHookType|REPROVED_KYC|
|webHookType|UPGRADED_KYC|
|webHookType|PIX_IN|
|webHookType|PIX_OUT|

> Example responses

> 200 Response

```json
{
  "sysCd": "BS000000",
  "sysMsg": "OK",
  "biz": {
    "bizCd": "BS000000",
    "bizMsg": "OK",
    "data": {
      "orderId": "123123123123123",
      "webHookType": "APPROVED_KYC",
      "confirmed": true
    }
  }
}
```

<h3 id="post__webhook_confirm-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|confirmed event|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[error](#schemaerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized Request|[error](#schemaerror)|

<h3 id="post__webhook_confirm-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» sysCd|string|false|none|none|
|» sysMsg|string|false|none|none|
|» biz|object|false|none|none|
|»» bizCd|string|false|none|none|
|»» bizMsg|string|false|none|none|
|»» data|object|false|none|none|
|»»» orderId|string|false|none|none|
|»»» webHookType|string|false|none|none|
|»»» confirmed|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## put__webhook

> Code samples

```shell
# You can also use wget
curl -X PUT https://api.brazil-qa.coins.xyz/webhook?webHookType=APPROVED_KYC \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f' \
  -H 'timestamp: 0' \
  -H 'signature: string' \
  -H 'X-COINS-APIKEY: API_KEY'

```

```http
PUT https://api.brazil-qa.coins.xyz/webhook?webHookType=APPROVED_KYC HTTP/1.1
Host: api.brazil-qa.coins.xyz
Content-Type: application/json
Accept: application/json
X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f
timestamp: 0
signature: string

```

```javascript
const inputBody = '{
  "callbackUrl": "https://myserver.com/send/callback/here"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-COINS-TRACE-ID':'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp':'0',
  'signature':'string',
  'X-COINS-APIKEY':'API_KEY'
};

fetch('https://api.brazil-qa.coins.xyz/webhook?webHookType=APPROVED_KYC',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp' => '0',
  'signature' => 'string',
  'X-COINS-APIKEY' => 'API_KEY'
}

result = RestClient.put 'https://api.brazil-qa.coins.xyz/webhook',
  params: {
  'webHookType' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'X-COINS-TRACE-ID': 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp': '0',
  'signature': 'string',
  'X-COINS-APIKEY': 'API_KEY'
}

r = requests.put('https://api.brazil-qa.coins.xyz/webhook', params={
  'webHookType': 'APPROVED_KYC'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
    'timestamp' => '0',
    'signature' => 'string',
    'X-COINS-APIKEY' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','https://api.brazil-qa.coins.xyz/webhook', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.brazil-qa.coins.xyz/webhook?webHookType=APPROVED_KYC");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "X-COINS-TRACE-ID": []string{"coins.xyz-9be3-4c8d-8cda-0f9334468c3f"},
        "timestamp": []string{"0"},
        "signature": []string{"string"},
        "X-COINS-APIKEY": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://api.brazil-qa.coins.xyz/webhook", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /webhook`

*Set a url to webhook*

Set a url to webhook

> Body parameter

```json
{
  "callbackUrl": "https://myserver.com/send/callback/here"
}
```

<h3 id="put__webhook-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|X-COINS-TRACE-ID|header|string|true|The value should start with the partner ID (e.g. coins.br), and end with UUID|
|webHookType|query|string|true|webhook types|
|timestamp|header|integer(int64)|true|UTC timestamp in ms|
|signature|header|string|true|Signature|
|body|body|object|true|none|
|» callbackUrl|body|string(uri)|true|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|webHookType|NEW_KYC|
|webHookType|APPROVED_KYC|
|webHookType|REPROVED_KYC|
|webHookType|UPGRADED_KYC|
|webHookType|PIX_IN|
|webHookType|PIX_OUT|

> Example responses

> 200 Response

```json
{
  "sysCd": "BS000000",
  "sysMsg": "OK",
  "biz": {
    "bizCd": "BS000000",
    "bizMsg": "OK",
    "data": {
      "webHookType": "APPROVED_KYC",
      "url": "https://myserver.com/send/callback/here"
    }
  }
}
```

<h3 id="put__webhook-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|kyc start|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[error](#schemaerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized Request|[error](#schemaerror)|

<h3 id="put__webhook-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» sysCd|string|false|none|none|
|» sysMsg|string|false|none|none|
|» biz|object|false|none|none|
|»» bizCd|string|false|none|none|
|»» bizMsg|string|false|none|none|
|»» data|object|false|none|none|
|»»» webHookType|string|false|none|none|
|»»» url|string|false|none|none|

### Callbacks

#### onConfirmedOrder

**{$request.body.callbackUrl}**

## put__webhook

> Code samples

```shell
# You can also use wget
curl -X PUT https://api.brazil-qa.coins.xyz/webhook \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT https://api.brazil-qa.coins.xyz/webhook HTTP/1.1
Host: api.brazil-qa.coins.xyz
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "sysCd": "00000000",
  "sysMsg": "OK",
  "biz": {
    "bizCd": "00000000",
    "bizMsg": "OK",
    "subscriptionType": "PIX_IN",
    "webhookCallTime": 1624529919000,
    "data": {
      "referenceId": "123123123123123",
      "channelReferenceId": "123123123123123",
      "orderId": "123123123123123",
      "settlementTime": 1624529919000,
      "status": "successed",
      "amount": "100",
      "currency": "BRL",
      "fee": "10",
      "referenceUserId": "123123123123123"
    }
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('https://api.brazil-qa.coins.xyz/webhook',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'https://api.brazil-qa.coins.xyz/webhook',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('https://api.brazil-qa.coins.xyz/webhook', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','https://api.brazil-qa.coins.xyz/webhook', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.brazil-qa.coins.xyz/webhook");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://api.brazil-qa.coins.xyz/webhook", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /webhook`

> Body parameter

```json
{
  "sysCd": "00000000",
  "sysMsg": "OK",
  "biz": {
    "bizCd": "00000000",
    "bizMsg": "OK",
    "subscriptionType": "PIX_IN",
    "webhookCallTime": 1624529919000,
    "data": {
      "referenceId": "123123123123123",
      "channelReferenceId": "123123123123123",
      "orderId": "123123123123123",
      "settlementTime": 1624529919000,
      "status": "successed",
      "amount": "100",
      "currency": "BRL",
      "fee": "10",
      "referenceUserId": "123123123123123"
    }
  }
}
```

<h3 id="put__webhook-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|subscription payload|
|» sysCd|body|string|false|none|
|» sysMsg|body|string|false|none|
|» biz|body|object|false|none|
|»» bizCd|body|string|false|none|
|»» bizMsg|body|string|false|none|
|»» subscriptionType|body|string|false|none|
|»» webhookCallTime|body|integer(int64)|false|epoch date time|
|»» data|body|object|false|none|
|»»» referenceId|body|string|false|none|
|»»» channelReferenceId|body|string|false|none|
|»»» orderId|body|string|false|none|
|»»» settlementTime|body|integer(int64)|false|epoch date time|
|»»» status|body|string|false|none|
|»»» amount|body|string|false|none|
|»»» currency|body|string|false|none|
|»»» fee|body|string|false|none|
|»»» referenceUserId|body|string|false|none|

> Example responses

> 200 Response

```json
{
  "sysCd": "00000000",
  "sysMsg": "OK",
  "biz": {
    "bizCd": "00000000",
    "bizMsg": "OK",
    "subscriptionType": "PIX_IN",
    "webhookReceivedTime": 1624529919000,
    "data": {}
  }
}
```

<h3 id="put__webhook-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Your server implementation should return this HTTP status code
if the data was received successfully|Inline|

<h3 id="put__webhook-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» sysCd|string|false|none|none|
|» sysMsg|string|false|none|none|
|» biz|object|false|none|none|
|»» bizCd|string|false|none|none|
|»» bizMsg|string|false|none|none|
|»» subscriptionType|string|false|none|none|
|»» webhookReceivedTime|integer(int64)|false|none|epoch date time|
|»» data|object|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## get__webhook

> Code samples

```shell
# You can also use wget
curl -X GET https://api.brazil-qa.coins.xyz/webhook \
  -H 'Accept: application/json' \
  -H 'X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f' \
  -H 'timestamp: 0' \
  -H 'signature: string' \
  -H 'X-COINS-APIKEY: API_KEY'

```

```http
GET https://api.brazil-qa.coins.xyz/webhook HTTP/1.1
Host: api.brazil-qa.coins.xyz
Accept: application/json
X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f
timestamp: 0
signature: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'X-COINS-TRACE-ID':'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp':'0',
  'signature':'string',
  'X-COINS-APIKEY':'API_KEY'
};

fetch('https://api.brazil-qa.coins.xyz/webhook',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp' => '0',
  'signature' => 'string',
  'X-COINS-APIKEY' => 'API_KEY'
}

result = RestClient.get 'https://api.brazil-qa.coins.xyz/webhook',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-COINS-TRACE-ID': 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp': '0',
  'signature': 'string',
  'X-COINS-APIKEY': 'API_KEY'
}

r = requests.get('https://api.brazil-qa.coins.xyz/webhook', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
    'timestamp' => '0',
    'signature' => 'string',
    'X-COINS-APIKEY' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://api.brazil-qa.coins.xyz/webhook', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.brazil-qa.coins.xyz/webhook");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-COINS-TRACE-ID": []string{"coins.xyz-9be3-4c8d-8cda-0f9334468c3f"},
        "timestamp": []string{"0"},
        "signature": []string{"string"},
        "X-COINS-APIKEY": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.brazil-qa.coins.xyz/webhook", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /webhook`

*List webhooks*

List webhooks

<h3 id="get__webhook-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|X-COINS-TRACE-ID|header|string|true|The value should start with the partner ID (e.g. coins.br), and end with UUID|
|timestamp|header|integer(int64)|true|UTC timestamp in ms|
|signature|header|string|true|Signature|

> Example responses

> 200 Response

```json
{
  "sysCd": "BS000000",
  "sysMsg": "OK",
  "biz": {
    "bizCd": "BS000000",
    "bizMsg": "OK",
    "data": [
      {
        "webHookType": "APPROVED_KYC",
        "url": "http://www.anycallbackendpoint.com/webhook"
      }
    ]
  }
}
```

<h3 id="get__webhook-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|kyc list|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[error](#schemaerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized Request|[error](#schemaerror)|

<h3 id="get__webhook-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» sysCd|string|false|none|none|
|» sysMsg|string|false|none|none|
|» biz|object|false|none|none|
|»» bizCd|string|false|none|none|
|»» bizMsg|string|false|none|none|
|»» data|[object]|false|none|none|
|»»» webHookType|string|false|none|none|
|»»» url|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## delete__webhook

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.brazil-qa.coins.xyz/webhook?webHookType=APPROVED_KYC \
  -H 'Accept: application/json' \
  -H 'X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f' \
  -H 'timestamp: 0' \
  -H 'signature: string' \
  -H 'X-COINS-APIKEY: API_KEY'

```

```http
DELETE https://api.brazil-qa.coins.xyz/webhook?webHookType=APPROVED_KYC HTTP/1.1
Host: api.brazil-qa.coins.xyz
Accept: application/json
X-COINS-TRACE-ID: coins.xyz-9be3-4c8d-8cda-0f9334468c3f
timestamp: 0
signature: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'X-COINS-TRACE-ID':'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp':'0',
  'signature':'string',
  'X-COINS-APIKEY':'API_KEY'
};

fetch('https://api.brazil-qa.coins.xyz/webhook?webHookType=APPROVED_KYC',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp' => '0',
  'signature' => 'string',
  'X-COINS-APIKEY' => 'API_KEY'
}

result = RestClient.delete 'https://api.brazil-qa.coins.xyz/webhook',
  params: {
  'webHookType' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-COINS-TRACE-ID': 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
  'timestamp': '0',
  'signature': 'string',
  'X-COINS-APIKEY': 'API_KEY'
}

r = requests.delete('https://api.brazil-qa.coins.xyz/webhook', params={
  'webHookType': 'APPROVED_KYC'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'X-COINS-TRACE-ID' => 'coins.xyz-9be3-4c8d-8cda-0f9334468c3f',
    'timestamp' => '0',
    'signature' => 'string',
    'X-COINS-APIKEY' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','https://api.brazil-qa.coins.xyz/webhook', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.brazil-qa.coins.xyz/webhook?webHookType=APPROVED_KYC");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-COINS-TRACE-ID": []string{"coins.xyz-9be3-4c8d-8cda-0f9334468c3f"},
        "timestamp": []string{"0"},
        "signature": []string{"string"},
        "X-COINS-APIKEY": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.brazil-qa.coins.xyz/webhook", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /webhook`

*Remove webhooks*

Remove webhooks

<h3 id="delete__webhook-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|X-COINS-TRACE-ID|header|string|true|The value should start with the partner ID (e.g. coins.br), and end with UUID|
|webHookType|query|string|true|webhook types|
|timestamp|header|integer(int64)|true|UTC timestamp in ms|
|signature|header|string|true|Signature|

#### Enumerated Values

|Parameter|Value|
|---|---|
|webHookType|NEW_KYC|
|webHookType|APPROVED_KYC|
|webHookType|REPROVED_KYC|
|webHookType|UPGRADED_KYC|
|webHookType|PIX_IN|
|webHookType|PIX_OUT|

> Example responses

> 200 Response

```json
{
  "sysCd": "BS000000",
  "sysMsg": "OK",
  "biz": {
    "bizCd": "BS000000",
    "bizMsg": "OK",
    "data": {}
  }
}
```

<h3 id="delete__webhook-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|kyc list|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[error](#schemaerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized Request|[error](#schemaerror)|

<h3 id="delete__webhook-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» sysCd|string|false|none|none|
|» sysMsg|string|false|none|none|
|» biz|object|false|none|none|
|»» bizCd|string|false|none|none|
|»» bizMsg|string|false|none|none|
|»» data|object|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

# Schemas

<h2 id="tocS_error">error</h2>
<!-- backwards compatibility -->
<a id="schemaerror"></a>
<a id="schema_error"></a>
<a id="tocSerror"></a>
<a id="tocserror"></a>

```json
{
  "code": 0,
  "msg": "error message"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|integer(int64)|true|none|Error code|
|msg|string|true|none|Error message|

