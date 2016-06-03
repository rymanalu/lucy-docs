# Installation

- [Server Requirements](#server-requirements)
- [Installing Lucy](#installing-lucy)
- [Application URL](#application-url)

<a name="server-requirements"></a>
## Server Requirements

Before we begin, make sure your server meets the following requirements:

- PHP >= 5.5.9
- OpenSSL PHP Extension
- PDO PHP Extension
- Mbstring PHP Extension
- Tokenizer PHP Extension

<a name="installing-lucy"></a>
## Installing Lucy

First, download Lucy and extract it into your web server folder (example for Apache: `/var/www/html`). After that, create the database in **MySQL**.  Let's say, you create the database named **lucy**.

1. Welcome Screen

   The foundation of Lucy, [Laravel](https://laravel.com), is designed to allow HTTP access to the application from your `public` folder only. It means that Lucy will be available at `yourdomain.com/public`. However, for production you will probably want to have your application available at `yourdomain.com`. In [next section](#application-url), we will show you how to accomplish that.

   The installation wizard will displayed when you access Lucy for the first time. Click `Next Step` to continue.
<img src="/storage/docs/01-install.png" alt="Welcome Screen" class="img-responsive img-rounded">

2. Environment Settings

   We use `.env` file to save the base environment settings. Go to `DB_*` section and ignore the others. Set your database settings for your application (see the image below for example).

   After that, click `Save .env` and click `Next Step` to continue.
<img src="/storage/docs/02-install.png" alt="Environment Settings" class="img-responsive img-rounded">

3. Requirements

   Lucy will check if your server meets the Lucy system requirements. Click `Next Step` to continue (if all requirements is pass).
<img src="/storage/docs/03-install.png" alt="Requirements" class="img-responsive img-rounded">

4. Permissions

   Lucy will check if the following folders is writable by your web server. Click `Next Step` to continue.
<img src="/storage/docs/04-install.png" alt="Permissions" class="img-responsive img-rounded">

5. Finished

   The installation is success. Click `Click here to exit` and you will redirect to login page.
<img src="/storage/docs/05-install.png" alt="Finished" class="img-responsive img-rounded">

   And the credential of the default user is:
   ```
   username: admin password: lucy12345
   ```

<a name="application-url"></a>
## Application URL

Because Laravel only allow HTTP access to `public` folder, you must change the document root inside **nginx** or **Apache** configuration files, to point to your `public` directory.

And here is the references that will help you:
- [Apache](http://stackoverflow.com/questions/5891802/how-do-i-change-the-root-directory-of-an-apache-server)
    - [Create Apache Virtual Host](https://www.digitalocean.com/community/tutorials/how-to-set-up-apache-virtual-hosts-on-ubuntu-14-04-lts)
- [nginx](http://nginx.org/en/docs/beginners_guide.html)
