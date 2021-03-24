### The polymorphic type

To create a polymorphic field

```yaml
Post:
  name: { type: string, rules: required, type: polymorphic }
```

or

```yaml
Post:
  name: { rules: required, polymorphic: true }
```

The name of the polymorphic relation is the name of the field with the suffix ***able*** by default. This behavior can be modified with:

```yaml
Post:
  image:
    type: image
    name: mediaable
    rules: required
```

Polymorphic field names can be changed with

```yaml
Post:
  image:
    type: image
    model_id: imageable_id
    model_type: imageable_type
    rules: required
```

The *model_id* must have the suffix ***_ id*** and the *model_type* must have the suffix ***_ type***

**NB:** To generate the model and the migration, you will have to use the *entity* tag on model's definition.

```yaml
Post:
  name: { rules: required }
  entity: true
```

