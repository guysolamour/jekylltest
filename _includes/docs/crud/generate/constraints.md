### Constraints

```yaml
Post:
  name: { constraints: nullable}
```

Constraints can be separated by  a comma *,*

```yaml
Post:
  name: { constraints: nullable,unique,index}
```

or with the list syntax

```yaml
Post:
  name:
    constraints:
       - nullable
       - unique
       - index
```

**NB**:

- The constraints must be valid according to the database management system.
- For the constraint ***set null***, no need to pass the field to ***nullable***. It’s done automatically.
- On the other hand, do not forget to remove the validation rule ***required*** if it is present because a field cannot be both ***required*** and ***nullable***.
- If the field is ***nullable*** no need to put it in the list of constraints and vice versa.
- For the ***default*** constraint  the value can be passed with **:**

```yaml
Post:
  age: { constraints: default:18 }
```
