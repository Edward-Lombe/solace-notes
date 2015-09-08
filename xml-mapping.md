# Mapping Notes / Schema
Mapping from XML to Caché Multidimensional

## XML - Caché Multidimensional

`XML`
```json
{
  "literalKey" : "value",
  "objectKey" : {
    "subKeyOne" : "with value",
    "subKeyTwo" : "with another value"
  },
  "arrayKey" : [
    "item one",
    "item two"
  ]
}
```

`Caché Multidimensional`
```
XML("literalKey")="value"
XML("objectKey", "subKeyOne")="with value"
XML("objectKey", "subKeyTwo")="with another value"
XML("arrayKey", "0")="item one"
XML("arrayKey", "1")="item two"
```

## Caché Multidimensional - XML
