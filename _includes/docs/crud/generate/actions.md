### The actions

Sometimes we do not want to generate all actions (http verbs).

NB: The authorized values are: ***index***, ***show***, ***create***, ***edit*** and ***delete***

Actions can be separated by a , (*comma*)

```yaml
Post:
  actions: index,show,create,edit,delete
```

Actions can be separated by the character pipe |

```yaml
Post:
  actions: index|show|create|edit|delete
```

Actions can be declared as a list

```yaml
Post:
  actions:
    - index
    - show
    - create
    - edit
    - delete
```