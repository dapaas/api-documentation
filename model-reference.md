# Group Model reference

![Model](model.png)

The Datagraft API supports [RDF/XML](https://en.wikipedia.org/wiki/RDF/XML) and [JSON-LD](https://en.wikipedia.org/wiki/JSON-LD).



#### Namespaces

* dcat - http://www.w3.org/ns/dcat#
* dct - http://purl.org/dc/terms/
* rdf - http://www.w3.org/1999/02/22-rdf-syntax-ns
* foaf - http://xmlns.com/foaf/0.1/

#### Dataset

| Property  | Range  | Description  |
|-------------|----------|----------------|
| rdf:type  | `"dcat:Dataset"`  | |
| dct:title | Text | |
| dct:description | Text  | |
| dct:issued | Date | |
| dct:modified | Date | |
| dcat:keyword | Text []| List of keywords |
| dct:publisher | Text | |
| dcat:distribution | URI [] | List of the connected distributions|
| dcat:public | `"true"` or `"false"`  | |

#### Distribution

| Property | Range  | Description  |
|-------------|----------|----------------|
| rdf:type | `"dcat:Distribution"`  | |
| dct:title | Text | |
| dct:description | Text  | |
| dct:issued | Date | |
| dct:modified | Date | |
| dcat:mediaType | Mimetype (Text)  | |
| dcat:accessURL | URI | The SPARQL endpoint URL for RDF distributions  |
| dcat:fileID  | Text  | UUID for the raw file generated by the system.  |
| dcat:fileName | Text  | Original file name  |

#### Transformation

| Property  | Range  | Description  |
|-------------|----------|----------------|
| rdf:type  | `"dcat:Transformation"`  | |
| dct:title  | Text | |
| dct:description  | Text  | |
| dct:issued  | Date | |
| dct:modified  | Date | |
| dcat:keyword  | Text [] | List of keywords |
| dct:publisher  | Text | |
| dcat:clojureDataID | Text | |
| dcat:jsonDataID | Text | |
| dcat:sourceData  | URI  | Reference to the input data Distribution object  |
| dcat:public | `"true"` or `"false"`  | |
| dcat:transformationType | `"pipe"` or `"graft"` | |
| dcat:transformationCommand | Text  | entry point (command/function) of the transformation. `"my-pipe"` for pipe and `"my-graft`" for graft are recommended.| 

### JSON-LD

JSON-LD, or JavaScript Object Notation for Linked Data is the recommended way to consume and provide data. You can use the same software as traditional JSON. The `@context`, `@type` and `@id` properties are JSON-LD specific.

**Example:**

```json
{
  "@context": {
    "dcat": "http://www.w3.org/ns/dcat#",
    "foaf": "http://xmlns.com/foaf/0.1/",
    "dct": "http://purl.org/dc/terms/",
    "xsd": "http://www.w3.org/2001/XMLSchema#"
  },
  "@type": "dcat:Catalog",
  "@id": "http://dapaas.eu/users/dapaas/catalog",
  "dct:publisher": "dapaas",
  "dcat:record": [
    {
      "@type": "dcat:CatalogRecord",
      "foaf:primaryTopic": "http://dapaas.eu/users/15052/dataset/example-1",
      "dct:issued": "2014-09-18",
      "dct:modified": "2014-09-17",
      "dct:publisher": "dapaas",
      "dct:title": "Title for DS4 DaPaaS dataset UPDATED",
      "dcat:public": "true"
    },
    ... 
  ]
}
```