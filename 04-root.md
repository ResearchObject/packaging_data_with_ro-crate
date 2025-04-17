---
title: Declaring the root folder
teaching: 2
exercises: 1
---

:::::::::::::::::::::::::::::::::::::::: questions
- What is the root folder?
::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: objectives
- Create a top-level entity that can list the parts of the crate
::::::::::::::::::::::::::::::::::::::::::::::::::

## RO-Crate Root

Next we'll add another entity to the `@graph` array,
to describe the [RO-Crate Root](https://www.researchobject.org/ro-crate/1.1/root-data-entity.html#direct-properties-of-the-root-data-entity):

```json
{
    "@id": "./",
    "@type": "Dataset",
    "hasPart": [ 

    ]
}
```

:::::::::::::::::::::::::::::::::::::::: callout
## Adding entities to the JSON array

Because we're adding incrementally to the `@graph` array.
It is important to remember the comma `,` between each entity,
**except** for the final entity in the JSON array;
and likewise for the properties within the JSON object for each entity.
This is an artefact of the strict [JSON](https://www.json.org/) file format rules to simplify parsing.
The order of the entities within the `@graph` JSON-LD array
and the order of the keys within a JSON object is _not significant_.
The _graph_ content is given by the `@id` cross-references.

You will add a comma here between the `ro-crate-metadata.json` entity, and the root data entity.
::::::::::::::::::::::::::::::::::::::::::::::::::

By convention, in RO-Crate the `@id` value of  `./` means that this entity describes the folder in which the RO-Crate metadata file is located.
This reference from `ro-crate-metadata.json` is therefore semantically marking the `crate1` folder as being the RO-Crate Root.


:::::::::::::::::::::::::::::::::::::::: discussion
## RO-Crates can be published on the Web
 
This example is a folder-based RO-Crate stored on disk,
and therefore absolute paths are avoided,
e.g. in case the root folder is moved or archived as a ZIP file. 
 
If the crate is being served from a Web service,
such as a data repository or database where files are not organized in folders,
then the `@id` might be an absolute URI instead of `./`
-- this is one reason why we point to the root entity from the metadata descriptor,
see section [Root Data Entity](https://www.researchobject.org/ro-crate/1.1/root-data-entity.html) for details.
::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: keypoints
- The RO-Crate Root is the top-level object of the RO-Crate
- The root identifier may be a URL, but commonly just ./ for the current folder
::::::::::::::::::::::::::::::::::::::::::::::::::

