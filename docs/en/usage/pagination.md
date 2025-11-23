# Pagination

## Manage pagination

You can edit the pagination property for one component in the `configure` method of the component class.
Options:

- `$this->setPerPage(25)` : change item count on each page
- `$this->enablePagination()` :  enable pagination for component
- `$this->disablePagination()` : disable pagination

```php

   namespace App\Livewire\Dataview;

   use App\Models\Post;
   use Aristonis\LaravelLivewireDataview\DataViewComponent;

   class PostsData extends DataViewComponent
   {
       protected function configure(): void
       {
            //    ...
            // write custom configuration here
            $this->setPerPage(10);
           
       }

       // ...
   }
```

> This new configuration overwrites default values from `dataview.php` config file and applies only to one component.
> If perPage value is not valid `n<1` or not a valid type `int` => throws exception InvalidPerPageException

## Global configuration

To make your configuration affect all components, you need to edit the `dataview.php` config file.
