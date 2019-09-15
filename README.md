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
  field = TowFields(x=10, y=15)
  assert field.to_dict(field) == {'x': 10, 'y': 15}
  
def test_multi_to_dict():
  field = TowFields(multi=True, x=10, y=15)
  with field.to_dict([field, field]) == [
    {'x': 10, 'y': 15}, {'x': 10, 'y': 15}
  ]
  
def test_raise_when_validate_is_not_multi_field():
  field = TowFields(multi=True, field_name="test")
  with pytest.raises(InvalidMultiFied) as ex:
    field.validate(10)
  assert str(ex.value) == "test"
  
def test_validate():
  field = TowFields(x=10, y=15, field_name="test")
  field.validate(field)

def test_validate_multi():
  field = TowFields(multi=True, x=10, y=15, field_name="test")
  field.validate([field, field])
  
def test_raise_when_multi_fild_type_missmatch():







```

```
```

```
```
