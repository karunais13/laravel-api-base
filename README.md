# Laravel API Base

## About

Laravel API Base allows you to jump start your API development quickly, without time consuming installation and setup proces.

## Features

* Manage Laravel Passport clients page
  https://laravel-base-api.test/admin/oauth
* API documentation with Swagger UI, integrated with Laravel Passport
  https://laravel-base-api.test/api/documentation
* Sample API and api routes integrated using Dingo API  
* LogViewer
https://laravel-base-api.test/admin/logviewer
* All HTTP request data automatically log using Spatie HTTP Logger and can be view from LogViewer
* Dedicated query string filtering class
https://laracasts.com/series/eloquent-techniques/episodes/4
* Easy user verification (user register and confirm via email) using Jrean Laravel User Verification

## Packages included

* Laravel Passport
https://laravel.com/docs/5.6/passport
* Laravel Swagger
https://github.com/DarkaOnLine/L5-Swagger
* Dingo API 
https://github.com/dingo/api
* GuzzleHTTP
https://github.com/guzzle/guzzle
* Laravel CORS
https://github.com/barryvdh/laravel-cors
* Spatie HTTP Logger
https://github.com/spatie/laravel-http-logger
* Arcanedev Log Viewer
https://github.com/ARCANEDEV/LogViewer
* Laravel User Verification
https://github.com/jrean/laravel-user-verification

## Installation

* git clone git@srv.nazrol.tech:internal/laravel-api-base.git
* composer install
* php artisan key:generate
* update your database config at .env file
* copy specific config from .env.example into .env file
* php artisan migrate
* enjoy!

## How to

### Dedicated query string filtering class

```
<?php

namespace App\Http\Filters;

use Illuminate\Database\Eloquent\Builder;

class UserFilters extends QueryFilters
{
    /**
     * Filter by latest.
     *
     * @param  string $order
     * @return Builder
     */
    public function latest($order = 'desc')
    {
        return $this->builder->orderBy('created_at', $order);
    }

    /**
     * Filter by email.
     *
     * @param  string $email
     * @return Builder
     */
    public function email($email)
    {
        return $this->builder->where('email', $email);
    }

    /**
     * Filter by name.
     *
     * @param  string $name
     * @return Builder
     */
    public function name($name)
    {
        return $this->builder->where('name', 'like', "%$name%");
    }
}
```

## TODO

* Spatie Laravel Permission
https://github.com/spatie/laravel-permission
* Spatie Laravel Medialibrary
https://github.com/spatie/laravel-medialibrary
* Spatie Laravel Sluggable
https://github.com/spatie/laravel-sluggable
* Spatie Laravel Tags
https://github.com/spatie/laravel-tags
* Owen-It Laravel Auditing
http://www.laravel-auditing.com/
* Rutorika Sortable
https://github.com/boxfrommars/rutorika-sortable
* Eduardokum Laravel Mail Auto Embed
https://github.com/eduardokum/laravel-mail-auto-embed