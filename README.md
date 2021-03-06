# Instagram

A simple inspired by socialite library for laravel to authenticate users and obtain data from instagram api.

[![Total Downloads](https://poser.pugx.org/DotEnv/instagram/downloads.svg)](https://packagist.org/packages/dotenv/instagram)
[![Latest Stable Version](https://poser.pugx.org/DotEnv/instagram/v/stable.svg)](https://packagist.org/packages/dotenv/instagram)
[![Build Status](https://travis-ci.org/DotEnv/instagram.svg?branch=master)](https://travis-ci.org/DotEnv/instagram) 

### Installing
The package installation can be done with composer by the following command:

```shell
composer require dotenv/instagram
```

## Usage

### 1 - Add the ServiceProvider in the app/config.php file.

```php
Dotenv\Instagram\Providers\InstagramServiceProvider::class,

```

### 2 - Register an alias in the app/config.php file.

```php
'Instagram' => Dotenv\Instagram\Facades\Instagram::class,

```

### 3 - Rgister a facade alias in app/config.php file.

```php
'Instagram' => Dotenv\Instagram\Facades\Instagram::class,

```

### 4 - Publish config file.

```php
php artisan vendor:publish --provider="dotenv\instagram"

```

### 5 - How to use it?

```php
Route::get('auth/', function() {
	
	return \Instagram::authenticate();
});

Route::get('auth/callback', function() {
	
	$user = \Instagram::retrieveUser();

   	$userFromToken = \Instagram::userFromToken($user->token);
});

```

### 6 - Go to wiki to see the full documentation.

[Wiki](https://github.com/DotEnv/instagram/wiki)

## License

Instagram library is licensed under [The MIT License (MIT)] (https://github.com/dotenv/instagram/blob/master/LICENSE)(LICENSE).
