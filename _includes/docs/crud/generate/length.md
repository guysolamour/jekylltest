### Length

To define the length of a field

```yaml
Post:
  name: { length: 60 }
```

For the ***string*** (*text*, *mediumText*, *longText*) or ***int*** (*int*, *smallInt*, *BigInt*)  types,  you can pass the size of the field to the type separate by ***: ***.

```yaml
Post:
  name: {  type: string:60  }
```

```yaml
User:
  age: { type: int:3 }
```