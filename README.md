
## Use-cases

- API for a Web Application
- API for a Mobile Application

## Setup

```bash
npm install
```

## Deploy

In order to deploy the endpoint simply run

```bash
serverless deploy
```

The expected result should be similar to:

```bash
endpoints:
  POST - https://fxg06m3rz8.execute-api.us-east-1.amazonaws.com/dev/user
  GET - https://fxg06m3rz8.execute-api.us-east-1.amazonaws.com/dev/user
  GET - https://fxg06m3rz8.execute-api.us-east-1.amazonaws.com/dev/user/{id}
  PUT - https://fxg06m3rz8.execute-api.us-east-1.amazonaws.com/dev/user/{id}
  DELETE - https://fxg06m3rz8.execute-api.us-east-1.amazonaws.com/dev/user/{id}
```

## Usage

You can create, retrieve, update, or delete user:

### Create a user body parameter

```
{
	"text":"hello 123"
}
```

### List all user

```bash
curl https://fxg06m3rz8.execute-api.us-east-1.amazonaws.com/dev/user
```

Example output:
```bash
[
    {
        "createdAt": 1518636121359,
        "text": "hello world",
        "id": "55128100-11bc-11e8-be4c-c900062311df",
        "updatedAt": 1518636121359
    },
    {
        "createdAt": 1518637021101,
        "text": "hello 123",
        "id": "6d5c15d0-11be-11e8-9e1c-b326b5f13648",
        "updatedAt": 1518637021101
    }
]%
```

### Get one User

```bash
# Replace the <id> part with a real id from your user table
curl https://fxg06m3rz8.execute-api.us-east-1.amazonaws.com/dev/user/<id>
```

Example Result:
```bash
{
    "createdAt": 1518636180942,
    "text": "hello delhi",
    "id": "7895fee0-11bc-11e8-be4c-c900062311df",
    "updatedAt": 1518636180942
}%
```

### Update a User

```bash
# Replace the <id> part with a real id from your user table
curl -X PUT  https://fxg06m3rz8.execute-api.us-east-1.amazonaws.com/dev/user/<id> --data '{ "text": "Learn Serverless" }'
```

Example Result:
```bash
{
	"text":"new one"
}%
```

### Delete a User

```bash
# Replace the <id> part with a real id from your user table
curl -X DELETE https://fxg06m3rz8.execute-api.us-east-1.amazonaws.com/dev/user/<id>

Example Result:
```bash
{
    "message": "user deleted successfully"
}%
```