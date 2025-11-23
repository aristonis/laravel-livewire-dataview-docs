# التثبيت

* قم بتثبيت المكتبة ضمن المشروع عن طريق الأمر

```bash
composer require aristonis/laravel-livewire-dataview
```

* أضف `ServicesProvider` إلى المشروع

```php
Aristonis\LaravelLivewireDataview\LaravelLivewireDataviewServiceProvider::class
```

* اختياري: يمكنك نشر ملفات الحزمة ضمن المشروع

```bash
php artisan vendor:publish --tag=dataview-config   # copies config/dataview.php
```
