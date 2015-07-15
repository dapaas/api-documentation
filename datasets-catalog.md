# Group Datasets Catalog

## List All Datasets [/catalog/datasets/catalog]

+ Parameters
    + showShared: (optional, y|n) - defaults to 'n'
    + Accept: (required, mimetype) - 
      ```application/ld+json``` or ```application/rdf+xml```

### List users's datasets [GET]

+ Request
    + Headers
        Accept: application/ld+json
        Authorization: Basic YXBpa2V5OmFwaXBhc3M=
        showShared: (y|n), defaults to 'n'

# Response 200

    {
        "@context": { ... }
        "@type": "dcat:Catalog",
        "dct:publisher": "Alex",
        "@id": "http://dapaas.eu/users/Alex/datasets",
        "dcat:record": [
            {
                "@type": "dcat:CatalogRecord",
                "foaf:primaryTopic": "http://eu.dapaas/dataset/1",
                "dct:issued": "2014-09-16",
                "dct:modified": "2014-09-17",
                "dct:title": "My first DaPaaS dataset"
            },
            {
                "@type": "dcat:CatalogRecord",
                "foaf:primaryTopic": "http://eu.dapaas/dataset/2",
                "dct:issued": "2014-09-15",
                "dct:modified": "2014-09-17",
                "dct:title": "My second DaPaaS dataset"
            }
        ]
    }

## Search Datasets [/catalog/datasets/search?q]

+ Parameters
    + q: (required, text) - The query  
    + showShared: (optional, y|n) - defaults to 'n'
    + Accept: (required, mimetype) - 
      ```application/ld+json``` or ```application/rdf+xml```

### On metadata [GET]
+ Request
    + Headers
        Accept: application/ld+json
        Authorization: Basic YXBpa2V5OmFwaXBhc3M=
        showShared: (y|n), defaults to 'n'

# Response 200

    {
        "@context": { ... }
        "@type": "dcat:Catalog",
        "dct:publisher": "Alex",
        "@id": "http://dapaas.eu/users/Alex/datasets",
        "dcat:record": [
            {
                "@type": "dcat:CatalogRecord",
                "foaf:primaryTopic": "http://eu.dapaas/dataset/1",
                "dct:issued": "2014-09-16",
                "dct:modified": "2014-09-17",
                "dct:title": "My first DaPaaS dataset"
            },
            {
                "@type": "dcat:CatalogRecord",
                "foaf:primaryTopic": "http://eu.dapaas/dataset/2",
                "dct:issued": "2014-09-15",
                "dct:modified": "2014-09-17",
                "dct:title": "My second DaPaaS dataset"
            }
        ]
    }

## Get a Dataset [/catalog/datasets]

+ Parameters
    + `dataset-id`: (required, URI)
        - URI of the dataset, taken from the catalog
    + Accept: (required, mimetype) - 
      ```application/ld+json``` or ```application/rdf+xml```

### Lapin [GET]

