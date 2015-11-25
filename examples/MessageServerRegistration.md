## Message Server Registration

The following code sample codes demonstrate how to register a new user on a message server.

### Curl
```bash
curl -X POST -H 'Content-Type: application/json' -d '{"key":"-----BEGIN RSA PUBLIC KEY-----\nMIIBCgKCAQEAxjTHr1pp+UqJZkI3ebBcIk..."}'"https://message.pigeon.io/api/v1/user"
```

### Javascript
```javascript
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
