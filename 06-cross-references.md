---
title: Adding cross-references
teaching: 3
exercises: 4
---
:::::::::::::::::::::::::::::::::::::::: questions
- How can I describe an entity further?
- How can I cross-reference different entities?
::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: objectives
- Understand cross-references in RO-Crate
- Add a data entity reference from the root entity
::::::::::::::::::::::::::::::::::::::::::::::::::


## About cross-references

In many JSON documents, related information is nested inside parent objects. For example:
```json
{
  "@id": "./",
  "@type": "Dataset",
  "name": "My Dataset",
  "author": {
    "@type": "Person",
    "name": "Josiah Carberry",
    "affiliation": "Brown University"
  }
}
```

While this is readable, it can become hard to manage when entities are reused or grow in complexity.

In contrast, RO-Crate uses a flattened structure, where each entity is described just once, and connected using @id cross-references:

```json
[
  {
    "@id": "./",
    "@type": "Dataset",
    "name": "My Dataset",
    "author": { "@id": "https://orcid.org/0000-0002-1825-0097" }
  },
  {
    "@id": "https://orcid.org/0000-0002-1825-0097",
    "@type": "Person",
    "name": "Josiah Carberry",
    "affiliation": "Brown University"
  }
]
```

In a RO-Crate Metadata Document,
entities are cross-referenced using `@id` reference objects,
rather than using deeply nested JSON objects.
In short, this _flattened JSON-LD_ style allows any entity to reference any other entity,
and RO-Crate consumers can directly find all the descriptions of a given entity as a single JSON object.

Think of @id as the entity’s “name tag”, you describe it once and refer to it anywhere in the graph.

![JSON block with id `ro-crate-metadata.json` has some attributes, `conformsTo` RO-Crate 1.2, and `about` referencing id `./`. In second JSON block with id <code>./</code> we see additional attributes such as its name and description.](fig/introduction-figure-1.svg){alt="showing RO-Crate Metadata descriptor's `about` property pointing at the RO-Crate Root entity with matching `@id`"}


:::::::::::::::::::::::::::::::::::::::: challenge
## Add cross-reference to data entity

Consider the root Data Entity `./`,
and add such a cross-reference to the file `data.csv` using the _property_ called `hasPart`:

:::::::::::::::  solution
```json
{
   "@id": "./",
   "@type": "Dataset",
   "hasPart": [ 
       {"@id": "data.csv"} 
   ],
   "…": "…"
}
```
:::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::::


:::::::::::::::::::::::::::::::::::::::: keypoints
- The @id uniquely identifies the entity within the RO-Crate
- Flattened JSON-LD helps keep each entity self-contained
- Reuse of @id avoids duplication and enables linking
::::::::::::::::::::::::::::::::::::::::::::::::::