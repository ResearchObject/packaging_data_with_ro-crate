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

Next we'll add another entity to the `@graph` array, to describe the [RO-Crate Root](https://www.researchobject.org/ro-crate/1.1/root-data-entity.html#direct-properties-of-the-root-data-entity).

This Root Data Entity must include certain properties and follow their conventions:

| Property | Convention |
| --- | --- |
| `@id` | normally `./` |
| `@type` | must be `Dataset` |
| `datePublished` | in `YYYY-MM-DD` format (ISO 6801) |
| `name` | identifies the dataset clearly to humans (e.g. _Rainfall data for Katoomba, NSW Australia February 2022_) |
| `description` | summarises the dataset and its context |
| `license` | links to a contextual entity elsewhere in `ro-crate-metadata.json`. |
| `hasPart` | a list of entities within the dataset (we'll fill this in later) |

```json
{
    "@id": "./",
    "@type": "Dataset",
    "datePublished": "2024-04-05",
    "name": "Example dataset for RO-Crate tutorial",
    "description": "A collection of arbitrary data used for demonstrating how to build RO-Crates.",
    "license": "https://www.apache.org/licenses/LICENSE-2.0"
    "hasPart": [ 
    ]
}
```

By convention, in RO-Crate the `@id` value of  `./` means that this entity describes the folder in which the RO-Crate metadata file is located. This reference from `ro-crate-metadata.json` is therefore semantically marking the `crate1` folder as being the RO-Crate Root.

> ## RO-Crates can be published on the Web
>
> This example is a folder-based RO-Crate stored on disk, and therefore absolute paths are avoided, e.g. in case the root folder is moved or archived as a ZIP file.
>
> If the crate is being served from a Web service, such as a data repository or database where files are not organized in folders, then the `@id` might be an absolute URI instead of `./` -- this is one reason why we point to the root entity from the metadata descriptor, see section [Root Data Entity](https://www.researchobject.org/ro-crate/1.1/root-data-entity.html) in the RO-Crate specification for details.
{: .discussion}

{% include links.md %}
