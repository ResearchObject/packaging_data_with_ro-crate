---
title: "Declaring the root folder"
teaching: 0
exercises: 0
questions:
- "Key question (FIXME)"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
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


> ## RO-Crates can be published on the Web
> 
> This example is a folder-based RO-Crate stored on disk, and therefore absolute paths are avoided, e.g. in case the root folder is moved or archived as a ZIP file. 
> 
> If the crate is being served from a Web service, such as a data repository or database where files are not organized in folders, then the `@id` might be an absolute URI instead of `./` -- this is one reason why we point to the root entity from the metadata descriptor, see section [Root Data Entity](https://www.researchobject.org/ro-crate/1.1/root-data-entity.html) for details.
{: .discussion}


{% include links.md %}

