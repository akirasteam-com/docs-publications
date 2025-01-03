Author: Loïc V.
Date: 02/01/2025

# AuthTool API Documentation

### Introduction
This document provides an example of how to use the AuthTool API. The API allows you to validate tokens, retrieve login statistics, and authenticate users.

### Base URL
The base URL for the API is:
> `https://api.akirasteam.com/auth/2`

### Endpoints
- 1. Validate Token

Validates a fiven token and returns user information based on the specified scope.

#### Endpoints :
```
GET /?action=validate_token&app_id={app_id}&token={token}
```

#### Parameters :
- `app_id` (required): The application ID
- `token` (required): The token to be validated

#### Reponse :
```
{
    "status": "success",
    "message": "Token validated",
    "data": {
        "user": {
            "id": "user_id",
            "name": "user_name",
            "email": "user_email",
            "avatar": "https://app.akirasteam.com/uploads/pdp_default.png"
        },
        "is_admin": true
    }
}
```

- 2. Get Login Statistics
Retrieves login statistics for a specific application.

#### Endpoints :
```
GET /?action=get_login_stats&app_id={app_id}
```

#### Parameters :
- `app_id` (required): The application ID

#### Reponse :
```
{
    "status": "success",
    "message": "",
    "data": [
        {
            "login_date": "2023-01-01",
            "login_count": 10
        },
        {
            "login_date": "2023-01-02",
            "login_count": 15
        }
    ]
}
```
