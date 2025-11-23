# الإعدادات

- يتحكم `config/dataview.php` في السلوك الأساسي:

> -يمكن تعديل الإعدادت من اجل مكون واحد عن طريق التابع  `configure`
>
> -جميع الإعادت المعرفة ضمن ملف الإعدادت تطبيق على جميع المكونات المنشئة ولكن إذا تم إعادة تعريفها ضمن التابع `configure`  سيتم تطبيقها القيمة الجديدة على الصف نفسه فقط
> -لمعرفة الطرق المخصصة لكل خاصية ضمن الإعدادت   تم توضيحها ضمن قسم الاستخدام

- نشر الإعدادت عن طريق الأمر

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
