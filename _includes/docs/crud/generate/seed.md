### seeder

To avoid generating a seeder file

```yaml
Post:
  age: { constraints: default:18}
  seeder: false
```

**breadcrumb**
For breadcrumb, the procedure is as follows:

```yaml
Post:
  age: { breadcrumb: true}
```

or pass the breadcrumb option at the model level with the name of the field to use

```yaml
Post:
  age: { name: age}
  breadcrumb: age
```

**NB**

- One of the two possibilities cannot be used.
- only one field can have this breadcrumb attribute
- The breadcrumb is only used in administration panel.
