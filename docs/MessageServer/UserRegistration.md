# User Registration
## Introduction
First thing a user has to do is to register on a message server, so he's able to receive messages from other users. The registration on a message server requires that a RSA key pair which will be assigned to a new generated user id.


## Description
To register a new user on a message server send a POST request to `/api/v1/user`.

The attribute values that must be set to successfully create a user are:

| Name | Type   | Description                  | Required |
| ---- | ------ | ---------------------------- | -------- |
| key  | string | A pem encoded RSA key (pkcs1) | true     |


The result will be returned as a JSON object containing the attributes:

| Name         | Type   | Description                                                |
| ------------ | ------ | ---------------------------------------------------------- |
| user_id      | string | The unique alphanumeric identifier of the new generated user |

## Examples

### Curl
```bash
curl -X POST -H 'Content-Type: application/json' -d '{"key":"-----BEGIN RSA PUBLIC KEY-----\nMIIBCgKCAQEAxjTHr1pp+UqJZkI3ebBcIk..."}'"https://message.pigeon.io/api/v1/user"
```

### Node.js
```nodejs
var request = require('request');

var data = {
  key: '-----BEGIN RSA PUBLIC KEY-----\nMIIBCgKCAQEAxjTHr1pp+UqJZkI3ebBcIk...'
};

var options = {
  method: 'POST',
  url: 'https://message.pigeon.io/api/v1/user',
  headers: {
    'Content-Type': 'application/json'
  },
  json: data
};

var callback = function(error, response, body) {
  if (error) {
    console.error(error);
    return;
  }

  var user = JSON.parse(JSON.stringify(body));
  console.log(user);
};

request(options, callback);
```
