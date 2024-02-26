---
title: "Converting JSON-LD to triples"
teaching: 1
exercises: 2
questions:
- "How can I generate RDF triples from an RO-Crate?"
objectives:
- "Understand converting the JSON-LD to RDF triples"
- "Learn how to create unique identifiers for items within an RO-Crate"
keypoints:
- "The JSON-LD @context maps JSON keys to schema.org vocabulary"
- "A @base URI is needed to make absolute URIs"
- "arcp and UUID can be used for RO-Crates that are not exposed on the Web"
---

## Advanced: Converting JSON-LD to triples

Try modify the graph's `@context` within the [JSON-LD Playground](https://json-ld.org/playground/) (don't modify the `ro-crate-metadata.json` on disk), and revisit the _Table_ rendering.

```json
{
  "@context": [
    "https://w3id.org/ro/crate/1.1/context",
    { "@base": "arcp://uuid,deffa754-c764-4e04-aabf-e600c6200553/" }
  ],
  "…": "…"
}
```

![Triples table in the JSON-LD Playground](../fig/jsonld-playground-table.png){: .image-with-shadow }

Above `arcp://uuid,deffa754-c764-4e04-aabf-e600c6200553/` is a randomly generated identifier to represent the RO-Crate root, and now the JSON-LD Playground can show all the triples from the metadata file. You can likewise use the _N-Quads_ button to convert the metadata file to the [RDF N-Quads](http://www.w3.org/TR/n-quads/) format. Most RDF libraries and stores have JSON-LD support, but may need to specify a base URI as we did above, making a new UUID for each imported RO-Crate.



{% include links.md %}

