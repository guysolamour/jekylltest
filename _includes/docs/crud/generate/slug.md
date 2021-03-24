### slug

To sluggify a field

```yaml
Post:
  name: {slug: true }
```

or pass the slug option at the model level with the name of the field to be sluggified which must be defined beforehand (***important***).

```yaml
Post:
  name: { name: name, type: string:125, rules: nullable}
  age: { type: int:3 }
  slug: name
```

**NB:**

- One of the two options can  be used.
- Only one field can be sluggable
- Only  (***text***, ***longText***, ***mediumText***) type fields can be sluggify