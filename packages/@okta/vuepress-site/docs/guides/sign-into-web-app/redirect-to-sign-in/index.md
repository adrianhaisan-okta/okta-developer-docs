---
title: Redirect to the Sign-In Page
---

To sign a user in, your application must redirect the browser to the Okta-hosted sign-in page. You can do this when a user visits a protected route or when the user clicks a button to sign in.

<StackSelector snippet="login-redirect"/>

The user is redirected to the hosted sign-in page where they authenticate. After successful authentication, the browser is redirected back to your application along with information about the user.

> Note: To customize the hosted sign-in page, see [Customize the Hosted Sign-in Page](/docs/guides/custom-hosted-signin/).

You can also define protected routes or areas of your application that will always require authentication.

<NextSectionLink/>
