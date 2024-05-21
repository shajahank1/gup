## API Specification: Get Access Token
> Description: This API provides an access token required to authenticate and authorize subsequent API requests.

### HTTP Method
- POST

### Endpoint
``` http://10.99.2.26/nehrapi/login/getToken ```

### Request Body
```
{
  "username": "MOH-90008",
  "password": "Moh@-90008"
}
```
### Parameters:

- username (string): The username of the user.
- password (string): The password associated with the username.
#### Successful Response
- HTTP Status Code: 200 (OK)

#### Content-Type: application/json

### Body:

```
{
    "version": "v2",
    "code": 0,
    "message": "1 Records found",
    "result": {
        "access_token": "d0816a77-af67-43fc-bad1-2edb2aae3dc5",
        "token_type": "bearer",
        "refresh_token": "542f00d0-4be3-4b47-940a-62e354b9c3e7",
        "expires_in": 86399,
        "scope": ["", "read", "write"],
        "firstLogin": null,
        "loggedInUser": null,
        "userDetails": null,
        "persCode": "-90008",
        "userIntitutes": [],
        "civilId": null,
        "userMobile": null
    }
}
```
### Fields:

- version (string): API version.
- code (integer): Status code of the operation.
- message (string): Description regarding the result.
- result (object): Contains details about the authentication token and user information.
- access_token (string): The token used for making authenticated requests.
- token_type (string): Type of token issued.
- refresh_token (string): Token used to renew access without re-entering credentials.
- expires_in (integer): Duration in seconds for which the token is valid.
- scope (array of strings): Permissions granted with this token.
- firstLogin (object): Information on whether this is the user's first login.
- loggedInUser (object): Information about the logged-in user.
- userDetails (object): Additional details of the user.
- persCode (string): Personnel code of the user.
- userIntitutes (array): Institutes associated with the user.
- civilId (object): Civil ID of the user, if applicable.
- userMobile (object): Mobile number of the user, if applicable.
#### Error Responses
- HTTP Status Code: 401 (Unauthorized)

### Content-Type: application/json
#### Body:
```
{
  "code": 401,
  "message": "Unauthorized: Access is denied due to invalid credentials."
}
```
HTTP Status Code: 500 (Internal Server Error)

Content-Type: application/json
Body:
```
{
  "code": 500,
  "message": "Internal Server Error: Unable to process the request due to server error."
}
```
> This document enables developers to understand and integrate the API endpoint for obtaining an access token necessary for authenticating further API interactions.
