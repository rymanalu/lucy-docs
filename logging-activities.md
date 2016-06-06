# Logging Activities

- [Introduction](#introduction)
- [Logging](#logging)

<a name="introduction"></a>
## Introduction

For security purpose, know what users do in your app is a must. And thats why we have **Logs** menu.

<img src="/storage/docs/logs.jpeg" class="img-responsive img-rounded">

<a name="logging"></a>
## Logging

Lucy have a built in function named `lucy_log($message, $user = null)` that will help you to logging user's activities.

Example:

```
<?php

class ExampleController extends Controller
{
    // Other methods on this controller...

    public function store(Request $request)
    {
        // The first argument is for description of user's activity.
        // The second argument is optional. If you leave it null, we will assume
        // that you will record the current user login activities.
        // Give the id of other user to the second argument, and it will record
        // the user who have that id.
        lucy_log('Create a new example.');
    }

    // Other methods on this controller...
}

```
