This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

## Laravel React Crud App

<hr>

**username table 🎨**

```
id
username
```

**exercises table 🎈**

```
id
username
description
duration
date
```

<hr>

```

php artisan make:model username --all
php artisan make:model exercise --all

```
<hr>

Allow accessing 

```

Php artisan make:middleware cors

```

```php

        ->header('Access-Control-Allow-Origin', '*')
        ->header('Access-Control-Allow-Methods', 'GET, POST, PUT, DELETE, OPTIONS')
        ->header('Access-Control-Allow-Headers',' Origin, Content-Type, Accept, Authorization, X-Request-With')
        ->header('Access-Control-Allow-Credentials',' true');

```
in Kernel.php file

```php

 \App\Http\Middleware\Cors::class,

```

<hr>

## react packages

```

npm install bootstrap

npm install react-router-dom

npm install react-datepicker

npm install axios

```

![Capture1121212](https://user-images.githubusercontent.com/37043938/80126405-acea5c80-85b0-11ea-8275-c1ee7da5d49b.PNG)







