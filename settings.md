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

You can find a detailed explanation from Facebook [here](https://developers.facebook.com/docs/apps/register). Make sure you that you have entered correct application domain on application's settings page.

<a name="socialite-google"></a>
#### Google+

First, go to [https://console.developers.google.com/project](https://console.developers.google.com/projet) and click **Create Project**.

And now, you will be able to enable Google+ API by click **Google+ API** and click **Enable**.

Go to credentials button and complete the form. After that, enter your `http://yourdomain.com` in **Authorized JavaScript origins** section and `http://yourdomain.com/socialite/login/google` in **Authorized redirect URIs** section.

Create the client ID and get your credentials.

<a name="socialite-twitter"></a>
#### Twitter

Create the your Twitter app [here](https://apps.twitter.com/), and fill all required fields. Remember, your callback URI is `http://yourdomain.com/socialite/login/twitter`!
