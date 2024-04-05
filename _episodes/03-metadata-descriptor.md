---
title: "Making a metadata descriptor"
teaching: 2
exercises: 2
questions:
- "Which RO-Crate version is used?"
- "How can the crate self-identify as an RO-Crate?"
objectives:
- "Add the first entity to the JSON-LD @graph"
- "Indicate the version of RO-Crate"
keypoints:
- "The RO-Crate Metadata Descriptor describes the JSON-LD file itself"
- "RO-Crate specifications are versioned"
- "The version of RO-Crate is indicated using the conformsTo property" 
---

## Entities

Our metadata will be made up of _entities_: items which we'll cross-reference with IDs. These items might be files within the directory (_data entities_), or references to things that exist outside of the directory (_contextual entities_).

The RO-Crate Metadata Document contains a flat list of _entities_ as JSON objects in the `@graph` array. These entities are cross-referenced using `@id` identifiers, rather than being deeply nested. This is one major difference from JSON structures you may have experienced before.

The rest of this tutorial, and indeed most of the [RO-Crate specification](https://www.researchobject.org/ro-crate/1.1/), specify which entities can be added to the `@graph` array.

## RO-Crate Metadata descriptor

The first entity to add has the `@id` value of `ro-crate-metadata.json` to describe the JSON file itself.

```json
{
    "@id": "ro-crate-metadata.json",
    "@type": "CreativeWork",
    "conformsTo": {"@id": "https://w3id.org/ro/crate/1.1"},
    "about": {"@id": "./"}
}
```

This entity, known as the [RO-Crate Metadata Descriptor](https://www.researchobject.org/ro-crate/1.1/root-data-entity.html#ro-crate-metadata-file-descriptor), helps this file self-identify as an RO-Crate Metadata Document, which is conforming to (`conformsTo`) the RO-Crate specification version 1.1. This entity must be included in any RO-Crate.

The `@type` keyword associates an object with a predefined type from the [JSON-LD context](https://www.researchobject.org/ro-crate/1.1/appendix/jsonld.html#ro-crate-json-ld-context). Almost any property can alternatively be used with an `[]` array to provide multiple values.

> ## Why is `conformsTo` the same as `@context`?
>
> Notice that the `conformsTo` URL corresponds to the `@context` URL version-wise, but they have two different functions. The `@context` brings the defined terms into the metadata document, while the `conformsTo` declares which RO-Crate conventions of using those terms are being followed.
{: .callout}

> ## Why do some keywords start with `@` but not others?
>
> TODO
{: .callout}

{% include links.md %}
