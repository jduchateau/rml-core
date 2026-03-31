## RMLTC0006b-JSON

**Title**: "Omit logical source with rml:constant in rml:subjectMap, rml:predicateMap, rml:objectMap and rml:graphMap"

**Description**: "Tests the omission of the rml:logicalSource when using only rml:constant in rml:subjectMap, rml:predicateMap, rml:objectMap and rml:graphMap"

**Default Base IRI**: http://example.com/

**Error expected?** No

**Mapping**
```
@prefix ex: <http://example.com/> .
@prefix rml: <http://w3id.org/rml/> .

<http://example.com/base/TriplesMap1> a rml:TriplesMap;
  rml:predicateObjectMap [
      rml:objectMap [
          rml:constant "Bad Student"
        ];
      rml:predicateMap [
          rml:constant ex:description
        ]
    ];
  rml:subjectMap [
      rml:constant ex:BadStudent;
      rml:graphMap [
          rml:constant <http://example.com/graph/student>
        ]
    ] .

```

**Output**
```
<http://example.com/BadStudent> <http://example.com/description> "Bad Student" <http://example.com/graph/student> .
```

