### The validation

The validation rules are passed by the key ***rules*** and by default is an empty string.

```yaml
Post:
  name: { rules: required }
```

It uses the default validation rules of [laravel] (https://laravel.com/docs/validation).

Several rules must be separated by the pipe character **|**

```yaml
Post:
  name: { rules: required|string|min:2 }
```

For the rule ***required*** we can use the diminutive ***req*** (just an alias)

```yaml
Post:
  name: { rules: req|string|min:2 }
```

