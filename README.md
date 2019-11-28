Aliyun API Gateway SDK for Node.js Pro

## Installation

>原来的阿里云的node.js网关的sdk依赖于httpx模块，在vue项目中使用会有小问题
>把httpx 修改为 api-gateway-httpx（只发布在Npm官网）


```sh
$ # save into package.json dependencies with -S
$ npm install api-gateway-http -S
```

## Usage

The SDK contains Simple client(authrozied by appcode) and Normal client(authrozied by appid & appsecret).

### Simple client

```js
'use strict';

const SimpleClient = require('aliyun-api-gateway').SimpleClient;
const client = new SimpleClient('YOUR_APP_CODE');

async function post() {
  var url = 'http://apiqingdaohttps.foundai.com/test1234';

  var result = await client.post(url, {
    data: {
      'testtest': 'query1Value'
    },
    headers: {
      accept: 'application/json'
    }
  });

  console.log(JSON.stringify(result));
}

post().catch((err) => {
  console.log(err.stack);
});
```

### Client (recommend)

```js
'use strict';

const Client = require('aliyun-api-gateway').Client;
const client = new Client('YOUR_APP_KEY','YOUR_APP_SECRET');

async function post() {
  var url = 'http://apiqingdaohttps.foundai.com/test1234';

  var result = await client.post(url, {
    data: {
      'testtest': 'query1Value'
    },
    headers: {
      accept: 'application/json'
    }
  });

  console.log(JSON.stringify(result));
}

post().catch((err) => {
  console.log(err.stack);
});
```

## Question?

Please submit an issue.

