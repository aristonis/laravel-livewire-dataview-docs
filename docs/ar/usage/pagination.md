# التصفح

## إدارة التصفح

يمكنك تعديل خاصية التصفح لمكون واحد في دالة `configure` في فئة المكون
الخيارات :

- `$this->setPerPage(25)` : تغيير عدد العناصر في كل صفحة
- `$this->enablePagination()` :  تفعيل التصفح للمكون
- `$this->disablePagination()` : تعطيل التصفح

```php

   namespace App\Livewire\Dataview;

   use App\Models\Post;
   use Aristonis\LaravelLivewireDataview\DataViewComponent;

   class PostsData extends DataViewComponent
   {
       protected function configure(): void
       {
            //    ...
            // write custom configration here
            $this->setPerPage(10);
           
       }

       // ...
   }
```

> هذا الإعداد الجديد يستبدل القيم الافتراضية من ملف الإعدادات `dataview.php` ويطبق فقط على مكون واحد
> إذا كانت قيمة perPage غير صالحة `n<1` أو نوع غير صالح `int`=> يرمي استثناء InvalidPerPageException

## الإعدادات العامة

لتطبيق إعداداتك على جميع المكونات تحتاج إلى تعديل ملف الإعدادات `dataview.php`
