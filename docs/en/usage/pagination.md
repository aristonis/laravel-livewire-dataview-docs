# Pagination

## manage pagination

you can edit pagination property for one component  on `configure` method on component class
options :

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
            // write custom configration here
            $this->setPerPage(10);
           
       }

       // ...
   }
```

> this new configureation overwrtie default values from `dataview.php` config file and aplies just on one component
> if perPage value not valid `n<1`  or not vaild type `int`=> throw exception InvalidPerPageException

## globale confgration

to make your configration affect on all component you need to edit `dataview.php` config file
