### Nullable

To make a field nullable

```yaml
Post:
  name: {  nullable: true }
```

or use the nullable validation rule

```yaml
Post:
  name: { rules: nullable }
```

- If a field has the nullable validation rule, the field is automatically nullable.
- If a field is nullable then it automatically has the nullable validation rule.
- No need to specify it in twice.
