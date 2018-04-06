---
title: laravel simple app with database
date: 2017-06-22 14:35:38
tags: [laravel]
---

<!-- toc -->

## Create new app

```bash
laravel new myapp
```

## Tasks without datebase

```php web.php
Route::get('/tasks', function () {
    $tasks = [
        "Go to store",
        "Finish the blog",
        "Clean the house'
    ];

    return view('welcome', compact('tasks'));
    /*
    or other variations for the last line
    return view('welcome')->with('tasks', $tasks);
    return view('welcome', ['tasks' => $tasks]);
    */
});
```

```html welcome.blade.php
<!doctype html>
<html>
<head>
<meta http-equiv="content-type" content="text/html; charset=utf-8" />

<title></title>

</head>

<body>
    <ul>
        @foreach ($tasks as $task)
            <li>{{ $task }}</li>
        @endforeach
    </ul>
</body>

</html>
```

visit myapp.dev


## Tasks with database

```bash .env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=blog
DB_USERNAME=root
DB_PASSWORD=
```
Create some tasks with [Sequal Pro](https://www.sequelpro.com), or whatever you like.

```sh
php artisan make:migration create_tasks_table --create=tasks
```

```php database/migrations/2017_06_21_140553_create_tasks_table.php
class CreateTasksTable extends Migration
{
    public function up()
    {
        Schema::create('tasks', function (Blueprint $table) {
                $table->increments('id');
                $table->text('body');
                $table->timestamps();
                });
    }

    public function down()
    {
        Schema::dropIfExists('tasks');
    }
}
```

```sh
php artisan migrate
```

```php 
Route::get('/tasks', function () {
    $tasks = DB::table('tasks')->get();
    return view('welcome', compact('tasks'));
});
```

## Database use Eloquent


    php artisan make:model Task


You can reference the task model in the terminal with tinker

```shell
php artisan tinker
```

    >>> Task::all()
    >>> App\Task::pluck('body').first()
    >>> $task = new App\Task
    >>> $task->body = 'Go to the market'
    >>> $task->save()

```php web.php
Route::get('/tasks', function () {
    $tasks = App\Task::all();
    return view('welcome', compact('tasks'));
});
```






