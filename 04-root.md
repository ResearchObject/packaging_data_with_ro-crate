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

First we'll add an entity to the `@graph` array,
to describe the [RO-Crate Root](https://www.researchobject.org/ro-crate/specification/1.2/root-data-entity.html#direct-properties-of-the-root-data-entity):

```json
{
    "@id": "./",
    "@type": "Dataset",
    "hasPart": [ 

    ]
}
```

By convention, in RO-Crate the `@id` value of  `./` means that this entity describes the folder in which the RO-Crate metadata file is located. The root data entity always has the `@type` value of `Dataset`, which is a [schema.org](https://schema.org/Dataset) type.
This will be referenced from `ro-crate-metadata.json`, semantically marking the `crate1` folder as being the RO-Crate Root.


:::::::::::::::::::::::::::::::::::::::: discussion
## RO-Crates can be published on the Web
 
This example is a folder-based RO-Crate stored on disk,
and therefore absolute paths are avoided,
e.g. in case the root folder is moved or archived as a ZIP file. 
 
If the crate is being served from a Web service,
such as a data repository or database where files are not organized in folders,
then the `@id` might be an absolute URI instead of `./`
-- this is one reason why we point to the root entity from the metadata descriptor,
as you will see in the next section.
::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: challenge
## Add an additional type

1. Navigate the schema.org type list to find a subtype of `CreativeWork` that is suitable for a learning resource.
2. Modify the root entity's `@type` to be an array.
3. Add the type name for learning resource at the end of the array.

:::::::::::::::  solution
```json
{
   "@id": "./",
   "@type": ["Dataset", "LearningResource"],
   "hasPart": [ 
     {"@id": "data.csv"} 
   ],
   "…": "…"
}
```
:::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::::

The root has several metadata properties that describe the RO-Crate as a whole,
considering it as a Research Object of collected resources.
In the next section we will cover the required and recommended properties of the root `./`.

:::::::::::::::::::::::::::::::::::::::: keypoints
- The RO-Crate Root is the top-level object of the RO-Crate
- The root identifier is commonly just ./ for the current folder, but can be a URL
- The root is always typed as a Dataset, but can have additional types
::::::::::::::::::::::::::::::::::::::::::::::::::