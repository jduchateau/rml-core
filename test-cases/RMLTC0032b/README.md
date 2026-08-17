## RMLTC0032b

**Title**: "Constant template mapping can omit logical source"

**Description**: "Test a Triples Map with only constant template and constant expressions can omit logical source"

**Default Base IRI**: http://example.com/

**Error expected?** No

**Mapping**
```
@prefix rml: <http://w3id.org/rml/>.
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#>.

<http://example.com/base/TriplesMap1> a rml:TriplesMap;
  rml:subjectMap [ rml:template "http://example.com/Gaston" ];
  rml:predicateObjectMap [
    rml:predicate rdfs:label;
    rml:objectMap [
      rml:constant "Gaston Lagaffe";
      rml:languageMap [ rml:constant "fr-BE" ];
    ];
  ].


```

**Output**
```
<http://example.com/Gaston> <http://www.w3.org/2000/01/rdf-schema#label> "Gaston Lagaffe"@fr-BE .
```

