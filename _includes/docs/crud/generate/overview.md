## Crud


This command generates the crud (***model***, ***controller***, ***migration***, ***form***, ***views***, ***seed***) for a particular model.

```php
php artisan administrable:make:crud {Model}
```

The ***--migrate*** option is used to run artisan migrate command

```php
php artisan administrable:make:crud {Model} --migrate="true"
```

or

```php
php artisan administrable:make:crud {Model} --migrate="false"
```

**NB:** The default value is *true*.

To adapt the generation, a configuration file ***administrable.yaml*** located at the root of the project is used. This file uses the **Yaml** language. If you do not know this syntax you can go [to the official website] (https://www.yaml.org) to learn more.

Example of model declaration: ***Post***

```yaml
Post:
name: { name: name, type: string, rules: nullable, slug: true }
image: { name: image, type: image, rules: required }
breadcrumb: name
imagemanager:
    - front
    - back
    - images
```

***NB***: The name of the model is compulsory and must correspond to that defined in the configuration file.
