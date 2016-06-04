# CRUD Generator

- [Introduction](#introduction)
- [Create a new Module](#create)
- [Delete a Module](#delete)

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
<img src="/storage/docs/02-crud.jpeg" class="img-responsive img-rounded">

   > **Note:** The primary key of your table is automatically created and the name is `id`.
   
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

One thing you should before delete a module, make sure you have dropped the table of the module.

And if you sure want to delete, just click **Delete** button and click **Continue**.

Lucy will delete all your module's files and the permissions.
