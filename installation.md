# Installation

- [Installation](#installation)
    - [Server Requirements](#server-requirements)
    - [Installing Lucy](#installing-lucy)
    - [Application URL](#application-url)

<a name="installation"></a>
## Installation

<a name="server-requirements"></a>
### Server Requirements

Before we begin, make sure your server meets the following requirements:

- PHP >= 5.5.9
- OpenSSL PHP Extension
- PDO PHP Extension
- Mbstring PHP Extension
- Tokenizer PHP Extension

<a name="installing-lucy"></a>
### Installing Lucy

First, download Lucy and extract it into your web server folder (example for Apache: `/var/www/html`). After that, create the database in **MySQL**.  Let's say, you create the database named **lucy**.

#### Step 1 - Welcome Screen

The foundation of Lucy, [Laravel](https://laravel.com), is designed to allow HTTP access to the application from your `public` folder only. It means that Lucy will be available at `yourdomain.com/public`. However, for production you will probably want to have your application available at `yourdomain.com`. In [next section](#application-url), we will show you how to accomplish that.

The installation wizard will displayed when you access Lucy for the first time. Click `Next Step` to continue.

![alt text](http://s33.postimg.org/efa073xun/01_install.png "Welcome Screen")

#### Step 2 - Environment Settings

We use `.env` file to save the base environment settings. Go to `DB_` section and ignore the others. Set your database settings for your application (see the image below for example). After that, click `Save .env` and click `Next Step` to continue.

![alt text](http://s33.postimg.org/6jvbxxfrz/02_install.png "Environment Settings")

#### Step 3 - Requirements

Lucy will check if your server meets the Lucy system requirements. Click `Next Step` to continue (if all requirements is pass).

![alt text](http://s33.postimg.org/nf6slxtzz/03_install.png "Requirements")

#### Step 4 - Permissions

Lucy will check if the following folders is writable by your web server. Click `Next Step` to continue.

![alt text](http://s33.postimg.org/npa6ax067/04_install.png "Permissions")

#### Step 5 - Finished

The installation is success. Click `Click here to exit` and you will redirect to login page.

![alt text](http://s33.postimg.org/6j5lsz38f/05_install.png "Finished")

And the default user is:

```
username: admin password: lucy12345
```
