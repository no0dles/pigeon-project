## Message Server
### Introduction
A message server is 

The job a message server is to accept new users registrations, receive and validate incomming messages and store them until they expire or the user fetches them.

###Docs

**[Users](./UserRegistration.md)**

**[Access Tokens](./AccessTokens.md)**

**[Messages](./SendingMessages.md)**



### How do I generate a access token?

To generate a new accees token from a message server send a POST request to `/api/v1/token`.

The attribute values that must be set to successfully create a access token are:

| Name      | Type   | Description | Required |
| --------- | ------ | ----------- | -------- |
| user_id    | string | The user ID of the retriving user | true |
| date       | string | The creation date of the request | true |
| validity   | number | The maximum time in seconds until the request expires | true |
| signature  | string | The signature of the request object generated with the private key of the user | true |

The result will be returned as a JSON object containing the attributes:

| Name      | Type   | Description |
| --------- | ------ | ----------- |
| token    | string | The generated access token |

### How do I revoke a access token?

### How do I revoke a user?

### How do I host a message server?

## Message

### Message Type Identifier

| Id  | Description |
| --- | ----------- |
| 1   | [Raw data]() |
| 2   | [Raw message]() |
| 3   | [Access token request]() |

#### Raw data


#### Raw message

```
last_id: string
name: string
content: string
```

