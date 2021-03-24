### Name

Only the name is required to declare a field (in some case).

```yaml
Post:
  name: {  }
```

```yaml
Post:
  name: { name: name }
```

However it can be optional if other keys are passed.

```yaml
Post:
  name: { type: string, rules: required }
```