### trans

The model can be translated with the *trans* option

```yaml
Post:
  name: { name: name, type: string:125, rules: nullable}
  age: { type: int:3 }
  trans: article
```

To field can be translated too.

```yaml
Post:
  name: { trans: nom }
```

**NB:** This translation is only used for display at view level.
If the option is not passed, the translation file in  **resources/lang**  in the current locale folder will be used.
