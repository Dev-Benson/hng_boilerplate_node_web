---
title: HNG boilerplate node_web v1.0.0
language_tabs:
  - javascript: javascript
language_clients:
  - javascript: ""
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="hng-boilerplate-node_web">HNG boilerplate node_web v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Boilerplate api

Base URLs:

* <a href="{baseUrl}/api/v1">{baseUrl}/api/v1</a>

    * **baseUrl** -  Default: ${API_URL}

# Authentication

- HTTP Authentication, scheme: bearer 

<h1 id="hng-boilerplate-node_web-default">Default</h1>

## get__organizations

> Code samples

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/organizations',
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

`GET /organizations`

*List organizations*

<h3 id="get__organizations-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|none|
|limit|query|integer|false|none|
|search|query|string|false|none|

> Example responses

> 200 Response

```json
{
  "organizations": [
    {
      "id": "string",
      "name": "string"
    }
  ],
  "totalCount": 0,
  "currentPage": 0,
  "totalPages": 0
}
```

<h3 id="get__organizations-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|List of organizations|Inline|

<h3 id="get__organizations-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» organizations|[[Organization](#schemaorganization)]|false|none|none|
|»» id|string|false|none|none|
|»» name|string|true|none|none|
|» totalCount|integer|false|none|none|
|» currentPage|integer|false|none|none|
|» totalPages|integer|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## put__organizations_{orgId}

> Code samples

```javascript
const inputBody = '{
  "id": "string",
  "name": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/organizations/{orgId}',
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

`PUT /organizations/{orgId}`

*Update an organization*

> Body parameter

```json
{
  "id": "string",
  "name": "string"
}
```

<h3 id="put__organizations_{orgid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orgId|path|string|true|none|
|body|body|[Organization](#schemaorganization)|true|none|

<h3 id="put__organizations_{orgid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Organization updated successfully|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## delete__organizations_{orgId}

> Code samples

```javascript

