# Permissions Management

- [Introduction](#introduction)
- [Manage Permissions](#manage-permissions)

<a name="introduction"></a>
## Introduction

Permissions represent some concrete actions that specific [**role**](/docs/roles) can perform. For example, one of default permissions is `users.create`, and every user with role which has this permission can create a new user.

This means that, for example, you can create a role called `Manager`, and allow managers to only create a bew users, without them being able to update general settings, etc.

> **Note:** Lucy's permissions and all created [**modules**](/docs/crud) cannot be deleted from UI. Custom created permissions can be deleted without any problem.

<img src="/storage/docs/01-permissions.jpeg" class="img-responsive img-rounded">

<a name="manage-permissions"></a>
## Manage Permissions

Lucy support unlimited number of permissions, and they can be added via form provided below.

<img src="/storage/docs/02-permissions.jpeg" class="img-responsive img-rounded">

Permission **name** is used as key / constant inside the source code to check if user has permissions to perform some action, and display name is used inside the UI, to better explain what the permission is used for.
