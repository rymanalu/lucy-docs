# Helpers

- [Introduction](#introduction)
- [Method Listing](#method-listing)
    - [avatar_path](#method-avatar-path)
    - [datatables](#method-datatables)
    - [link_to_avatar](#method-link-to-avatar)
    - [lucy_config](#method-lucy-config)
    - [lucy_log](#method-lucy-log)
    - [mail_send](#method-mail-send)
    - [transaction](#method-transaction)
    - [user_info](#method-user-info)

<a name="introduction"></a>
## Introduction

Lucy includes a variety of "helper" PHP functions. Many of these functions are used by the framework itself; however, you are free to use them in your own applications if you find them convenient.

<a name="method-listing"></a>
## Method Listing

<a name="method-avatar-path"></a>
#### `avatar_path`

The `avatar_path` function return the full path of given avatar. If the given avatar is `null`, it will return the base path (directory path) where the avatars saved:
    
    $avatar = avatar_path('image.png');
    // Return: "/your_lucy_path/public/storage/avatars/image.png"

    $avatarBasePath = avatar_path();
    // Return: "/your_lucy_path/public/storage/avatars"

<a name="method-datatables"></a>
#### `datatables`

The `datatables` function is a shortcut to `Datatables::of($builder)`:

    $datatables = datatables(\App\Models\User::all());

For detailed documentation of the datatables, click [here](https://github.com/yajra/laravel-datatables).

<a name="method-link-to-avatar"></a>
#### `link_to_avatar`

The `link_to_avatar` function return the link of the avatar based on given argument.

If the argument starts with `http` or `https`, it will return the argument. If the file in the argument is not exists or you don't give any argument, it will return `http://lorempixel.com/128/128/`. If the given argument is exists, it will return the link for the avatar:

    $linkToAvatar = link_to_avatar('image.png');
    // Return: "http://yourdomain.com/storage/avatars/image.png"

<a name="method-lucy-config"></a>
#### `lucy_config`

The `lucy_config` function return the value of the given config's key. Or you can set the value of the given config's ket by pass the value in second argument.

    $appName = lucy_config('APP_NAME');
    // Return: "Lucy"

    // Set the APP_DESC...
    lucy_config('APP_DESC', 'Complete PHP Starter App');
    // Return: boolean

<a name="method-lucy-log"></a>
#### `lucy_log`

The `lucy_log` function record the user's activities. For detailed information, click [here](/docs/logging-activities).

<a name="method-mail-send"></a>
#### `mail_send`

The `mail_send` function is convenient way to send an email based on your Mail Settings (use Queue or not).

    mail_send('emails.welcome', $dataToBindInTheView, function ($message) {
        $message->subject('Welcome to Lucy!');

        $message->to('rymanalu@gmail.com', 'Roni Yusuf Manalu');
    });

<a name="method-transaction"></a>
#### `transaction`

The `transaction` function execute a `Closure` within a database transaction.

If an exception is thrown within the transaction `Closure`, the transaction will automatically be rolled back. If the `Closure` executes successfully, the transaction will automatically be committed. You don't need to worry about manually rolling back or committing while using the `transaction` function:

    transaction(function () use ($request) {
        Comment::create($request->all());

        Post::where('id', $request->input('post_id'))->update(['is_commented' => true]);
    });

<a name="method-user-info"></a>
#### `user_info`

The `user_info` function return the current logged in user object (`App\Models\User`). Or you can pass a column of the `users` table to get the value of the column.

If user not logged in, it will return `null`.

    // If user is logged in...

    $user = user_info();
    // Return the App\Models\User object.

    // Get the user's name...
    $name = user_info('full_name')
    // Return: "Roni Yusuf Manalu"
    // Or...
    $name = $user->full_name;
    // Or...
    $name = user_info()->full_name;

    // You can get the user's role too...
    $role = user_info('role');
    // Return the App\Models\Role object.

    // Get the user's role name...
    $roleName = $role->name;
    // Return: "Administrator"
    // Or...
    $roleName = user_info('role')->name;

    // If the user is not logged in...
    $user = user_info();
    // Return: null
