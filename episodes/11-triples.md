---
title: "Converting JSON-LD to triples"
teaching: 1
exercises: 2
---
:::::::::::::::::::::::::::::::::::::::: questions
- "How can I generate RDF triples from an RO-Crate?"
::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: objectives
- "Understand converting the JSON-LD to RDF triples"
- "Learn how to create unique identifiers for items within an RO-Crate"
::::::::::::::::::::::::::::::::::::::::::::::::::

## Advanced: Converting JSON-LD to triples

To convert the RO-Crate JSON-LD to triples,
e.g. to demonstrate how it might be described at a web resource,
a 'base' URI is needed that will point to that resource,
i.e. resolve as a page or file on the web.

Try to specify a hypothetical base URI by modifing the graph's `@context` within the [JSON-LD Playground](https://json-ld.org/playground/)
(do not modify the `ro-crate-metadata.json` on disk), and revisit the _Table_ rendering.

```json
{
  "@context": [
    "https://w3id.org/ro/crate/1.1/context",
    { "@base": "arcp://uuid,deffa754-c764-4e04-aabf-e600c6200553/" }
  ],
  "…": "…"
}
```

![Triples table in the JSON-LD Playground](fig/jsonld-playground-table.png){alt='' .image-with-shadow }

Above `arcp://uuid,deffa754-c764-4e04-aabf-e600c6200553/` is a randomly generated identifier to represent the RO-Crate root,
and now the JSON-LD Playground can show all the triples from the metadata file.
You can likewise use the _N-Quads_ button to convert the metadata file to the [RDF N-Quads](http://www.w3.org/TR/n-quads/) format.
Most RDF libraries and stores have JSON-LD support, but may need to specify a base URI as we did above,
making a new UUID for each imported RO-Crate.


:::::::::::::::::::::::::::::::::::::::: keypoints
- "The JSON-LD @context maps JSON keys to schema.org vocabulary"
- "A @base URI is needed to make absolute URIs"
- "arcp and UUID can be used for RO-Crates that are not exposed on the Web"
::::::::::::::::::::::::::::::::::::::::::::::::::