const headers = {
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/organizations/{orgId}',
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

`DELETE /organizations/{orgId}`

*Delete an organization*

<h3 id="delete__organizations_{orgid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orgId|path|string|true|none|

<h3 id="delete__organizations_{orgid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Organization deleted successfully|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## put__users_{userId}

> Code samples

```javascript
const inputBody = '{
  "user_id": "string",
  "name": "string",
  "email": "user@example.com"
}';
const headers = {
  'Content-Type':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/users/{userId}',
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

`PUT /users/{userId}`

*Update user details*

> Body parameter

```json
{
  "user_id": "string",
  "name": "string",
  "email": "user@example.com"
}
```

<h3 id="put__users_{userid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string|true|none|
|body|body|[UserResponse](#schemauserresponse)|true|none|

<h3 id="put__users_{userid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|User updated successfully|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## delete__users_{userId}

> Code samples

```javascript

const headers = {
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/users/{userId}',
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

`DELETE /users/{userId}`

*Delete an User*

<h3 id="delete__users_{userid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string|true|none|

<h3 id="delete__users_{userid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|User deleted successfully|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## put__settings

> Code samples

```javascript
const inputBody = '{
  "userId": 0,
  "emailNotifications": true,
  "theme": "light",
  "language": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/settings',
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

`PUT /settings`

*Update user settings*

> Body parameter

```json
{
  "userId": 0,
  "emailNotifications": true,
  "theme": "light",
  "language": "string"
}
```

<h3 id="put__settings-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserSettings](#schemausersettings)|true|none|

<h3 id="put__settings-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|User settings updated successfully|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## get__notifications

> Code samples

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/notifications',
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

`GET /notifications`

*Get notifications*

<h3 id="get__notifications-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|none|
|limit|query|integer|false|none|

> Example responses

> 200 Response

```json
{
  "notifications": [
    {
      "id": "string",
      "userId": "string",
      "message": "string",
      "timestamp": "2019-08-24T14:15:22Z"
    }
  ],
  "totalCount": 0,
  "currentPage": 0,
  "totalPages": 0
}
```

<h3 id="get__notifications-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|List of notifications|Inline|

<h3 id="get__notifications-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» notifications|[[Notification](#schemanotification)]|false|none|none|
|»» id|string|false|none|none|
|»» userId|string|false|none|none|
|»» message|string|false|none|none|
|»» timestamp|string(date-time)|false|none|none|
|» totalCount|integer|false|none|none|
|» currentPage|integer|false|none|none|
|» totalPages|integer|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

<h1 id="hng-boilerplate-node_web-authentication">Authentication</h1>

User authentication endpoints

## post__auth_signup

> Code samples

```javascript
const inputBody = '{
  "name": "string",
  "email": "user@example.com",
  "password": "pa$$word"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('{baseUrl}/api/v1/auth/signup',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /auth/signup`

*Create a new User*

Register a new User

> Body parameter

```json
{
  "name": "string",
  "email": "user@example.com",
  "password": "pa$$word"
}
```

<h3 id="post__auth_signup-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[NewUser](#schemanewuser)|true|none|

> Example responses

> 201 Response

```json
{
  "user": {
    "user_id": "string",
    "name": "string",
    "email": "user@example.com"
  },
  "token": {
    "auth_token": "string",
    "auth_type": "Bearer",
    "expires_in": 3600
  }
}
```

<h3 id="post__auth_signup-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|User created successfully|[LoginResponse](#schemaloginresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid input|None|

<aside class="success">
This operation does not require authentication
</aside>

## post__auth_login

> Code samples

```javascript
const inputBody = '{
  "email": "user@example.com",
  "password": "pa$$word"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('{baseUrl}/api/v1/auth/login',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /auth/login`

*User Login*

Authenticates a user and initiates a new session.

Requires:
- User email
- Password

Returns:
- Authentication token
- User information

Notes:
- Passwords are case-sensitive
- Failed attempts may result in temporary account lockout

> Body parameter

```json
{
  "email": "user@example.com",
  "password": "pa$$word"
}
```

<h3 id="post__auth_login-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[LoginCredentials](#schemalogincredentials)|true|none|

> Example responses

> 200 Response

```json
{
  "user": {
    "user_id": "string",
    "name": "string",
    "email": "user@example.com"
  },
  "token": {
    "auth_token": "string",
    "auth_type": "Bearer",
    "expires_in": 3600
  }
}
```

<h3 id="post__auth_login-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Login successful|[LoginResponse](#schemaloginresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid credentials|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|User not found|None|

<aside class="success">
This operation does not require authentication
</aside>

## post__auth_forgot-password

> Code samples

```javascript
const inputBody = '{
  "email": "user@example.com"
}';
const headers = {
  'Content-Type':'application/json'
};

fetch('{baseUrl}/api/v1/auth/forgot-password',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /auth/forgot-password`

*Request password reset*

> Body parameter

```json
{
  "email": "user@example.com"
}
```

<h3 id="post__auth_forgot-password-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» email|body|string(email)|true|none|

<h3 id="post__auth_forgot-password-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Password reset email sent|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request - invalid email format|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|User not found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<aside class="success">
This operation does not require authentication
</aside>

## post__auth_reset-password

> Code samples

```javascript
const inputBody = '{
  "token": "string",
  "newPassword": "pa$$word"
}';
const headers = {
  'Content-Type':'application/json'
};

fetch('{baseUrl}/api/v1/auth/reset-password',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /auth/reset-password`

*Reset password*

> Body parameter

```json
{
  "token": "string",
  "newPassword": "pa$$word"
}
```

<h3 id="post__auth_reset-password-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» token|body|string|true|none|
|» newPassword|body|string(password)|true|none|

<h3 id="post__auth_reset-password-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Password reset successful|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request - Invalid credentials|None|

<aside class="success">
This operation does not require authentication
</aside>

## post__auth_change-password

> Code samples

```javascript
const inputBody = '{
  "currentPassword": "pa$$word",
  "newPassword": "pa$$word"
}';
const headers = {
  'Content-Type':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/auth/change-password',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /auth/change-password`

*Change password*

> Body parameter

```json
{
  "currentPassword": "pa$$word",
  "newPassword": "pa$$word"
}
```

<h3 id="post__auth_change-password-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» currentPassword|body|string(password)|true|none|
|» newPassword|body|string(password)|true|none|

<h3 id="post__auth_change-password-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Password changed successfully|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## post__email_send

> Code samples

```javascript
const inputBody = '{
  "to": "user@example.com",
  "subject": "string",
  "body": "string",
  "template": "string",
  "templateData": {}
}';
const headers = {
  'Content-Type':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/email/send',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /email/send`

*Send an email*

> Body parameter

```json
{
  "to": "user@example.com",
  "subject": "string",
  "body": "string",
  "template": "string",
  "templateData": {}
}
```

<h3 id="post__email_send-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» to|body|string(email)|true|none|
|» subject|body|string|true|none|
|» body|body|string|true|none|
|» template|body|string|false|none|
|» templateData|body|object|false|none|

<h3 id="post__email_send-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Email sent successfully|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid Email|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Error|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

<h1 id="hng-boilerplate-node_web-organisations">Organisations</h1>

Organisations endpoints

## post__organizations

> Code samples

```javascript
const inputBody = '{
  "id": "string",
  "name": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/organizations',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /organizations`

*Create an organization*

> Body parameter

```json
{
  "id": "string",
  "name": "string"
}
```

<h3 id="post__organizations-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Organization](#schemaorganization)|true|none|

<h3 id="post__organizations-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Organization created successfully|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## get__organizations_{orgId}

> Code samples

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/organizations/{orgId}',
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

`GET /organizations/{orgId}`

*Get an organization*

<h3 id="get__organizations_{orgid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orgId|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "name": "string"
}
```

<h3 id="get__organizations_{orgid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Organization details|[Organization](#schemaorganization)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

<h1 id="hng-boilerplate-node_web-users">Users</h1>

User management endpoints

## get__users_{userId}

> Code samples

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/users/{userId}',
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

`GET /users/{userId}`

*Get single User*

<h3 id="get__users_{userid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "user_id": "string",
  "name": "string",
  "email": "user@example.com"
}
```

<h3 id="get__users_{userid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|user details|[UserResponse](#schemauserresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## get__users_{userId}_dashboard

> Code samples

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/users/{userId}/dashboard',
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

`GET /users/{userId}/dashboard`

*Get User Dashboard*

Retrieves the dashboard data for a specific user. This endpoint requires authentication,
and users can only access their own dashboard data. The user ID in the path must match
the ID of the authenticated user.

<h3 id="get__users_{userid}_dashboard-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|integer|true|The ID of the user whose dashboard is being requested|

> Example responses

> 200 Response

```json
{
  "user": {
    "user_id": 0,
    "name": "string",
    "email": "string",
    "role": "string",
    "profile_picture": "string",
    "auth_type": "string",
    "auth_provider": "string",
    "gdpr_consent": true,
    "status": "string",
    "last_login": "2019-08-24T14:15:22Z",
    "created_at": "2019-08-24T14:15:22Z",
    "updated_at": "2019-08-24T14:15:22Z"
  },
  "random_data": [
    {
      "id": 0,
      "user_id": 0,
      "data": {},
      "created_at": "2019-08-24T14:15:22Z"
    }
  ]
}
```

<h3 id="get__users_{userid}_dashboard-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized - Invalid or missing token|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden - Token does not match the requested user ID|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found - User not found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<h3 id="get__users_{userid}_dashboard-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» user|[UserDetails](#schemauserdetails)|false|none|none|
|»» user_id|integer|false|none|none|
|»» name|string|false|none|none|
|»» email|string|false|none|none|
|»» role|string|false|none|none|
|»» profile_picture|string|false|none|none|
|»» auth_type|string|false|none|none|
|»» auth_provider|string|false|none|none|
|»» gdpr_consent|boolean|false|none|none|
|»» status|string|false|none|none|
|»» last_login|string(date-time)|false|none|none|
|»» created_at|string(date-time)|false|none|none|
|»» updated_at|string(date-time)|false|none|none|
|» random_data|[[RandomData](#schemarandomdata)]|false|none|none|
|»» id|integer|false|none|none|
|»» user_id|integer|false|none|none|
|»» data|object|false|none|none|
|»» created_at|string(date-time)|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## post__users_{userId}_data-export

> Code samples

```javascript
const inputBody = '{
  "data_types": [
    "user_details"
  ],
  "date_range": {
    "start_date": "2019-08-24",
    "end_date": "2019-08-24"
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/users/{userId}/data-export',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /users/{userId}/data-export`

*Request User Data Export*

Initiates a data export process for the authenticated user.
This endpoint allows users to request an export of their personal data,
including user details, settings, associated organizations, payment history,
and activity logs. The export is processed asynchronously, and the response
includes a job ID that can be used to check the export status later.

> Body parameter

```json
{
  "data_types": [
    "user_details"
  ],
  "date_range": {
    "start_date": "2019-08-24",
    "end_date": "2019-08-24"
  }
}
```

<h3 id="post__users_{userid}_data-export-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|integer|true|The ID of the user whose data is to be exported|
|body|body|object|true|none|
|» data_types|body|[string]|false|Types of data to include in the export. If empty, all types will be included.|
|» date_range|body|object|false|none|
|»» start_date|body|string(date)|false|none|
|»» end_date|body|string(date)|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|» data_types|user_details|
|» data_types|user_settings|
|» data_types|organisations|
|» data_types|payments|
|» data_types|activity_logs|

> Example responses

> 202 Response

```json
{
  "job_id": 0,
  "status": "pending",
  "estimated_completion_time": "2019-08-24T14:15:22Z"
}
```

<h3 id="post__users_{userid}_data-export-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|Export job created successfully|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request (e.g., invalid date range)|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<h3 id="post__users_{userid}_data-export-responseschema">Response Schema</h3>

Status Code **202**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» job_id|integer|false|none|Unique identifier for the export job|
|» status|string|false|none|Current status of the export job|
|» estimated_completion_time|string(date-time)|false|none|Estimated time when the export job will be completed|

#### Enumerated Values

|Property|Value|
|---|---|
|status|pending|
|status|processing|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## get__users_{userId}_data-export_{job_id}

> Code samples

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/users/{userId}/data-export/{job_id}',
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

`GET /users/{userId}/data-export/{job_id}`

*Get User Data Export Status and Data*

<h3 id="get__users_{userid}_data-export_{job_id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string|true|The ID of the user whose data is requested|
|job_id|path|string|true|The ID of the requested job export|

> Example responses

> 200 Response

```json
{
  "job_id": 0,
  "status": "pending",
  "export_data": {
    "user_data": {
      "user_id": 0,
      "name": "string",
      "email": "string",
      "role": "string",
      "profile_picture": "string",
      "auth_type": "string",
      "auth_provider": "string",
      "gdpr_consent": true,
      "status": "string",
      "last_login": "2019-08-24T14:15:22Z",
      "created_at": "2019-08-24T14:15:22Z",
      "updated_at": "2019-08-24T14:15:22Z"
    },
    "user_settings": [
      {
        "userId": 0,
        "emailNotifications": true,
        "theme": "light",
        "language": "string"
      }
    ],
    "organisations": [
      {
        "org_id": 0,
        "name": "string",
        "description": "string",
        "created_by": 0,
        "status": "string",
        "created_at": "2019-08-24T14:15:22Z",
        "updated_at": "2019-08-24T14:15:22Z"
      }
    ],
    "payments": [
      {
        "id": "string",
        "amount": 0,
        "currency": "string",
        "method": "string",
        "status": "pending",
        "createdAt": "2019-08-24T14:15:22Z"
      }
    ],
    "activity_logs": [
      {
        "log_id": 0,
        "user_id": 0,
        "org_id": 0,
        "activity_type": "string",
        "description": "string",
        "ip_address": "string",
        "user_agent": "string",
        "created_at": "2019-08-24T14:15:22Z"
      }
    ]
  }
}
```

<h3 id="get__users_{userid}_data-export_{job_id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Export job status and data|Inline|

<h3 id="get__users_{userid}_data-export_{job_id}-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» job_id|integer|false|none|none|
|» status|string|false|none|none|
|» export_data|[UserDataExport](#schemauserdataexport)|false|none|none|
|»» user_data|[UserDetails](#schemauserdetails)|false|none|none|
|»»» user_id|integer|false|none|none|
|»»» name|string|false|none|none|
|»»» email|string|false|none|none|
|»»» role|string|false|none|none|
|»»» profile_picture|string|false|none|none|
|»»» auth_type|string|false|none|none|
|»»» auth_provider|string|false|none|none|
|»»» gdpr_consent|boolean|false|none|none|
|»»» status|string|false|none|none|
|»»» last_login|string(date-time)|false|none|none|
|»»» created_at|string(date-time)|false|none|none|
|»»» updated_at|string(date-time)|false|none|none|
|»» user_settings|[[UserSettings](#schemausersettings)]|false|none|none|
|»»» userId|integer|false|none|none|
|»»» emailNotifications|boolean|false|none|none|
|»»» theme|string|false|none|none|
|»»» language|string|false|none|none|
|»» organisations|[[OrganisationDetails](#schemaorganisationdetails)]|false|none|none|
|»»» org_id|integer|false|none|none|
|»»» name|string|false|none|none|
|»»» description|string|false|none|none|
|»»» created_by|integer|false|none|none|
|»»» status|string|false|none|none|
|»»» created_at|string(date-time)|false|none|none|
|»»» updated_at|string(date-time)|false|none|none|
|»» payments|[[Payment](#schemapayment)]|false|none|none|
|»»» id|string|false|none|none|
|»»» amount|number|false|none|none|
|»»» currency|string|false|none|none|
|»»» method|string|false|none|none|
|»»» status|string|false|none|none|
|»»» createdAt|string(date-time)|false|none|none|
|»» activity_logs|[[ActivityLog](#schemaactivitylog)]|false|none|none|
|»»» log_id|integer|false|none|none|
|»»» user_id|integer|false|none|none|
|»»» org_id|integer|false|none|none|
|»»» activity_type|string|false|none|none|
|»»» description|string|false|none|none|
|»»» ip_address|string|false|none|none|
|»»» user_agent|string|false|none|none|
|»»» created_at|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|pending|
|status|processing|
|status|completed|
|status|failed|
|theme|light|
|theme|dark|
|status|pending|
|status|completed|
|status|failed|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## get__users_{userId}_chart-data

> Code samples

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/users/{userId}/chart-data',
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

`GET /users/{userId}/chart-data`

*Get Chart Data*

<h3 id="get__users_{userid}_chart-data-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|integer|true|The ID of the user whose data-chart is requested|

> Example responses

> 200 Response

```json
{
  "labels": [
    "string"
  ],
  "datasets": [
    {
      "label": "string",
      "data": [
        0
      ]
    }
  ]
}
```

<h3 id="get__users_{userid}_chart-data-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|[ChartData](#schemachartdata)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## get__users_{userId}_settings

> Code samples

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/users/{userId}/settings',
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

`GET /users/{userId}/settings`

*Get user settings*

<h3 id="get__users_{userid}_settings-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "userId": 0,
  "emailNotifications": true,
  "theme": "light",
  "language": "string"
}
```

<h3 id="get__users_{userid}_settings-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|[UserSettings](#schemausersettings)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden - User doesn't have permission to access these settings|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|User not found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## put__users_{userId}_settings

> Code samples

```javascript
const inputBody = '{
  "userId": 0,
  "emailNotifications": true,
  "theme": "light",
  "language": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/users/{userId}/settings',
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

`PUT /users/{userId}/settings`

*Update user settings*

> Body parameter

```json
{
  "userId": 0,
  "emailNotifications": true,
  "theme": "light",
  "language": "string"
}
```

<h3 id="put__users_{userid}_settings-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|integer|true|none|
|body|body|[UserSettings](#schemausersettings)|true|none|

<h3 id="put__users_{userid}_settings-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Settings updated successfully|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid input|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden - User doesn't have permission to update these settings|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|User not found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

<h1 id="hng-boilerplate-node_web-invites">Invites</h1>

User Invitation endpoints

## post__invites

> Code samples

```javascript
const inputBody = '{
  "email": "user@example.com",
  "role": "user"
}';
const headers = {
  'Content-Type':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/invites',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /invites`

*Create an invite*

> Body parameter

```json
{
  "email": "user@example.com",
  "role": "user"
}
```

<h3 id="post__invites-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» email|body|string(email)|true|none|
|» role|body|string|true|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|» role|user|
|» role|admin|

<h3 id="post__invites-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Invite created successfully|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server error|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## post__invites_{inviteId}_accept

> Code samples

```javascript
const inputBody = '{
  "password": "pa$$word"
}';
const headers = {
  'Content-Type':'application/json'
};

fetch('{baseUrl}/api/v1/invites/{inviteId}/accept',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /invites/{inviteId}/accept`

*Accept an invite*

> Body parameter

```json
{
  "password": "pa$$word"
}
```

<h3 id="post__invites_{inviteid}_accept-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|inviteId|path|string|true|none|
|body|body|object|true|none|
|» password|body|string(password)|true|none|

<h3 id="post__invites_{inviteid}_accept-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Invite accepted successfully|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="hng-boilerplate-node_web-payment">Payment</h1>

Payment endpoints

## post__payments

> Code samples

```javascript
const inputBody = '{
  "amount": 0,
  "currency": "string",
  "method": "credit_card",
  "description": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('{baseUrl}/api/v1/payments',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /payments`

*Create a new payment*

> Body parameter

```json
{
  "amount": 0,
  "currency": "string",
  "method": "credit_card",
  "description": "string"
}
```

<h3 id="post__payments-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PaymentRequest](#schemapaymentrequest)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "string",
  "amount": 0,
  "currency": "string",
  "method": "string",
  "status": "pending",
  "createdAt": "2019-08-24T14:15:22Z"
}
```

<h3 id="post__payments-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Payment created successfully|[Payment](#schemapayment)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid input|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<aside class="success">
This operation does not require authentication
</aside>

## get__payments

> Code samples

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('{baseUrl}/api/v1/payments',
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

`GET /payments`

*List all payments*

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "amount": 0,
    "currency": "string",
    "method": "string",
    "status": "pending",
    "createdAt": "2019-08-24T14:15:22Z"
  }
]
```

<h3 id="get__payments-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<h3 id="get__payments-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Payment](#schemapayment)]|false|none|none|
|» id|string|false|none|none|
|» amount|number|false|none|none|
|» currency|string|false|none|none|
|» method|string|false|none|none|
|» status|string|false|none|none|
|» createdAt|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|pending|
|status|completed|
|status|failed|

<aside class="success">
This operation does not require authentication
</aside>

## get__payments_{paymentId}

> Code samples

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('{baseUrl}/api/v1/payments/{paymentId}',
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

`GET /payments/{paymentId}`

*Get a payment by ID*

<h3 id="get__payments_{paymentid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|paymentId|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "amount": 0,
  "currency": "string",
  "method": "string",
  "status": "pending",
  "createdAt": "2019-08-24T14:15:22Z"
}
```

<h3 id="get__payments_{paymentid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|[Payment](#schemapayment)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Payment not found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<aside class="success">
This operation does not require authentication
</aside>

## put__payments_{paymentId}

> Code samples

```javascript
const inputBody = '{
  "amount": 0,
  "currency": "string",
  "method": "credit_card",
  "description": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('{baseUrl}/api/v1/payments/{paymentId}',
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

`PUT /payments/{paymentId}`

*Update a payment*

> Body parameter

```json
{
  "amount": 0,
  "currency": "string",
  "method": "credit_card",
  "description": "string"
}
```

<h3 id="put__payments_{paymentid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|paymentId|path|string|true|none|
|body|body|[PaymentRequest](#schemapaymentrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "amount": 0,
  "currency": "string",
  "method": "string",
  "status": "pending",
  "createdAt": "2019-08-24T14:15:22Z"
}
```

<h3 id="put__payments_{paymentid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Payment updated successfully|[Payment](#schemapayment)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid input|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Payment not found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<aside class="success">
This operation does not require authentication
</aside>

## put__payments_{paymentId}_status

> Code samples

```javascript
const inputBody = '{
  "status": "pending"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('{baseUrl}/api/v1/payments/{paymentId}/status',
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

`PUT /payments/{paymentId}/status`

*Update payment status*

> Body parameter

```json
{
  "status": "pending"
}
```

<h3 id="put__payments_{paymentid}_status-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|paymentId|path|string|true|none|
|body|body|object|true|none|
|» status|body|string|true|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|» status|pending|
|» status|completed|
|» status|failed|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "amount": 0,
  "currency": "string",
  "method": "string",
  "status": "pending",
  "createdAt": "2019-08-24T14:15:22Z"
}
```

<h3 id="put__payments_{paymentid}_status-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Payment status updated successfully|[Payment](#schemapayment)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid input|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Payment not found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="hng-boilerplate-node_web-settings">Settings</h1>

User Settings endpoints

## put__settings_language

> Code samples

```javascript
const inputBody = '{
  "languageCode": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/settings/language',
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

`PUT /settings/language`

*Update language preference*

> Body parameter

```json
{
  "languageCode": "string"
}
```

<h3 id="put__settings_language-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» languageCode|body|string|true|none|

<h3 id="put__settings_language-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Language preference updated successfully|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## put__settings_region

> Code samples

```javascript
const inputBody = '{
  "regionCode": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/settings/region',
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

`PUT /settings/region`

*Update region preference*

> Body parameter

```json
{
  "regionCode": "string"
}
```

<h3 id="put__settings_region-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» regionCode|body|string|true|none|

<h3 id="put__settings_region-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Region preference updated successfully|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## get__settings

> Code samples

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/settings',
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

`GET /settings`

*Get user settings*

> Example responses

> 200 Response

```json
{
  "userId": 0,
  "emailNotifications": true,
  "theme": "light",
  "language": "string"
}
```

<h3 id="get__settings-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|User settings|[UserSettings](#schemausersettings)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

<h1 id="hng-boilerplate-node_web-notifications">Notifications</h1>

Activity-logs endpoints

## post__notifications

> Code samples

```javascript
const inputBody = '{
  "userId": "string",
  "message": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/notifications',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /notifications`

*Send a notification*

> Body parameter

```json
{
  "userId": "string",
  "message": "string"
}
```

<h3 id="post__notifications-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» userId|body|string|true|none|
|» message|body|string|true|none|

<h3 id="post__notifications-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Notification sent successfully|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

<h1 id="hng-boilerplate-node_web-ai-text-analysis">AI Text Analysis</h1>

AI Text Analysis endpoints

## post__ai_analyze-text

> Code samples

```javascript
const inputBody = '{
  "text": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('{baseUrl}/api/v1/ai/analyze-text',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /ai/analyze-text`

*Analyze text and return sentiment, entities, and keywords*

> Body parameter

```json
{
  "text": "string"
}
```

<h3 id="post__ai_analyze-text-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» text|body|string|true|The text to be analyzed|

> Example responses

> 200 Response

```json
{
  "sentiment": "positive",
  "entities": [
    {
      "text": "string",
      "type": "string"
    }
  ],
  "keywords": [
    "string"
  ]
}
```

<h3 id="post__ai_analyze-text-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful analysis|[TextAnalysisResult](#schematextanalysisresult)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid input|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<aside class="success">
This operation does not require authentication
</aside>

## post__ai_analyze-sentiment

> Code samples

```javascript
const inputBody = '{
  "text": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('{baseUrl}/api/v1/ai/analyze-sentiment',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /ai/analyze-sentiment`

*Analyze sentiment of the given text*

> Body parameter

```json
{
  "text": "string"
}
```

<h3 id="post__ai_analyze-sentiment-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» text|body|string|true|The text to analyze for sentiment|

> Example responses

> 200 Response

```json
{
  "sentiment": "positive"
}
```

<h3 id="post__ai_analyze-sentiment-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful sentiment analysis|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid input|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<h3 id="post__ai_analyze-sentiment-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» sentiment|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|sentiment|positive|
|sentiment|neutral|
|sentiment|negative|

<aside class="success">
This operation does not require authentication
</aside>

## post__ai_extract-entities

> Code samples

```javascript
const inputBody = '{
  "text": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('{baseUrl}/api/v1/ai/extract-entities',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /ai/extract-entities`

*Extract entities from the given text*

> Body parameter

```json
{
  "text": "string"
}
```

<h3 id="post__ai_extract-entities-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» text|body|string|true|The text to extract entities from|

> Example responses

> 200 Response

```json
{
  "entities": [
    {
      "text": "string",
      "type": "string"
    }
  ]
}
```

<h3 id="post__ai_extract-entities-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful entity extraction|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid input|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<h3 id="post__ai_extract-entities-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» entities|[object]|false|none|none|
|»» text|string|false|none|none|
|»» type|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## post__ai_extract-keywords

> Code samples

```javascript
const inputBody = '{
  "text": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('{baseUrl}/api/v1/ai/extract-keywords',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /ai/extract-keywords`

*Extract keywords from the given text*

> Body parameter

```json
{
  "text": "string"
}
```

<h3 id="post__ai_extract-keywords-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» text|body|string|true|The text to extract keywords from|

> Example responses

> 200 Response

```json
{
  "keywords": [
    "string"
  ]
}
```

<h3 id="post__ai_extract-keywords-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful keyword extraction|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid input|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<h3 id="post__ai_extract-keywords-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» keywords|[string]|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="hng-boilerplate-node_web-activity-logs">Activity-logs</h1>

Activity-logs endpoints

## get__activity-logs

> Code samples

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/activity-logs',
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

`GET /activity-logs`

*Get activity logs*

<h3 id="get__activity-logs-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|none|
|limit|query|integer|false|none|
|userId|query|string|false|none|
|action|query|string|false|none|
|startDate|query|string(date)|false|none|
|endDate|query|string(date)|false|none|

> Example responses

> 200 Response

```json
{
  "logs": [
    {
      "log_id": 0,
      "user_id": 0,
      "org_id": 0,
      "activity_type": "string",
      "description": "string",
      "ip_address": "string",
      "user_agent": "string",
      "created_at": "2019-08-24T14:15:22Z"
    }
  ],
  "totalCount": 0,
  "currentPage": 0,
  "totalPages": 0
}
```

<h3 id="get__activity-logs-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|List of activity logs|Inline|

<h3 id="get__activity-logs-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» logs|[[ActivityLog](#schemaactivitylog)]|false|none|none|
|»» log_id|integer|false|none|none|
|»» user_id|integer|false|none|none|
|»» org_id|integer|false|none|none|
|»» activity_type|string|false|none|none|
|»» description|string|false|none|none|
|»» ip_address|string|false|none|none|
|»» user_agent|string|false|none|none|
|»» created_at|string(date-time)|false|none|none|
|» totalCount|integer|false|none|none|
|» currentPage|integer|false|none|none|
|» totalPages|integer|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

<h1 id="hng-boilerplate-node_web-admin">Admin</h1>

Admin endpoints

## get__admin_dashboard

> Code samples

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('{baseUrl}/api/v1/admin/dashboard',
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

`GET /admin/dashboard`

*Get Superadmin Dashboard*

> Example responses

> 200 Response

```json
{
  "users": {
    "user_id": 0,
    "name": "string",
    "email": "string",
    "role": "string",
    "profile_picture": "string",
    "auth_type": "string",
    "auth_provider": "string",
    "gdpr_consent": true,
    "status": "string",
    "last_login": "2019-08-24T14:15:22Z",
    "created_at": "2019-08-24T14:15:22Z",
    "updated_at": "2019-08-24T14:15:22Z"
  },
  "organisations": {
    "org_id": 0,
    "name": "string",
    "description": "string",
    "created_by": 0,
    "status": "string",
    "created_at": "2019-08-24T14:15:22Z",
    "updated_at": "2019-08-24T14:15:22Z"
  },
  "payments": {
    "id": "string",
    "amount": 0,
    "currency": "string",
    "method": "string",
    "status": "pending",
    "createdAt": "2019-08-24T14:15:22Z"
  },
  "activity_logs": {
    "log_id": 0,
    "user_id": 0,
    "org_id": 0,
    "activity_type": "string",
    "description": "string",
    "ip_address": "string",
    "user_agent": "string",
    "created_at": "2019-08-24T14:15:22Z"
  }
}
```

<h3 id="get__admin_dashboard-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|[SuperadminDashboard](#schemasuperadmindashboard)|

<aside class="success">
This operation does not require authentication
</aside>

## get__admin_users

> Code samples

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('{baseUrl}/api/v1/admin/users',
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

`GET /admin/users`

*List all users*

<h3 id="get__admin_users-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|none|
|limit|query|integer|false|none|
|sort|query|string|false|none|
|search|query|string|false|none|

> Example responses

> 200 Response

```json
[
  {
    "user_id": 0,
    "name": "string",
    "email": "string",
    "role": "string",
    "profile_picture": "string",
    "auth_type": "string",
    "auth_provider": "string",
    "gdpr_consent": true,
    "status": "string",
    "last_login": "2019-08-24T14:15:22Z",
    "created_at": "2019-08-24T14:15:22Z",
    "updated_at": "2019-08-24T14:15:22Z"
  }
]
```

<h3 id="get__admin_users-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|Inline|

<h3 id="get__admin_users-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[UserDetails](#schemauserdetails)]|false|none|none|
|» user_id|integer|false|none|none|
|» name|string|false|none|none|
|» email|string|false|none|none|
|» role|string|false|none|none|
|» profile_picture|string|false|none|none|
|» auth_type|string|false|none|none|
|» auth_provider|string|false|none|none|
|» gdpr_consent|boolean|false|none|none|
|» status|string|false|none|none|
|» last_login|string(date-time)|false|none|none|
|» created_at|string(date-time)|false|none|none|
|» updated_at|string(date-time)|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## get__admin_organisations

> Code samples

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('{baseUrl}/api/v1/admin/organisations',
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

`GET /admin/organisations`

*List all organisations*

<h3 id="get__admin_organisations-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|none|
|limit|query|integer|false|none|
|sort|query|string|false|none|
|search|query|string|false|none|

> Example responses

> 200 Response

```json
[
  {
    "org_id": 0,
    "name": "string",
    "description": "string",
    "created_by": 0,
    "status": "string",
    "created_at": "2019-08-24T14:15:22Z",
    "updated_at": "2019-08-24T14:15:22Z"
  }
]
```

<h3 id="get__admin_organisations-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|Inline|

<h3 id="get__admin_organisations-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[OrganisationDetails](#schemaorganisationdetails)]|false|none|none|
|» org_id|integer|false|none|none|
|» name|string|false|none|none|
|» description|string|false|none|none|
|» created_by|integer|false|none|none|
|» status|string|false|none|none|
|» created_at|string(date-time)|false|none|none|
|» updated_at|string(date-time)|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## get__admin_payments

> Code samples

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('{baseUrl}/api/v1/admin/payments',
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

`GET /admin/payments`

*List all payments*

<h3 id="get__admin_payments-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|none|
|limit|query|integer|false|none|
|sort|query|string|false|none|
|search|query|string|false|none|

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "amount": 0,
    "currency": "string",
    "method": "string",
    "status": "pending",
    "createdAt": "2019-08-24T14:15:22Z"
  }
]
```

<h3 id="get__admin_payments-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|Inline|

<h3 id="get__admin_payments-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Payment](#schemapayment)]|false|none|none|
|» id|string|false|none|none|
|» amount|number|false|none|none|
|» currency|string|false|none|none|
|» method|string|false|none|none|
|» status|string|false|none|none|
|» createdAt|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|pending|
|status|completed|
|status|failed|

<aside class="success">
This operation does not require authentication
</aside>

## get__admin_activity-logs

> Code samples

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('{baseUrl}/api/v1/admin/activity-logs',
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

`GET /admin/activity-logs`

*List all activity logs*

<h3 id="get__admin_activity-logs-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|none|
|limit|query|integer|false|none|
|sort|query|string|false|none|
|search|query|string|false|none|

> Example responses

> 200 Response

```json
[
  {
    "log_id": 0,
    "user_id": 0,
    "org_id": 0,
    "activity_type": "string",
    "description": "string",
    "ip_address": "string",
    "user_agent": "string",
    "created_at": "2019-08-24T14:15:22Z"
  }
]
```

<h3 id="get__admin_activity-logs-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|Inline|

<h3 id="get__admin_activity-logs-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[ActivityLog](#schemaactivitylog)]|false|none|none|
|» log_id|integer|false|none|none|
|» user_id|integer|false|none|none|
|» org_id|integer|false|none|none|
|» activity_type|string|false|none|none|
|» description|string|false|none|none|
|» ip_address|string|false|none|none|
|» user_agent|string|false|none|none|
|» created_at|string(date-time)|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="hng-boilerplate-node_web-pages">Pages</h1>

page endpoints

## get__pages

> Code samples

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('{baseUrl}/api/v1/pages?pageName=privacy-policy',
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

`GET /pages`

*Get page content*

<h3 id="get__pages-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|pageName|query|string|true|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|pageName|privacy-policy|
|pageName|about-us|
|pageName|contact-us|

> Example responses

> 200 Response

```json
{
  "title": "string",
  "content": "string",
  "lastUpdated": "2019-08-24T14:15:22Z"
}
```

<h3 id="get__pages-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|[Page](#schemapage)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Page not found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="hng-boilerplate-node_web-blog">Blog</h1>

Blog endpoints

## get__blog

> Code samples

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('{baseUrl}/api/v1/blog',
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

`GET /blog`

*Get blog posts*

<h3 id="get__blog-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|none|
|limit|query|integer|false|none|

> Example responses

> 200 Response

```json
{
  "posts": [
    {
      "title": "string",
      "body": "string",
      "authorId": 0,
      "type": "article",
      "status": "draft",
      "id": 0,
      "createdAt": "2019-08-24T14:15:22Z",
      "updatedAt": "2019-08-24T14:15:22Z",
      "excerpt": "string",
      "tags": [
        "string"
      ]
    }
  ],
  "totalPages": 0,
  "currentPage": 0
}
```

<h3 id="get__blog-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<h3 id="get__blog-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» posts|[allOf]|false|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|any|false|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»» *anonymous*|[ContentInput](#schemacontentinput)|false|none|none|
|»»»» title|string|false|none|none|
|»»»» body|string|false|none|none|
|»»»» authorId|integer|false|none|none|
|»»»» type|string|false|none|none|
|»»»» status|string|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»» *anonymous*|object|false|none|none|
|»»»» id|integer|false|none|none|
|»»»» createdAt|string(date-time)|false|none|none|
|»»»» updatedAt|string(date-time)|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|object|false|none|none|
|»»» excerpt|string|false|none|none|
|»»» tags|[string]|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» totalPages|integer|false|none|none|
|» currentPage|integer|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|article|
|type|blog_post|
|type|page|
|status|draft|
|status|published|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="hng-boilerplate-node_web-content">Content</h1>

content endpoints

## post__content

> Code samples

```javascript
const inputBody = '{
  "title": "string",
  "body": "string",
  "authorId": 0,
  "type": "article",
  "status": "draft"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/content',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /content`

*Create new content*

> Body parameter

```json
{
  "title": "string",
  "body": "string",
  "authorId": 0,
  "type": "article",
  "status": "draft"
}
```

<h3 id="post__content-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ContentInput](#schemacontentinput)|true|none|

> Example responses

> 201 Response

```json
{
  "title": "string",
  "body": "string",
  "authorId": 0,
  "type": "article",
  "status": "draft",
  "id": 0,
  "createdAt": "2019-08-24T14:15:22Z",
  "updatedAt": "2019-08-24T14:15:22Z"
}
```

<h3 id="post__content-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Content created successfully|[Content](#schemacontent)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid input|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden - User doesn't have permission to create content|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## get__content_{contentId}

> Code samples

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('{baseUrl}/api/v1/content/{contentId}',
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

`GET /content/{contentId}`

*Get content by ID*

<h3 id="get__content_{contentid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|contentId|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "title": "string",
  "body": "string",
  "authorId": 0,
  "type": "article",
  "status": "draft",
  "id": 0,
  "createdAt": "2019-08-24T14:15:22Z",
  "updatedAt": "2019-08-24T14:15:22Z"
}
```

<h3 id="get__content_{contentid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|[Content](#schemacontent)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Content not found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<aside class="success">
This operation does not require authentication
</aside>

## put__content_{contentId}

> Code samples

```javascript
const inputBody = '{
  "title": "string",
  "body": "string",
  "authorId": 0,
  "type": "article",
  "status": "draft"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/content/{contentId}',
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

`PUT /content/{contentId}`

*Update content*

> Body parameter

```json
{
  "title": "string",
  "body": "string",
  "authorId": 0,
  "type": "article",
  "status": "draft"
}
```

<h3 id="put__content_{contentid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|contentId|path|integer|true|none|
|body|body|[ContentInput](#schemacontentinput)|true|none|

> Example responses

> 200 Response

```json
{
  "title": "string",
  "body": "string",
  "authorId": 0,
  "type": "article",
  "status": "draft",
  "id": 0,
  "createdAt": "2019-08-24T14:15:22Z",
  "updatedAt": "2019-08-24T14:15:22Z"
}
```

<h3 id="put__content_{contentid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Content updated successfully|[Content](#schemacontent)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid input|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden - User doesn't have permission to update this content|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Content not found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## delete__content_{contentId}

> Code samples

```javascript

const headers = {
  'Authorization':'Bearer {access-token}'
};

fetch('{baseUrl}/api/v1/content/{contentId}',
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

`DELETE /content/{contentId}`

*Delete content*

<h3 id="delete__content_{contentid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|contentId|path|integer|true|none|

<h3 id="delete__content_{contentid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Content deleted successfully|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden - User doesn't have permission to delete this content|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Content not found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

# Schemas

<h2 id="tocS_Token">Token</h2>
<!-- backwards compatibility -->
<a id="schematoken"></a>
<a id="schema_Token"></a>
<a id="tocStoken"></a>
<a id="tocstoken"></a>

```json
{
  "auth_token": "string",
  "auth_type": "Bearer",
  "expires_in": 3600
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|auth_token|string|false|none|none|
|auth_type|string|false|none|none|
|expires_in|integer|false|none|Expiration time in seconds|

<h2 id="tocS_NewUser">NewUser</h2>
<!-- backwards compatibility -->
<a id="schemanewuser"></a>
<a id="schema_NewUser"></a>
<a id="tocSnewuser"></a>
<a id="tocsnewuser"></a>

```json
{
  "name": "string",
  "email": "user@example.com",
  "password": "pa$$word"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|none|
|email|string(email)|true|none|none|
|password|string(password)|true|none|none|

<h2 id="tocS_UserResponse">UserResponse</h2>
<!-- backwards compatibility -->
<a id="schemauserresponse"></a>
<a id="schema_UserResponse"></a>
<a id="tocSuserresponse"></a>
<a id="tocsuserresponse"></a>

```json
{
  "user_id": "string",
  "name": "string",
  "email": "user@example.com"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|user_id|string|false|none|none|
|name|string|false|none|none|
|email|string(email)|false|none|none|

<h2 id="tocS_LoginCredentials">LoginCredentials</h2>
<!-- backwards compatibility -->
<a id="schemalogincredentials"></a>
<a id="schema_LoginCredentials"></a>
<a id="tocSlogincredentials"></a>
<a id="tocslogincredentials"></a>

```json
{
  "email": "user@example.com",
  "password": "pa$$word"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|email|string(email)|true|none|none|
|password|string(password)|true|none|none|

<h2 id="tocS_LoginResponse">LoginResponse</h2>
<!-- backwards compatibility -->
<a id="schemaloginresponse"></a>
<a id="schema_LoginResponse"></a>
<a id="tocSloginresponse"></a>
<a id="tocsloginresponse"></a>

```json
{
  "user": {
    "user_id": "string",
    "name": "string",
    "email": "user@example.com"
  },
  "token": {
    "auth_token": "string",
    "auth_type": "Bearer",
    "expires_in": 3600
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|user|[UserResponse](#schemauserresponse)|false|none|none|
|token|[Token](#schematoken)|false|none|none|

<h2 id="tocS_Organization">Organization</h2>
<!-- backwards compatibility -->
<a id="schemaorganization"></a>
<a id="schema_Organization"></a>
<a id="tocSorganization"></a>
<a id="tocsorganization"></a>

```json
{
  "id": "string",
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|name|string|true|none|none|

<h2 id="tocS_ActivityLog">ActivityLog</h2>
<!-- backwards compatibility -->
<a id="schemaactivitylog"></a>
<a id="schema_ActivityLog"></a>
<a id="tocSactivitylog"></a>
<a id="tocsactivitylog"></a>

```json
{
  "log_id": 0,
  "user_id": 0,
  "org_id": 0,
  "activity_type": "string",
  "description": "string",
  "ip_address": "string",
  "user_agent": "string",
  "created_at": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|log_id|integer|false|none|none|
|user_id|integer|false|none|none|
|org_id|integer|false|none|none|
|activity_type|string|false|none|none|
|description|string|false|none|none|
|ip_address|string|false|none|none|
|user_agent|string|false|none|none|
|created_at|string(date-time)|false|none|none|

<h2 id="tocS_UserSettings">UserSettings</h2>
<!-- backwards compatibility -->
<a id="schemausersettings"></a>
<a id="schema_UserSettings"></a>
<a id="tocSusersettings"></a>
<a id="tocsusersettings"></a>

```json
{
  "userId": 0,
  "emailNotifications": true,
  "theme": "light",
  "language": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userId|integer|false|none|none|
|emailNotifications|boolean|false|none|none|
|theme|string|false|none|none|
|language|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|theme|light|
|theme|dark|

<h2 id="tocS_Notification">Notification</h2>
<!-- backwards compatibility -->
<a id="schemanotification"></a>
<a id="schema_Notification"></a>
<a id="tocSnotification"></a>
<a id="tocsnotification"></a>

```json
{
  "id": "string",
  "userId": "string",
  "message": "string",
  "timestamp": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|userId|string|false|none|none|
|message|string|false|none|none|
|timestamp|string(date-time)|false|none|none|

<h2 id="tocS_PaymentRequest">PaymentRequest</h2>
<!-- backwards compatibility -->
<a id="schemapaymentrequest"></a>
<a id="schema_PaymentRequest"></a>
<a id="tocSpaymentrequest"></a>
<a id="tocspaymentrequest"></a>

```json
{
  "amount": 0,
  "currency": "string",
  "method": "credit_card",
  "description": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|amount|number|true|none|none|
|currency|string|true|none|none|
|method|string|true|none|none|
|description|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|method|credit_card|
|method|paypal|
|method|bank_transfer|

<h2 id="tocS_Payment">Payment</h2>
<!-- backwards compatibility -->
<a id="schemapayment"></a>
<a id="schema_Payment"></a>
<a id="tocSpayment"></a>
<a id="tocspayment"></a>

```json
{
  "id": "string",
  "amount": 0,
  "currency": "string",
  "method": "string",
  "status": "pending",
  "createdAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|amount|number|false|none|none|
|currency|string|false|none|none|
|method|string|false|none|none|
|status|string|false|none|none|
|createdAt|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|pending|
|status|completed|
|status|failed|

<h2 id="tocS_TextAnalysisResult">TextAnalysisResult</h2>
<!-- backwards compatibility -->
<a id="schematextanalysisresult"></a>
<a id="schema_TextAnalysisResult"></a>
<a id="tocStextanalysisresult"></a>
<a id="tocstextanalysisresult"></a>

```json
{
  "sentiment": "positive",
  "entities": [
    {
      "text": "string",
      "type": "string"
    }
  ],
  "keywords": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sentiment|string|false|none|none|
|entities|[object]|false|none|none|
|» text|string|false|none|none|
|» type|string|false|none|none|
|keywords|[string]|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|sentiment|positive|
|sentiment|neutral|
|sentiment|negative|

<h2 id="tocS_UserDetails">UserDetails</h2>
<!-- backwards compatibility -->
<a id="schemauserdetails"></a>
<a id="schema_UserDetails"></a>
<a id="tocSuserdetails"></a>
<a id="tocsuserdetails"></a>

```json
{
  "user_id": 0,
  "name": "string",
  "email": "string",
  "role": "string",
  "profile_picture": "string",
  "auth_type": "string",
  "auth_provider": "string",
  "gdpr_consent": true,
  "status": "string",
  "last_login": "2019-08-24T14:15:22Z",
  "created_at": "2019-08-24T14:15:22Z",
  "updated_at": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|user_id|integer|false|none|none|
|name|string|false|none|none|
|email|string|false|none|none|
|role|string|false|none|none|
|profile_picture|string|false|none|none|
|auth_type|string|false|none|none|
|auth_provider|string|false|none|none|
|gdpr_consent|boolean|false|none|none|
|status|string|false|none|none|
|last_login|string(date-time)|false|none|none|
|created_at|string(date-time)|false|none|none|
|updated_at|string(date-time)|false|none|none|

<h2 id="tocS_OrganisationDetails">OrganisationDetails</h2>
<!-- backwards compatibility -->
<a id="schemaorganisationdetails"></a>
<a id="schema_OrganisationDetails"></a>
<a id="tocSorganisationdetails"></a>
<a id="tocsorganisationdetails"></a>

```json
{
  "org_id": 0,
  "name": "string",
  "description": "string",
  "created_by": 0,
  "status": "string",
  "created_at": "2019-08-24T14:15:22Z",
  "updated_at": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|org_id|integer|false|none|none|
|name|string|false|none|none|
|description|string|false|none|none|
|created_by|integer|false|none|none|
|status|string|false|none|none|
|created_at|string(date-time)|false|none|none|
|updated_at|string(date-time)|false|none|none|

<h2 id="tocS_SuperadminDashboard">SuperadminDashboard</h2>
<!-- backwards compatibility -->
<a id="schemasuperadmindashboard"></a>
<a id="schema_SuperadminDashboard"></a>
<a id="tocSsuperadmindashboard"></a>
<a id="tocssuperadmindashboard"></a>

```json
{
  "users": {
    "user_id": 0,
    "name": "string",
    "email": "string",
    "role": "string",
    "profile_picture": "string",
    "auth_type": "string",
    "auth_provider": "string",
    "gdpr_consent": true,
    "status": "string",
    "last_login": "2019-08-24T14:15:22Z",
    "created_at": "2019-08-24T14:15:22Z",
    "updated_at": "2019-08-24T14:15:22Z"
  },
  "organisations": {
    "org_id": 0,
    "name": "string",
    "description": "string",
    "created_by": 0,
    "status": "string",
    "created_at": "2019-08-24T14:15:22Z",
    "updated_at": "2019-08-24T14:15:22Z"
  },
  "payments": {
    "id": "string",
    "amount": 0,
    "currency": "string",
    "method": "string",
    "status": "pending",
    "createdAt": "2019-08-24T14:15:22Z"
  },
  "activity_logs": {
    "log_id": 0,
    "user_id": 0,
    "org_id": 0,
    "activity_type": "string",
    "description": "string",
    "ip_address": "string",
    "user_agent": "string",
    "created_at": "2019-08-24T14:15:22Z"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|users|[UserDetails](#schemauserdetails)|false|none|none|
|organisations|[OrganisationDetails](#schemaorganisationdetails)|false|none|none|
|payments|[Payment](#schemapayment)|false|none|none|
|activity_logs|[ActivityLog](#schemaactivitylog)|false|none|none|

<h2 id="tocS_UserDataExport">UserDataExport</h2>
<!-- backwards compatibility -->
<a id="schemauserdataexport"></a>
<a id="schema_UserDataExport"></a>
<a id="tocSuserdataexport"></a>
<a id="tocsuserdataexport"></a>

```json
{
  "user_data": {
    "user_id": 0,
    "name": "string",
    "email": "string",
    "role": "string",
    "profile_picture": "string",
    "auth_type": "string",
    "auth_provider": "string",
    "gdpr_consent": true,
    "status": "string",
    "last_login": "2019-08-24T14:15:22Z",
    "created_at": "2019-08-24T14:15:22Z",
    "updated_at": "2019-08-24T14:15:22Z"
  },
  "user_settings": [
    {
      "userId": 0,
      "emailNotifications": true,
      "theme": "light",
      "language": "string"
    }
  ],
  "organisations": [
    {
      "org_id": 0,
      "name": "string",
      "description": "string",
      "created_by": 0,
      "status": "string",
      "created_at": "2019-08-24T14:15:22Z",
      "updated_at": "2019-08-24T14:15:22Z"
    }
  ],
  "payments": [
    {
      "id": "string",
      "amount": 0,
      "currency": "string",
      "method": "string",
      "status": "pending",
      "createdAt": "2019-08-24T14:15:22Z"
    }
  ],
  "activity_logs": [
    {
      "log_id": 0,
      "user_id": 0,
      "org_id": 0,
      "activity_type": "string",
      "description": "string",
      "ip_address": "string",
      "user_agent": "string",
      "created_at": "2019-08-24T14:15:22Z"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|user_data|[UserDetails](#schemauserdetails)|false|none|none|
|user_settings|[[UserSettings](#schemausersettings)]|false|none|none|
|organisations|[[OrganisationDetails](#schemaorganisationdetails)]|false|none|none|
|payments|[[Payment](#schemapayment)]|false|none|none|
|activity_logs|[[ActivityLog](#schemaactivitylog)]|false|none|none|

<h2 id="tocS_RandomData">RandomData</h2>
<!-- backwards compatibility -->
<a id="schemarandomdata"></a>
<a id="schema_RandomData"></a>
<a id="tocSrandomdata"></a>
<a id="tocsrandomdata"></a>

```json
{
  "id": 0,
  "user_id": 0,
  "data": {},
  "created_at": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|false|none|none|
|user_id|integer|false|none|none|
|data|object|false|none|none|
|created_at|string(date-time)|false|none|none|

<h2 id="tocS_ChartData">ChartData</h2>
<!-- backwards compatibility -->
<a id="schemachartdata"></a>
<a id="schema_ChartData"></a>
<a id="tocSchartdata"></a>
<a id="tocschartdata"></a>

```json
{
  "labels": [
    "string"
  ],
  "datasets": [
    {
      "label": "string",
      "data": [
        0
      ]
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|labels|[string]|false|none|none|
|datasets|[object]|false|none|none|
|» label|string|false|none|none|
|» data|[number]|false|none|none|

<h2 id="tocS_Page">Page</h2>
<!-- backwards compatibility -->
<a id="schemapage"></a>
<a id="schema_Page"></a>
<a id="tocSpage"></a>
<a id="tocspage"></a>

```json
{
  "title": "string",
  "content": "string",
  "lastUpdated": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|title|string|false|none|none|
|content|string|false|none|none|
|lastUpdated|string(date-time)|false|none|none|

<h2 id="tocS_ContentInput">ContentInput</h2>
<!-- backwards compatibility -->
<a id="schemacontentinput"></a>
<a id="schema_ContentInput"></a>
<a id="tocScontentinput"></a>
<a id="tocscontentinput"></a>

```json
{
  "title": "string",
  "body": "string",
  "authorId": 0,
  "type": "article",
  "status": "draft"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|title|string|false|none|none|
|body|string|false|none|none|
|authorId|integer|false|none|none|
|type|string|false|none|none|
|status|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|article|
|type|blog_post|
|type|page|
|status|draft|
|status|published|

<h2 id="tocS_Content">Content</h2>
<!-- backwards compatibility -->
<a id="schemacontent"></a>
<a id="schema_Content"></a>
<a id="tocScontent"></a>
<a id="tocscontent"></a>

```json
{
  "title": "string",
  "body": "string",
  "authorId": 0,
  "type": "article",
  "status": "draft",
  "id": 0,
  "createdAt": "2019-08-24T14:15:22Z",
  "updatedAt": "2019-08-24T14:15:22Z"
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ContentInput](#schemacontentinput)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» id|integer|false|none|none|
|» createdAt|string(date-time)|false|none|none|
|» updatedAt|string(date-time)|false|none|none|

<h2 id="tocS_BlogPost">BlogPost</h2>
<!-- backwards compatibility -->
<a id="schemablogpost"></a>
<a id="schema_BlogPost"></a>
<a id="tocSblogpost"></a>
<a id="tocsblogpost"></a>

```json
{
  "title": "string",
  "body": "string",
  "authorId": 0,
  "type": "article",
  "status": "draft",
  "id": 0,
  "createdAt": "2019-08-24T14:15:22Z",
  "updatedAt": "2019-08-24T14:15:22Z",
  "excerpt": "string",
  "tags": [
    "string"
  ]
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Content](#schemacontent)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» excerpt|string|false|none|none|
|» tags|[string]|false|none|none|

