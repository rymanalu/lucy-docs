# Roles Management

- [Introduction](#introduction)
- [Manage Roles](#manage-roles)

<a name="introduction"></a>
## Introduction

Roles is like a position in jobs world. Lucy only allow users to have **only one** role and roles can have many [**permissions**](/docs/permissions).

Lucy comes with 2 default roles: **Administrator** and **User**.

<img src="/storage/docs/01-roles.jpeg" class="img-responsive img-rounded">

> **Note:** Lucy's default roles cannot be deleted from UI. Custom created roles can be deleted without any problem.

<a name="manage-roles"></a>
## Manage Roles

Lucy support unlimited number of roles, and they can be added via form provided below.

<img src="/storage/docs/02-roles.jpeg" class="img-responsive img-rounded">

Every role has **slug**, that is used as key inside the source code of application. **Name** is used inside the UI to better explain what it is. And **permissions** field used to assign permissions to the role.
