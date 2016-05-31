# CRUD Generator

- [Introduction](#introduction)
- [Create a new Module](#create)
- [Delete a Module](#delete)

<a name="introduction"></a>
## Introduction
The main feature in Lucy is CRUD Generator.

The Generator generates all the file you need (migration, model, request, controller, view, and route) like when you create CRUD manually.

<a name="create"></a>
## Create a new Module

Give a try to create a new module by click **Add** button.

Just fill all the required field, and create your table schema.

> **Note:** The primary key of your table is automatically created and the name is `id`.

> **Note:** The **Length**, **Default**, and **Comment** field is optional.

When you hit the **Save** button, Lucy will automatically call the `artisan migrate` command (migrate the table) too.

<a name="delete"></a>
## Delete a Module

One thing you should before delete a module, make sure you have dropped the table of the module.

And if you sure want to delete, just click **Delete** button and click **Continue**.

Lucy will delete all your module's files.
