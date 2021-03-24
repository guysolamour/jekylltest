### Relationships

For relations the type ***relation*** is used

```yaml
Post:
  user_id: { type: relation, related: user }
```

The related is optional, we guest the name by remove the *_id*  on the field's name.
If the field doest not respect this convention, you have to use this option.

```yaml
Post:
  user_id: { type: relation }
```

Dans ce cas, le related sera **user**.

It is possible to use the full qualify class name.

```yaml
Post:
  user_id: { type: relation, related: App\Models\User }
```

You can change the deletion policy. OnDelete tag

```yaml
Post:
  user_id: { type: { relation: one to one, type: simple, related: user, property: name, onDelete: cascade }, rules: required }
```

You can change the key used for the foreign key.

```yaml
Post:
  user_id: { type: { relation: one to one, type: simple, related: user, property: name, references: id }, rules: required }
```

By default it is id which is used
**NB:**

- The authorized values are: ***cascade*** and ***set null***.
- No onDelete on a polymorphic type field.
- if a field must be polymorphic it will be necessary to create the linked model first before making the connection
- for relationship type fields if the related is not passed it is the name of the field which is used


### Type simple

#### One to One (simple)

```yaml
Post:
  user_id: { type: { relation: one to one, type: simple, related: user, property: name }, rules: required }
```

**NB:**

- The related is obligatory we must know to which field the relation is linked
- The related is mandatory and is the linked model. We can just pass the name
or the namespace.
- The property is the field used only for display and must exist on the linked model.

### Foreign keys

- For the model we are going to create

```yaml
Post:
  user_id:
    type:
      relation: many to many
      type: simple
      related: user
      property: name
      intermediate_table: post_user
      local_keys: { foreign_key: kguy_id, local_key: kid }
    rules: required
```

- For the model to be linked

```yaml
Post:
  user_id:
    type:
      relation: many to many
      type: simple
      related: user
      property: name
      intermediate_table: post_user
      related_keys:  { foreign_key: guy_id, other_key: id }
    rules: required
```

#### One to Many (simple)

```yaml
Post:
  user_id: { type: { relation: one to many, type: simple, related: user, property: name }, rules: required }
```

**NB:**

- The related is obligatory (we must know to which field the relation is linked)
- The related is mandatory and is the linked model. We can just pass the name
or the full namespace.
- The property is the field used only for display and must exist on the linked model.

#### Foreign keys

- For the model we are going to create

```yaml
Post:
  user_id:
    type:
      relation: many to many
      type: simple
      related: user
      property: name
      intermediate_table: post_user
      local_keys: { foreign_key: kguy_id, local_key: kid }
    rules: required
```

- For the model that will be linked

```yaml
Post:
  user_id:
    type:
      relation: many to many
      type: simple
      related: user
      property: name
      intermediate_table: post_user
      related_keys:  { foreign_key: guy_id, other_key: id }
    rules: required
```

**Many to Many (simple)**

```yaml
Post:
  user_id: { type: { relation: many to many, type: simple, related: user, property: name }, rules: required }
```

**NB:**

- The pivot table is automatically generated.
- You can change the name of the pivot intermediate table.

```yaml
Post:
  user_id:
    type:
      relation: many to many
      type: simple
      related: user
      property: name
      intermediate_table: post_user
    rules: required
```

#### Foreign keys

- For the model we are going to create

```yaml
Post:
  user_id:
    type:
      relation: many to many
      type: simple
      related: user
      property: name
      intermediate_table: post_user
      local_keys: { foreign_key: terrain_id, join_key: user_id }
    rules: required
```

- For the model that will be linked

```yaml
Post:
  user_id:
    type:
      relation: many to many
      type: simple
      related: user
      property: name
      intermediate_table: post_user
      related_keys: { foreign_key: user_id, join_key: terrain_id }
    rules: required
```

If the keys are passed and the intermediate table (pivot) is not then this table will be created with the convention.

### One to One (polymorphic)

```yaml
Post:
  user_id:
    type:
      relation: one to one
      type: polymorphic
      related: user
      property: name
    rules: required
```

### One to Many (polymorphic)

```yaml
Post:
  user_id:
    type:
      relation: one to many
      type: polymorphic
      related: user
      property: name
    rules: required
```

### Many to Many polymorphic

The ***many to many*** polymorphic relationship is not yet established. I haven't had to use it in my various projects yet.


