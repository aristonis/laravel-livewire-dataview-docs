# التثبيت

* ثم بتثيت المكتبة ضمن المشروع عن طريق الامر

```bash
composer require aristonis/laravel-livewire-dataview
```

* أضف `ServicesProvider` إلى المشروع

```php
Aristonis\LaravelLivewireDataview\LaravelLivewireDataviewServiceProvider::class
```

* اختياري يمكنك نشر اللفات ضمن المشروع

```bash
php artisan vendor:publish --tag=dataview-config   # copies config/dataview.php
```
