# الإعدادات

- يتحكم `config/dataview.php` في السلوك الأساسي:

> - يمكنك تجاوز الإعدادات الافتراضية لمكون واحد داخل دالة `configure` في فئة المكون.
> - سيتم الحصول على الإعدادات الافتراضية من ملف الإعدادات وتطبيقها على جميع المكونات. إذا قام أحد المكونات بتجاوز بعض الإعدادات في فئة المكون، فسيتم تطبيقها فقط على ذلك المكون.
> - لتجاوز الإعدادات لمكون واحد، يمكنك الاطلاع على قسم الاستخدام.

- نشر الإعدادات عن طريق الأمر

```bash
php artisan vendor:publish --tag=dataview-config   # copies config/dataview.php
```

## ترقيم الصفحات

```php
    'pagination' => [
        /**
         * item count on each page
         */
        'per_page' => 15,
        // enable / disable pagination feture  can have bool values
        'enable' => true,
        'page_name' => 'page',
    ],

```

## العنصر

- `keyName`: عند عرض المجموعة وتمريرها إلى الحلقة في `livewire`، يجب استخدام `wire:key` واستخدام هذا الإعداد لتحديد المفتاح المستخدم من فئة النموذج. القيمة الافتراضية هي `id` ويجب أن يكون اسم المفتاح هو عمود في كائن النموذج.

```php
    /**
     * item configrations
     */
    "item" => [
        "keyName" => "id",
    ],


```
