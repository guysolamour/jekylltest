### Types

```yaml
Post:
  name: {  type: string }
```

The default type is: ***string***
The available types are: *string, text, mediumText, longText, date, datetime, boolean, enum, decimal, float, double, integer, mediumInteger, bigInteger, polymorphic, ipAdress, image, relation, file*

For file type fields you can use the *file* or *image* type (just an alias)

```yaml
Post:
  name: {  type: file }
```

or

```yaml
Post:
  name: {  type: image }
```
