# Settings

- [Introduction](#introduction)
- [General](#general)
- [Socialite](#socialite)
    - [Facebook](#socialite-facebook)
    - [Google +](#socialite-google)
    - [Twitter](#socialite-twitter)
- [Authentication](#authentication)
    - [General](#authentication-general)
    - [Throttling](#authentication-throttling)
- [Registration](#registration)
- [Mail](#mail)

<a name="introduction"></a>
## Introduction

Make sure you have a knowledge about Laravel configuration, you can find that [here](https://laravel.com/docs/5.2/configuration).

Lucy has dynamic configurations / settings that you can find in **Settings** menu. Feel free to setting your app.

<a name="general"></a>
## General

General settings section is used for updating the base your app configuration like **Environment**, **Debug**, **URL**, **Timezone**, **App Name**, **App Initial Name**, and **App Description**. Once the settings has been updated, it will change inside entire system, so you don't have to edit any code at all.
<img src="/storage/docs/general-settings.jpeg" class="img-responsive img-rounded">

<a name="socialite"></a>
## Socialite

Integrate your authentication with popular social media like **Facebook**, **Google+**, and **Twitter**. Just switch on and fill your social media app credentials.

Here, we will show you how to get the social media app credentials.

<a name="socialite-facebook"></a>
### Facebook

You can find a detailed explanation from Facebook [here](https://developers.facebook.com/docs/apps/register). Or you can follow our steps:

1. Go to [https://developers.facebook.com/apps/](https://developers.facebook.com/apps/) and click **Create a New App**.
<img src="/storage/docs/01-fb.jpeg" class="img-responsive img-rounded">
2. Fill all the required fields and click **Create App ID**.
<img src="/storage/docs/02-fb.jpeg" class="img-responsive img-rounded">
3. Click **Get Started** in **Facebook Login** section.
<img src="/storage/docs/03-fb.jpeg" class="img-responsive img-rounded">
4. In **Client OAuth Settings**, fill **Valid OAuth redirect URIs** like this: `http://yourdomain.com/auth/socialite/login/facebook`. Then, **Save Changes**.
<img src="/storage/docs/04-fb.jpeg" class="img-responsive img-rounded">
5. Go to **Dashboard** to get your **App ID** and **App Secret**.
<img src="/storage/docs/05-fb.jpeg" class="img-responsive img-rounded">

<a name="socialite-google"></a>
### Google+

In order to get Google **APP ID ** and **APP Secret**, you must have a **Google Account**.

1. Go to [https://console.developers.google.com/](https://console.developers.google.com/). Click **My Project** and click **Create a project...**.
<img src="/storage/docs/01-google.jpeg" class="img-responsive img-rounded">
2. Fill the required fields and click **Create**.
<img src="/storage/docs/02-google.jpeg" class="img-responsive img-rounded">
3. After that, click **Google+ API** in **Social APIs** section.
<img src="/storage/docs/03-google.jpeg" class="img-responsive img-rounded">
4. **Enable** the API.
<img src="/storage/docs/04-google.jpeg" class="img-responsive img-rounded">
5. Go to Credentials.
<img src="/storage/docs/05-google.jpeg" class="img-responsive img-rounded">
6. Fill the form like this and click **What credentials do I need?**.
<img src="/storage/docs/06-google.jpeg" class="img-responsive img-rounded">
7. Create the **OAuth Client**. The **Authorized redirect URIs** is like this: `http://yourdomain.com/auth/socialite/login/google`.
<img src="/storage/docs/07-google.jpeg" class="img-responsive img-rounded">
8. Setup the OAuth consent screen.
<img src="/storage/docs/08-google.jpeg" class="img-responsive img-rounded">
9. Download your credentials and click **Done**.
<img src="/storage/docs/09-google.jpeg" class="img-responsive img-rounded">
10. Open the file and fill the **APP ID** and **APP Secret** in **Google+** socialite. Or you can click **Credentials** in your **Google APIs** and click the project name.
<img src="/storage/docs/10-google.jpeg" class="img-responsive img-rounded">
11. And then, copy the credentials.
<img src="/storage/docs/11-google.jpeg" class="img-responsive img-rounded">

<a name="socialite-twitter"></a>
### Twitter

1. Go to [https://apps.twitter.com/](https://apps.twitter.com/) and click **Create New App**.
<img src="/storage/docs/01-twitter.jpeg" class="img-responsive img-rounded">
2. Fill all the required fields and remember, your callback URL is: `http://yourdomain.com/auth/socialite/login/twitter`.
3. After your Twitter app created, click **Keys and Access Tokens** to get your **APP ID** and **APP Secret**.
<img src="/storage/docs/02-twitter.jpeg" class="img-responsive img-rounded">

<a name="authentication"></a>
## Authentication

Authentication settings section contains everything that will allow easy authentication configuration.
<img src="/storage/docs/auth-settings.jpeg" class="img-responsive img-rounded">

<a name="authentication-general"></a>
### General

- **Allow Remember Me** - used for enabling or disabling the checkbox for remembering the user, that is available on login page. If this option is set to OFF, users will be automatically logged out once their session expire.
- **Forgot Password** - used for enabling or disabling reset password feature. If it is set to OFF, users won't be able to reset their password if they forget it.
- **Reset Token Lifetime** - numeric variable that represent lifetime of password reset token (**in minutes**).

<a name="authentication-throttling"></a>
### Throttling

- **Throttle** - used to enable or disable authentication throttling.
- **Throttling Interval** - the time (**in minutes**) for which we check for failed logins.
- **Throttling Thresholds** - max number of failed login attempts before the user's account locked.

<a name="registration"></a>
## Registration

Registration settings section covers your app registration configuration.

- **Enable Registration?** - used for enabling or disabling registration.
- **Enable Activation?** - if this option is set to YES, every new created users must activate their account. The activation code will send to their email account. If this option is set to NO, every new created users will automatically activated.
- **Activation Code Lifetime** - number of **minutes** that the activation code should be considered valid.

<img src="/storage/docs/reg-settings.jpeg" class="img-responsive img-rounded">

<a name="mail"></a>
## Mail

Mail settings section provide the easiest way to set your app mail configurations. Feel free to setting this section. 

> **Note:** Since sending e-mail messages can drastically lengthen the response time of your application, many developers choose to queue e-mail messages for background sending. Set the **Use Queue?** to YES to enabling this feature.

<img src="/storage/docs/mail-settings.jpeg" class="img-responsive img-rounded">
