# Installation

- [Server Requirements](#server-requirements)
- [Installing Lucy](#installing-lucy)
- [Application URL](#application-url)
    - [Shared Hosting](#application-url-shared-hosting)

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

First, download Lucy and extract it into your web server folder (example for Apache: `/var/www/html`). After that, create the database in **MySQL** (**mysql**) or **PostgreSQL** (**pgsql**).  Let's say, you create the database named **lucy**.

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

<a name="application-url-shared-hosting"></a>
### Shared Hosting

But, what if you are hosting your application on some shared hosting and you are not able to change your document root? In that case, you will have to modify some application files.

Lets say that you want to upload your application to some shared hosting. Typically, there will be an `public_html` directory where you would upload your application since everything that's inside that directory will be accessible via HTTP.

1. Upload Lucy

   So, in this case, the best way is to upload Lucy application into it's own folder that is **one level** above the `public_html` folder. In that case, your directory structure will look something like this:
   ```
   .
   ..
   /Lucy
   /public_html
   /other_folder
   ```
   In this case, we have uploaded our whole Lucy app into `Lucy` folder that is on the same level as your `public_html` folder, and it is not accessible from your browser.

2. Copy `public` files

   Now you need to copy everything from Lucy's `public` folder to `public_html` folder on your server (you can remove `Lucy/public` folder after moving those files).
   This will allow us to change the name and location of public folder for our application.

3. Update index.php file

   The final step is to update the `index.php` file you have copied from `public` to `public_html` directory. So, go to `public_html` and edit `index.php` file and update it as following:
   ```
   // Update path to autoload.php file...
   require __DIR__.'/../Lucy/bootstrap/autoload.php';

   // Update path to app.php file...
   $app = require_once __DIR__.'/../Lucy/bootstrap/app.php';

   // This line should be added right after previous line where $app variable 
   // is defined and it is used to tell Laravel where your public folder is now. 
   // Do not change it, just copy and paste it!
   $app->instance('path.public', __DIR__);

   // Leave the rest unchanged...
   ```

   And that's it, Lucy application will now be available at `yourdomain.com`, and all application files will be secured.
