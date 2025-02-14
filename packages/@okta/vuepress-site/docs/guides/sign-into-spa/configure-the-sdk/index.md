---
title: Configure the SDK
---

You'll need two values from the Okta Application and the Developer Console you worked with in <GuideLink link="../create-okta-application">Create an Okta Application</GuideLink>:

* **Client ID** - Find it in the applications list or on the application's **General** tab.
* **Okta domain** - Find it on the Developer Console dashboard in the upper-right corner as the **Org URL**.

In your application code, build a config object. This is used to initialize the Okta services with the values specific to your application:

```javascript
const config = {
  clientId: '{clientId}',
  issuer: 'https://{yourOktaDomain}/oauth2/default',
  redirectUri: 'http://localhost:8080/implicit/callback',
  scope: 'openid profile email',
};
```

> Note: `openid`, `profile`, and `email` are reserved scopes in OpenID Connect that allow you to get access to user's data. You can read more about scopes [here](/docs/reference/api/oidc/#scopes).

You can also build it from dynamic values like environment variables:

```javascript
const OKTA_DOMAIN = process.env.DOMAIN;
const CLIENT_ID = process.env.CLIENT_ID;
const CALLBACK_PATH = '/implicit/callback';

const ISSUER = `https://${OKTA_DOMAIN}/oauth2/default`;
const HOST = window.location.host;
const REDIRECT_URI = `http://${HOST}${CALLBACK_PATH}`;
const SCOPES = 'openid profile email';

const config = {
  issuer: ISSUER,
  clientId: CLIENT_ID,
  redirectUri: REDIRECT_URI,
  scope: SCOPES,
});
```

With the configuration ready, initialize the SDK:

<StackSelector snippet="config"/>

<NextSectionLink/>
