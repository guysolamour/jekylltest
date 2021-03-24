### fillable

To use fillable or guarded property in the model

```yaml
Post:
  name: {slug: true }
  fillable: true
```

Or use it globally. This will affect all models

```yaml
fillable: true
```

**NB:**

- The default value is *true*.