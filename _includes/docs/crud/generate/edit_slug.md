### edit slug

To have the slug field in form and edit it

```yaml
Post:
  name: {slug: true }
  edit_slug: true
```

Or use it globally. This will affect all models

```yaml
edit_slug: true
```

**NB:**

- The default value is *false*.
- A slug field is required on the model

### clone

To have a button in index vue to clone or duplicate a field

```yaml
Post:
  name: {slug: true }
  clone: true
```

Or use it globally. This will affect all models

```yaml
clone: true
```

**NB:**

- The default value is *true*.
