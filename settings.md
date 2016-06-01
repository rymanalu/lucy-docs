# Settings

- [Settings](#settings)
    - [Socialite](#socialite)
        - [Facebook](#socialite-facebook)
        - [Google +](#socialite-google)
        - [Twitter](#socialite-twitter)

<a name="settings"></a>
## Introduction

Make sure you have a knowledge about Laravel configuration, you can find that [here](https://laravel.com/docs/5.2/configuration).

<a name="socialite"></a>
### Socialite

Integrate your authentication with popular social media like **Facebook**, **Google+**, and **Twitter**. Just switch on and fill your social media app credentials.

Here, we will show you how to get the social media app credentials.

<a name="socialite-facebook"></a>
#### Facebook

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
#### Google+

First, go to [https://console.developers.google.com/project](https://console.developers.google.com/projet) and click **Create Project**.

And now, you will be able to enable Google+ API by click **Google+ API** and click **Enable**.

Go to credentials button and complete the form. After that, enter your `http://yourdomain.com` in **Authorized JavaScript origins** section and `http://yourdomain.com/socialite/login/google` in **Authorized redirect URIs** section.

Create the client ID and get your credentials.

<a name="socialite-twitter"></a>
#### Twitter

Create the your Twitter app [here](https://apps.twitter.com/), and fill all required fields. Remember, your callback URI is `http://yourdomain.com/socialite/login/twitter`!
