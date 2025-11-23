# Configuration

- `config/dataview.php` controls the base behaviour:

> - you can overied default congiration for one of component inside `configure` method on Component class
> - will get deafult congiration form config file then  and aplye it on all component and if one of component overwrite some config on Component class will aplye on just that component
> - to overwrite congiration for one component you can see Usage section

- publish configuration by command

```bash
php artisan vendor:publish --tag=dataview-config   # copies config/dataview.php
```

## pagination

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

## Item

-`keyName`: when render collection and passed to loop on `livewire` should use `wire:key`  and use this config to defain what key used from model class by default is `id` and should key name is column of model Object

```php
    /**
     * item configrations
     */
    "item" => [
        "keyName" => "id",
    ],


```
