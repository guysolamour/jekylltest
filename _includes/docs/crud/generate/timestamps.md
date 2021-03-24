### timestamps

By default for each model laravel manages the *created_at* and *updated_at* fields.
To deactivate it you can proceed as follows:

```yaml
Post:
  timestamps: false
```

It will add on the model the attribute

```php
protected $timestamps = false;
```