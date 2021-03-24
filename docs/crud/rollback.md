---
title: Quickstart
permalink: /docs/rollback-crud
layout: page
---

## Rollback Crud

Rollback a crud

```php
php artisan administrable:rollback:crud {model}
```

The ***--rollback*** option is used to run the rollback artisan command. The default value is *true*

```php
php artisan administrable:make:crud {Model} --rollback="true"
```

or

```php
php artisan administrable:make:crud {Model} --rollback="false"
```

**NB:**

- The model must have been defined in *administrable.yaml* file.

Example:

```php
php artisan administrable:rollback:crud Post
```

By default the rollback artisan command will be run, if you want to change it.

```php
php artisan administrable:rollback:crud Post --rollback
```

or with the short versioning

```php
php artisan administrable:rollback:crud Post -r
```
