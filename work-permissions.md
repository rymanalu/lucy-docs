# Working with Permissions

- [Introduction](#introduction)
- [Applying the Permissions](#applying-the-permissions)
    - [Controller](#applying-the-permissions-controller)
    - [Model](#applying-the-permissions-model)
    - [Route](#applying-the-permissions-route)
    - [View](#applying-the-permissions-view)

<a name="introduction"></a>
## Introduction

Lucy comes with some default permissions but, if some of them does not fit your needs, they can be easily modify them. Adding new permissions is a breeze too.

<a name="applying-the-permissions"></a>
## Applying the Permissions

Permissions can be applied in Backend (Controller, Model, and Route) and Frontend (View).

<a name="applying-the-permissions-controller"></a>
### Controller

```
<?php

namespace App\Http\Controllers;

// Import this class...
use LucyGuard;

class ExampleController extends Controller
{
    // Other methods on this controller...

    // Applying permission in controller example...
    protected function check($permission)
    {
        // Pass the permission name (or you can pass an array of permissions name) in first argument.
        // It will strictly require all passed permissions to be true in order to grant access.
        // Or you can pass a boolean true in second argument, and it will grant access if any permission passes the check.
        if (LucyGuard::hasAccess($permission)) {
            // Anything what user can do if user passes the check...
        } else {
            // User did not passes the check...
        }
    }

    // Other methods on this controller...
}
```

<a name="applying-the-permissions-model"></a>
### Model

Same like you apply the permissions in [controller](#applying-the-permissions-controller).

<a name="applying-the-permissions-route"></a>
### Route

Applying permissions in route is so easy. Follow this example:

```
<?php

// Other routes...

// Just use the LucyRoute class, and define your URI, controller with method name,
// and pass the permission name in third argument.
// In this example, when user want to view users list, the user must has "users.view" permission.
LucyRoute::get('users', 'UserController@index', 'users.view');

// Other routes...
```

<a name="applying-the-permissions-view"></a>
### View

Lucy comes with elegant [**Blade**](https://laravel.com/docs/5.2/blade) directive (`@access('permission_name')`) to apply the permissions.

```
@access('users.create')
    <!-- Anything here will be displayed only if currently logged in user has "user.create" permission... -->
    <a class="btn btn-primary pull-right" href="/users-management/users/create" title="Create"><i class="fa fa-plus fa-fw"></i></a>
@endaccess
```
