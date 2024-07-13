<!-- npx widdershins documentation/swagger.yaml -o documentation/apiDocs.md --language_tabs javascript -->
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

API for managing users

Base URLs:

* <a href="{baseUrl}/api/v1">{baseUrl}/api/v1</a>

    * **baseUrl** -  Default: https://host-api-domain.com

        * https://host-api-domain.com

        * https://staging.host-api-domain.com

        * https://dev.host-api-domain.com

        * http://localhost:3000

# Authentication

- HTTP Authentication, scheme: bearer 

<h1 id="hng-boilerplate-node_web-default">Default</h1>

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

*Create a new user*

Add a new user to the system

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
  "id": "string",
  "name": "string",
  "email": "user@example.com"
}
```

<h3 id="post__auth_signup-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|User created successfully|[User](#schemauser)|
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

*User login*

Logs in an existing user

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
    "id": "string",
    "name": "string",
    "email": "user@example.com"
  },
  "token": "string"
}
```

<h3 id="post__auth_login-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Login successful|[UserResponse](#schemauserresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid credentials|None|

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

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

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
      "id": "string",
      "userId": "string",
      "action": "string",
      "timestamp": "2019-08-24T14:15:22Z"
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
|»» id|string|false|none|none|
|»» userId|string|false|none|none|
|»» action|string|false|none|none|
|»» timestamp|string(date-time)|false|none|none|
|» totalCount|integer|false|none|none|
|» currentPage|integer|false|none|none|
|» totalPages|integer|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

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
  "languageCode": "string",
  "regionCode": "string"
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

## put__settings

> Code samples

```javascript
const inputBody = '{
  "languageCode": "string",
  "regionCode": "string"
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
  "languageCode": "string",
  "regionCode": "string"
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

# Schemas

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

<h2 id="tocS_User">User</h2>
<!-- backwards compatibility -->
<a id="schemauser"></a>
<a id="schema_User"></a>
<a id="tocSuser"></a>
<a id="tocsuser"></a>

```json
{
  "id": "string",
  "name": "string",
  "email": "user@example.com"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|name|string|false|none|none|
|email|string(email)|false|none|none|

<h2 id="tocS_UserResponse">UserResponse</h2>
<!-- backwards compatibility -->
<a id="schemauserresponse"></a>
<a id="schema_UserResponse"></a>
<a id="tocSuserresponse"></a>
<a id="tocsuserresponse"></a>

```json
{
  "user": {
    "id": "string",
    "name": "string",
    "email": "user@example.com"
  },
  "token": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|user|[User](#schemauser)|false|none|none|
|token|string|false|none|none|

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
  "id": "string",
  "userId": "string",
  "action": "string",
  "timestamp": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|userId|string|false|none|none|
|action|string|false|none|none|
|timestamp|string(date-time)|false|none|none|

<h2 id="tocS_UserSettings">UserSettings</h2>
<!-- backwards compatibility -->
<a id="schemausersettings"></a>
<a id="schema_UserSettings"></a>
<a id="tocSusersettings"></a>
<a id="tocsusersettings"></a>

```json
{
  "languageCode": "string",
  "regionCode": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|languageCode|string|false|none|none|
|regionCode|string|false|none|none|

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

<h2 id="tocS_securitySchemes">securitySchemes</h2>
<!-- backwards compatibility -->
<a id="schemasecurityschemes"></a>
<a id="schema_securitySchemes"></a>
<a id="tocSsecurityschemes"></a>
<a id="tocssecurityschemes"></a>

```json
null

```

### Properties

*None*

