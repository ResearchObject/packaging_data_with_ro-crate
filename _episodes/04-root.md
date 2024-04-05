---
title: "Declaring the root folder"
teaching: 2
exercises: 1
questions:
- "What is the root folder?"
objectives:
- "Create a top-level entity that can list the parts of the crate"
keypoints:
- "The RO-Crate Root is the top-level object of the RO-Crate"
- "The root identifier may be a URL, but commonly just ./ for the current folder"
---

## RO-Crate Root

Next we'll add another entity to the `@graph` array, to describe the [RO-Crate Root](https://www.researchobject.org/ro-crate/1.1/root-data-entity.html#direct-properties-of-the-root-data-entity):

```json
{
    "@id": "./",
    "@type": "Dataset",
    "hasPart": [ 

    ]
}
```

By convention, in RO-Crate the `@id` value of  `./` means that this entity describes the folder in which the RO-Crate metadata file is located. This reference from `ro-crate-metadata.json` is therefore semantically marking the `crate1` folder as being the RO-Crate Root.

The `@type` of this entity must always be `Dataset`.

The `hasPart` array will contain cross-references to the other entities in the crate (we'll fill these in later).

> ## RO-Crates can be published on the Web
>
> This example is a folder-based RO-Crate stored on disk, and therefore absolute paths are avoided, e.g. in case the root folder is moved or archived as a ZIP file.
>
> If the crate is being served from a Web service, such as a data repository or database where files are not organized in folders, then the `@id` might be an absolute URI instead of `./` -- this is one reason why we point to the root entity from the metadata descriptor, see section [Root Data Entity](https://www.researchobject.org/ro-crate/1.1/root-data-entity.html) in the RO-Crate specification for details.
{: .discussion}

{% include links.md %}
