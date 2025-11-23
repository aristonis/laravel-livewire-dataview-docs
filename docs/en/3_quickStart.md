# Quick start

## create new component

* create new component by this command that will create new Component class inside Livewire  Folder
  * you can replase `Dataview` with any path you need like when create normal component on livewire
  * `PostData` this Component name

```bash
php artisan dataview:make Dataview/PostsData 

```

## congiure class component

* you must pass view item componet pass our component is just a container that need `item-view` component
* will pass items automaticly to `item-view` component
* `item-view` should be livewire component if not found will throw Exception `InvalidItemViewException`

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

* now for item view class you should defain public `item` property or use mount method

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

* call component on you blade page

```php
 <livewire:dataview.posts-data>
```
