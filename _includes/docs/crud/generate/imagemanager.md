### imagemanger

To use the image manager for a specific model.

**NB**:

- A model can only use 03 collections (*front*, *back* and *images*)

To use all collections and default labels

```yaml
Post:
  imagemanager: true
```

You can choose the collection (s) to use

```yaml
Post:
    imagemanager:
      - front
      - back
      - images
```

Labels can be changed this way

With the comma syntax

```yaml
Post:
  imagemanager: { front: front image label, back: back image label, images: images label }
```

or with the other syntax

```yaml
Post:
    imagemanager:
      front: front image label
      back: back image label
      images: images label
```
