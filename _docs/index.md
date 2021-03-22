---
title: Quickstart
permalink: /docs/
layout: docs
---

Installation via composer

```bash
composer require guysolamour/laravel-administrable
```

### 1. Create database

Open ***.env*** file and fill database credentials
next run

```php
php artisan cmd:db:create
```

This command will create your database according to your ***.env*** file

### 2. Administration installation

```php
php artisan administrable:install
```

The ***--debug_packages*** option is used to add some development packages
such as (the debugbar and others). The default value is *false*

```php
php artisan administrable:make:crud {Model} --debug_packages
```

By default the **guard** used is **admin** and can be changed by passing in argument of the command the name of the **guard** to use.

```php
php artisan administrable:install client
```

### The options

- **locale**

The locale can be changed with the option *--locale*

```php
php artisan administrable:install {guard=admin} --locale="fr"
```

or with the short version

```bash
php artisan administrable:install {guard=admin} -l "fr"
```

**NB**: The local supported is French

- **generate**

By default the crud of articles (**Post**), messaging (**Mailbox**) and testimonials (**Testimonial**) are generated. This behavior can be modified with the *--generate* option.

**NB**: the models must be separated by a comma and the authorized values are: **Post**, **Mailbox** and **Testimonial**.

```php
php artisan administrable:install {guard=admin} --generate="Post,Mailbox,Testimonial"
```

or with the short version

```php
php artisan administrable:install {guard=admin} -g "Post,Mailbox,Testimonial"
```

The default is: *Post,Mailbox,Testimonial*

- **preset**

When generating the framework used for the front end is **view**. This behavior can be modified with the option ***--preset***.
The authorized values are: **view**, **react** and **bootstrap** in connection with the ***laravel/ui*** package.

```php
php artisan administrable:install {guard=admin} --preset="vue"
```

or with the short version

```php
php artisan administrable:install {guard=admin} -p "vue"
```

- **models**

By default, models are stored in the **App/Models** folder. This folder can be modified with the option ***--models***.
With the value of the name of the folder which must necessarily be located in the ***app*** folder at the root of the project.

**NB**: This folder is automatically created if it does not exist.

```php
php artisan administrable:install {guard=admin} --models="Models"
```

or with the short version

```php
php artisan administrable:install {guard=admin} -m "Models"
```

**seed**
To automatically seed the database, you must first configure the database access in the ***.env*** file.

```php
php artisan administrable:install {guard=admin} --seed
```

or with the short version

```php
php artisan administrable:install {guard=admin} -s
```

- **theme**

To change the administration theme (template). The available themes are: **adminlte**, **tabler**, **theadmin** and **themekit**

**NB:** The default theme is ***adminlte***.

**adminlte**
![adminlte](docs/img/adminlte.png?raw=true)


**tabler**
![tabler](docs/img/tabler.png?raw=true)

**theadmin**
![theadmin](docs/img/theadmin.png?raw=true)

**themekit**
![themekit](docs/img/themekit.png?raw=true)

```php
php artisan administrable:install {guard=admin} --theme="adminlte"
```

ou avec la version courte

```php
php artisan administrable:install {guard=admin} -t "adminlte"
```

You can now log in to the back office  ***domain/administrable***

Example: *http::localhost:8000/administrable*

The url can be changed in the administrable config file located in config folder.
You need to publish the service provider first (explain in step 2) and create guard (explain in step 5).

```php
/**
 * Administration routes prefix.
 */
'auth_prefix_path' => 'administrable',
```

### 3. Publication of config and assets (css and js)

Necessary for the theme.

```php
php artisan vendor:publish --provider="Guysolamour\Administrable\ServiceProvider"
```

### 4. Empty the cache

```php
php artisan route:clear && php artisan config:clear
```

### 5. Create the symbolic link for the media

```php
php artisan storage:link
```

### 6. Create guard

You need to create a guard entry in database before log in.

Example:

```php
php artisan administrable:create --username=johndoe --email=john@doe.fr --password=12345678
```

or with the short version

```php
php artisan administrable:create -u johndoe -e john@doe.fr -p 12345678
```

**NB:**

- You will be prompt if a option is not passed.
- available options are: *username*, *email* and *password*

### 7. Seed  the database

```php
php artisan db:seed --class ConfigurationsTableSeeder
```

If the **Post** crud was generated

```php
php artisan db:seed --class PostsTableSeeder
```

If the **Testimonial** crud was generated

```php
php artisan db:seed --class TestimonialsTableSeeder
```

If the **Mailbox** crud was generated

```php
php artisan db:seed --class MailboxesTableSeeder

```

The guard

```php
php artisan db:seed --class {guard}sTableSeeder
```

If the guard is admin:

```php
php artisan db:seed --class AdminsTableSeeder
```
