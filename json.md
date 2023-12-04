# Schema

## Ref

**test online**: https://www.jsonschemavalidator.net/
**doc**: https://opis.io/json-schema/2.x/object.html#dependentrequired

## DependentRequired

```json
{
  "type": "object",
  "dependentRequired": {
    "a": ["b", "c"]
  }
}
```
If the object has property `a`, then it must also have `b` and `c`.

