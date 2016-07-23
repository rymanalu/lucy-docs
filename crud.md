# CRUD Generator

- [Introduction](#introduction)
- [Create a new Module](#create)
- [Delete a Module](#delete)
- [Relationships](#relationships)
- [Create a new Module via Interactive CLI](#create-cli)

<a name="introduction"></a>
## Introduction
One of main features in Lucy is CRUD Generator.

The Generator generates all the file you need (migration, model, request, controller, view, and route) like when you create CRUD manually and of course in Laravel way. Plus, it will automatically create new [**permissions**](/docs/permissions).

For your information, this feature is just only a starter to help you create a new CRUD faster. And after that, you can freely custom your created CRUD.

<a name="create"></a>
## Create a new Module

1. Open **CRUD Generator** menu and click **Add** button.
<img src="/storage/docs/01-crud.jpeg" class="img-responsive img-rounded">
2. Fill all the required fields and build the table schema like this:
<img src="/storage/docs/02-crud.png" class="img-responsive img-rounded">

   > **Note:** The primary key of your table (`id`), `created_at` and `updated_at` column, automatically created by the Generator.
   
   > **Note:** The **Length**, **Default**, and **Comment** field is optional.
3. Click **Save**. It will take seconds to generate all files and migrate the table. You will see this if module successfully created:
<img src="/storage/docs/03-crud.jpeg" class="img-responsive img-rounded">
4. Click **Go to Module** button to see your created CRUD.
5. The files of your module will saved in path like this:

   File | Path
   --- | ---
   Migration | `/lucy_path/database/migrations/2016_06_12_120616_create_authors_table.php`
   Model | `/lucy_path/app/Models/Modules/Author.php`
   Request | `/lucy_path/app/Http/Requests/Modules/AuthorRequest.php`
   Controller | `/lucy_path/app/Http/Controllers/Modules/AuthorController.php`
   Route | `/lucy_path/app/Http/Routes/authors_route.php`
   Views | `/lucy_path/resources/views/modules/authors/form.blade.php`, `/lucy_path/resources/views/modules/authors/index.blade.php`, `/lucy_path/resources/views/modules/authors/view.blade.php`

<a name="delete"></a>
## Delete a Module

One thing you should before delete a module, make sure you have dropped the table of the module (do not forget to always use migration).

And if you sure want to delete, just click **Delete** button and click **Continue**.

Lucy will delete all your module's files and the permissions.

<a name="relationships"></a>
## Relationships

Sometimes when you create a new table, you must create a relationship to another table.

You can easily add a relationship in Lucy's CRUD Generator, by click the "green plus" button. For example, we will create a CRUD named **Books** that have `author_id` column (**MUST INTEGER**) that have a relationship with `authors` table.

<img src="/storage/docs/04-crud.png" class="img-responsive img-rounded">

And then, define the relationship. For this example, we will add a relationship between `books.author_id` and `authors.id`. Click **Save**.

<img src="/storage/docs/05-crud.png" class="img-responsive img-rounded">

When you generate this Books CRUD, Lucy will automatically define the relationship in Book's Model class. And don't forget to define the inverse relation in Author's Model class.

FYI, Laravel have an amazing doc about [Relationships](https://laravel.com/docs/5.2/eloquent-relationships).

<a name="create-cli"></a>
## Create a new Module via Interactive CLI

Since some developers prefered CLI instead of GUI, now we can create a new module via Artisan command. The command require an authentication before creating the module. Just give your email or username in `--login` and you will be asked for the password:

    php artisan lucy:crud Authors --table=authors --login=admin
