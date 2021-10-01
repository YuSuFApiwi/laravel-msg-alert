# Welcome in the package laravel-msg-alert

# laravel-msg-alert

| Laravel Version     | Is Working? |
| ---      | ---       |
| 8.x | Yes         |
| 7.x | Yes        |
| 6.x | Yes        |
| >= 5.5 | Yes        |

### install

Using Composer

    composer require YuSufApiwi/laravel-msg-alert

### Laravel >= 5.5

That's it! The package is auto-discovered on 5.5 and up!

#* But <= 5.4
    Add the service provider to `config/app.php`

```php
'Toastr'  => YuSuFApiwi\Toastr\Facades\Toastr::class,
```

### Options

You can set custom options for Reminder. Run:

    php artisan vendor:publish

to publish the config file for toastr.

You can see [toastr's documentation](http://codeseven.github.io/toastr/demo.html) to custom your need.


> You can use toastr() function available.

### Dependencies

jQuery [toast](https://github.com/CodeSeven/toastr), you need to add css and js to your html.

### Basic


* Toastr::info('message', 'title', ['options']);

* Toastr::success('message', 'title', ['options']);

* Toastr::warning('message', 'title', ['options']);

* Toastr::error('message', 'title', ['options']);

* Toastr::clear();

* Toastr()->info('message', 'title', ['options']);

```php
<?php

Route::get('/', function () {
    Toastr::success('Messages in here', 'Title', ["positionClass" => "toast-top-center"]);

    return view('welcome');
});
```

Then

You should add `{!! Toastr::message() !!}` to your html.

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Laravel</title>
        <link rel="stylesheet" href="http://cdn.bootcss.com/toastr.js/latest/css/toastr.min.css">
    </head>
    <body>
        <div class="container">
            <div class="content">
                <div class="title">Laravel 5</div>
            </div>
        </div>
		<script src="http://cdn.bootcss.com/jquery/2.2.4/jquery.min.js"></script>
        <script src="http://cdn.bootcss.com/toastr.js/latest/js/toastr.min.js"></script>
        {!! Toastr::message() !!}
    </body>
</html>
```

### MIT
