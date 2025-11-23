# Basic

## publish view component

publish view and customize styling

```bash
    php artisan vendor:publish --tag=dataview-view
```

## create new component

* Create a new component using this command that will create a new Component class inside the Livewire folder.
  * You can replace `Dataview` with any path you need, like when creating a normal component in Livewire.
  * `PostData` is the Component name.

```bash
php artisan dataview:make Dataview/PostsData 
#  or auto create item-view component by this 
# this command will generate PostsData component and Item Component
php artisan dataview:make Dataview/PostsData --with-item=Dataview/PostItem

```

## Configure class component

* You must pass the view item component. Our component is just a container that needs an `item-view` component.
* Items will be passed automatically to the `item-view` component.
* `item-view` should be a Livewire component. If not found, it will throw Exception `InvalidItemViewException`.

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

* Now for the item view class, you should define a public `item` property or use the mount method.

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

* Call the component on your Blade page

```php
 <livewire:dataview.posts-data>
```
