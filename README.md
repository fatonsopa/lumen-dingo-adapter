# Dingo Adapter for Lumen
Using Dingo + JWT in your Lumen Based Application with no pain.

### Installation

```
composer require durimjusaj/lumen-dingo-adapter
```

### Configuration

In your `bootstrap/app.php` file add this line:

```php
$app->register(Zeek\LumenDingoAdapter\Providers\LumenDingoAdapterServiceProvider::class);
```

Below is environment variable you should configure to make this package works out of the box:

```env
API_PREFIX=api
```

### Guarding Your Routes via Dingo Routing

```php
$app->make(Dingo\Api\Routing\Router::class)->version('v1', function ($api) {
    $api->group([
        'middleware' => 'api.auth',
    ], function ($api) {
        $api->get('/', 'App\Http\Controllers\DefaultController@index');
    });
});
```


This package is copy of (https://github.com/krisanalfa/lumen-dingo-adapter).