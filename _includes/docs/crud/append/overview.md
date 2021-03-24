## Append Crud

To append one or many fields on an existing model.

```php
php artisan administrable:append:crud {model} --fields="field1,field2,field3"
```

with the short version

```php
php artisan administrable:append:crud {model} -f="field1,field2,field3"
```

**NB:**

- The model must exists
- The fields must be defined in the same way as that of the **administrable:make:crud** command in the  *administrable.yaml* file
