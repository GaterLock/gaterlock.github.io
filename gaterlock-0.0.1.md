---
title: GaterLock v0.0.1
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

<h1 id="gaterlock">GaterLock v0.0.1</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

GaterLock Backend API

Base URLs:

* <a href="http://localhost:{port}/{version}">http://localhost:{port}/{version}</a>

    * **port** -  Default: 3000

        * 3000

    * **version** -  Default: v1

        * v1

Email: <a href="mailto:nmartins10@gmail.com">Nuno Martins</a> Web: <a href="https://ngmmartins.github.io">Nuno Martins</a> 

<h1 id="gaterlock-organization">organization</h1>

## searchOrganizations

<a id="opIdsearchOrganizations"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:{port}/{version}/organization \
  -H 'Accept: application/json' \
  -H 'Content-Type: application/json'

```

```http
GET http://localhost:{port}/{version}/organization HTTP/1.1
Host: localhost
Accept: application/json
Content-Type: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Content-Type':'application/json'
};

fetch('http://localhost:{port}/{version}/organization',
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
  'Content-Type' => 'application/json'
}

result = RestClient.get 'http://localhost:{port}/{version}/organization',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Content-Type': 'application/json'
}

r = requests.get('http://localhost:{port}/{version}/organization', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Content-Type' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:{port}/{version}/organization', array(
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
URL obj = new URL("http://localhost:{port}/{version}/organization");
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
        "Content-Type": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:{port}/{version}/organization", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /organization`

*Search organizations*

<h3 id="searchorganizations-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Content-Type|header|string|false|none|
|status|query|string|false|Status to filter by, if not provided all status are considered|

> Example responses

> 200 Response

```json
{
  "id": 1,
  "name": "My Company",
  "businessName": "My Super Company",
  "address": {
    "line1": "Avenida da República",
    "line2": "Nº 458, 2ºEsq",
    "city": "Lisboa",
    "state": "Lisboa",
    "postalCode": "1000-427",
    "countryCode": 620
  }
}
```

<h3 id="searchorganizations-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of organizations|[Organization](#schemaorganization)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[Error](#schemaerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_Organization">Organization</h2>
<!-- backwards compatibility -->
<a id="schemaorganization"></a>
<a id="schema_Organization"></a>
<a id="tocSorganization"></a>
<a id="tocsorganization"></a>

```json
{
  "id": 1,
  "name": "My Company",
  "businessName": "My Super Company",
  "address": {
    "line1": "Avenida da República",
    "line2": "Nº 458, 2ºEsq",
    "city": "Lisboa",
    "state": "Lisboa",
    "postalCode": "1000-427",
    "countryCode": 620
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(uint32)|true|none|none|
|name|string|true|none|none|
|businessName|string|true|none|none|
|address|[Address](#schemaaddress)|false|none|none|

<h2 id="tocS_Address">Address</h2>
<!-- backwards compatibility -->
<a id="schemaaddress"></a>
<a id="schema_Address"></a>
<a id="tocSaddress"></a>
<a id="tocsaddress"></a>

```json
{
  "line1": "Avenida da República",
  "line2": "Nº 458, 2ºEsq",
  "city": "Lisboa",
  "state": "Lisboa",
  "postalCode": "1000-427",
  "countryCode": 620
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|line1|string|false|none|none|
|line2|string|false|none|none|
|city|string|false|none|none|
|state|string|false|none|none|
|postalCode|string|false|none|none|
|countryCode|integer(int64)|false|none|none|

<h2 id="tocS_Error">Error</h2>
<!-- backwards compatibility -->
<a id="schemaerror"></a>
<a id="schema_Error"></a>
<a id="tocSerror"></a>
<a id="tocserror"></a>

```json
{
  "timestamp": "2019-08-24T14:15:22Z",
  "status": 0,
  "error": "string",
  "message": "string",
  "path": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|timestamp|string(date-time)|true|none|none|
|status|integer(int32)|true|none|none|
|error|string|true|none|none|
|message|string|true|none|none|
|path|string|true|none|none|

