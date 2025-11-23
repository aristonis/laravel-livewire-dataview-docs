# installation

* Install the package on your project  by command

```bash
composer require aristonis/laravel-livewire-dataview
```

* Add ServicesProvider to project

```php
Aristonis\LaravelLivewireDataview\LaravelLivewireDataviewServiceProvider::class
```

* Optionally publish the package assets:

```bash
php artisan vendor:publish --tag=dataview-config   # copies config/dataview.php
```
