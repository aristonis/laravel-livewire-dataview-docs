# بداية سريعة

## إنشاء مكون جديد

* قم بإنشاء مكون جديد باستخدام هذا الأمر الذي سينشئ فئة `Component` جديدة داخل مجلد `Livewire`.
  * يمكنك استبدال `Dataview` بأي مسار تحتاجه، كما تفعل عند إنشاء مكون عادي في `Livewire`.
  * `PostData` هو اسم هذا المكون.

```bash
php artisan dataview:make Dataview/PostsData
```

## تهيئة فئة المكون

* يجب عليك تمرير مكون عرض العنصر. مكوننا هو مجرد حاوية تحتاج إلى مكون `item-view`.
* سيتم تمرير العناصر تلقائيًا إلى مكون `item-view`.
* يجب أن يكون `item-view` مكون Livewire، وإذا لم يتم العثور عليه، فسيتم إطلاق استثناء `InvalidItemViewException`.

```php

namespace App\Livewire\Dataview;

use App\Models\Post;
use Aristonis\LaravelLivewireDataview\DataViewComponent;

class PostsData extends DataViewComponent
{
    protected function configure(): void
    {
        $this->setItemView('posts.post-card');
        
    }

    protected function query()
    {
        return Post::query()->with('comments');
    }
}
```

* الآن بالنسبة لفئة عرض العنصر، يجب عليك تحديد خاصية `item` عامة أو استخدام طريقة mount.

```php

namespace App\Livewire\posts;

use Livewire\Component;

class PostCard extends Component
{
    // Option 1
    public $item;

    // Option 2
    public function mount($item)
    {
        $this->item = $item;
    }

    public function render()
    {
        return view('livewire.posts.post-card');
    }
}
```

* استدعاء المكون في صفحة blade الخاصة بك

```php
<livewire:dataview.posts-data>
```
