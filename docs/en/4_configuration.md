# Configuration

- `config/dataview.php` controls the base behaviour:

> - You can override the default configuration for one component inside the `configure` method on the Component class.
> - It will get the default configuration from the config file and apply it to all components. If one component overwrites some config in the Component class, it will apply only to that component.
> - To overwrite configuration for one component, you can see the Usage section.

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

- `keyName`: When rendering a collection and passing it to a loop in `livewire`, you should use `wire:key` and use this config to define what key is used from the model class. By default, it is `id` and the key name should be a column of the model Object.

```php
    /**
     * item configrations
     */
    "item" => [
        "keyName" => "id",
    ],


```
