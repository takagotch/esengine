### esengine
---
https://github.com/seek-ai/esengine

```py
// tests/test_embedded_document.py

class TowFields(EmbeddedDocument):
  x = IntegerField()
  y = IntegerField()
  
def test_pass_none_to_to_dict():
  field = TowFields()
  assert field.to_dict(None) is None
  
def test_to_dict():

```

```
```

```
```
