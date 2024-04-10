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

## react packages

```

npm install bootstrap

npm install react-router-dom

npm install react-datepicker

npm install axios

```

![Capture1121212](https://user-images.githubusercontent.com/37043938/80126405-acea5c80-85b0-11ea-8275-c1ee7da5d49b.PNG)


## controller

```php

<?php

namespace App\Http\Controllers;

use App\exercise;
use Illuminate\Http\Request;

class ExerciseController extends Controller
{
    /**
     * Display a listing of the resource.
     *
     * @return \Illuminate\Http\Response
     */
    public function index()
    {
        return response()->json(exercise::get(),200);
    }

    /**
     * Show the form for creating a new resource.
     *
     * @return \Illuminate\Http\Response
     */
    public function create()
    {
        //
    }

    /**
     * Store a newly created resource in storage.
     *
     * @param  \Illuminate\Http\Request  $request
     * @return \Illuminate\Http\Response
     */
    public function store(Request $request)
    {
        $exe = exercise::create($request->all());
        return response()->json($exe,200);
    }

    /**
     * Display the specified resource.
     *
     * @param  \App\exercise  $exercise
     * @return \Illuminate\Http\Response
     */
    public function show($id)
    {
        return response()->json(exercise::find($id),200);
    }

    /**
     * Show the form for editing the specified resource.
     *
     * @param  \App\exercise  $exercise
     * @return \Illuminate\Http\Response
     */
    public function edit(exercise $exercise)
    {
        //
    }

    /**
     * Update the specified resource in storage.
     *
     * @param  \Illuminate\Http\Request  $request
     * @param  \App\exercise  $exercise
     * @return \Illuminate\Http\Response
     */
    public function update(Request $request, exercise $exercise)
    {
        $exercise->update($request->all());
        return response()->json($exercise,200);
    }

    /**
     * Remove the specified resource from storage.
     *
     * @param  \App\exercise  $exercise
     * @return \Illuminate\Http\Response
     */
    public function destroy(Request $request, exercise $exercise)
    {
        $exercise->delete();
        return response()->json(null,204);
    }
}


```

```php

<?php

use Illuminate\Http\Request;

/*
|--------------------------------------------------------------------------
| API Routes
|--------------------------------------------------------------------------
|
| Here is where you can register API routes for your application. These
| routes are loaded by the RouteServiceProvider within a group which
| is assigned the "api" middleware group. Enjoy building your API!
|
*/

Route::middleware('auth:api')->get('/user', function (Request $request) {
    return $request->user();
});

//http://127.0.0.1:8000/api/exercises
Route::resource('exercises','ExerciseController');
//http://127.0.0.1:8000/api/users
Route::resource('users','UsernameController');

```




