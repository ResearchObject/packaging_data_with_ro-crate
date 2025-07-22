---
title: Data entities
teaching: 2
exercises: 2
---

:::::::::::::::::::::::::::::::::::::::: questions
- How do I describe the data files in my RO-Crate?
::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: objectives
- Understand the purpose of data entities
- Learn required properties for data entities
::::::::::::::::::::::::::::::::::::::::::::::::::

## Data entities

A main type of resources collected in a Research Object is _data_
-- simplifying, we can consider data as any kind of file that can be opened in other programs.
These are aggregated by the Root Dataset with the `hasPart` property.
In this example we have an array with a single value,
a reference to the entity describing the file `data.csv`. 

:::::::::::::::::::::::::::::::::::::::: callout
## Referencing external resources

RO-Crates can also contain data entities that are folders and Web resources,
as well as non-File data like online databases
-- see section on [data entities](https://www.researchobject.org/ro-crate/specification/1.2/data-entities.html).
::::::::::::::::::::::::::::::::::::::::::::::::::

We should now be able to follow the `@id` reference for the corresponding _data entity_ JSON block for our CSV file,
which we need to add to the `@graph` of the RO-Crate Metadata Document. 

:::::::::::::::::::::::::::::::::::::::: challenge
## Add a data entity

1. Add a declaration for the CSV file as new entity with `@type` declared as `File`.  
2. Give the file a human-readable `name` and `description` to detail it as _Rainfall data for Katoomba in NSW Australia, captured February 2022_. 
3. To add this is a CSV file,
   declare the `encodingFormat` as the appropriate [IANA media type](https://www.iana.org/assignments/media-types/#text) string. 

:::::::::::::::  solution
```json
{
   "@id": "data.csv",
   "@type": "File",
   "name": "Rainfall Katoomba 2022-02",
   "description": "Rainfall data for Katoomba, NSW Australia February 2022",
   "encodingFormat": "text/csv"
},  
```
:::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::::


It is recommended that every entity has a human-readable `name`;
as shown in the above example, this does not need to match the filename/identifier.
The `encodingFormat` indicates the media file type so that consumers of the crate can open `data.csv` in an appropriate program,
and can be particularly important for less common file extensions frequently encountered in outputs from research software and instruments.

You can override the license for the root data entity by specifying a `license` property on the data entity itself.

For more information on describing files and folders,
including their recommended and required attributes,
see section on [data entities](https://www.researchobject.org/ro-crate/specification/1.2/data-entitites.html).


:::::::::::::::::::::::::::::::::::::::: keypoints
- Data entities are files & folders within the root, as well as external Web references
- Required properties for files are name and encodingFormat
::::::::::::::::::::::::::::::::::::::::::::::::::