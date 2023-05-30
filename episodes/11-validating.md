---
title: "Validating JSON-LD"
teaching: 2
exercises: 4
questions:
- "Key question (FIXME)"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---


## Validating JSON-LD

As we made this RO-Crate Metadata File by hand, it's good to check for any JSON errors, such as missing/extra `,` or unclosed `"` quotes. Try pasting the file content into the [JSON-LD Playground](https://json-ld.org/playground/). It should show up any errors, for example:

~~~
JSON markup - SyntaxError: JSON.parse: expected `','` or `']'` after array element 
at line 29 column 5 of the JSON data
~~~
{: .error}

Modify the JSON file in your editor to fix any such errors. You can also use editor commands such as _Format Document_ to ensure you have consistent spacing, indentation and brackets.

If the document passes without errors in the JSON-LD Playground, you should see output under _Expanded_ looking something like:

```json
[
  {
    "@id": "ro-crate-metadata.json",
    "@type": [
      "http://schema.org/CreativeWork"
    ],
    "http://schema.org/about": [
      {
        "@id": "./"
      }
    ],
    "http://purl.org/dc/terms/conformsTo": [
      {
        "@id": "https://w3id.org/ro/crate/1.1"
      }
    ]
  },
  {
    "@id": "./",
    "@type": [
      "http://schema.org/Dataset"
    ],
    "…": "…"
  }
]
```
{: .output .language-json}

This verbose listing of the JSON-LD shows how the `@context` has correctly expanded the keys, but is not particularly readable. Try the _Visualized_ tab to see an interactive rendering of the entities:

![Visualized in the JSON-LD Playground](../fig/jsonld-playground-visualized.png)

As the RO-Crate Metadata Document is valid JSON-LD it is also possible to process it using Linked Data technologies such as triple stores and SPARQL queries. It is beyond the scope of this tutorial to explain this aspect fully, but interested readers should consider how to [handle relative URI references](https://www.researchobject.org/ro-crate/1.1/appendix/relative-uris.html).
As an example, try the _Table_ button and notice that the entities with relative identifiers are not included. This is because when converting to RDF you need absolute URIs which do not readily exist when a crate is stored on disk, we've not decided where the crate is to be published yet.  


{% include links.md %}

