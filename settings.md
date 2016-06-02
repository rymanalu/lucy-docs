# Settings

- [Introduction](#introduction)
- [Socialite](#socialite)
    - [Facebook](#socialite-facebook)
    - [Google +](#socialite-google)
    - [Twitter](#socialite-twitter)

<a name="introduction"></a>
## Introduction

Make sure you have a knowledge about Laravel configuration, you can find that [here](https://laravel.com/docs/5.2/configuration).

Lucy has dynamic configurations / settings that you can find in **Settings** menu. Feel free to setting your app.

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
