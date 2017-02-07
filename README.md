#Laravel 5.4 package share fix

Laravel 5.4 compatible

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