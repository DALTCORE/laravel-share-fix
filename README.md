# Laravel 5.4 package share fix

Laravel 5.4 compatible

Will give back the functionality thats taken out in 5.4:
```
share Method Removed

The share method has been removed from the container. This was a legacy method that has not been documented in several years. If you are using this method, you should begin using the  singleton method instead:

$container->singleton('foo', function () {
    return 'foo';
});
```

```
composer require daltcore/laravel-share-fix dev-master
```

Change in your `bootstrap/app.php`

```php
$app = new Illuminate\Foundation\Application(
    realpath(__DIR__ . '/../')
);
```
to
```php
$app = new DALTCORE\ShareFix\Application(
    realpath(__DIR__ . '/../')
);
```

Now you can use `$this->app->share` again.
