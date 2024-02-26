---
title: "Adding cross-references"
teaching: 3
exercises: 4
questions:
- "How can I describe an entity further?"
- "How can I cross-reference different entities?"
objectives:
- "Understand cross-references in flattened JSON-LD"
- "Add a data entity reference from the root entity"
- "Add another type to the root entity"
keypoints:
- "The @id uniquely identifies the entity within the RO-Crate"
- "The @id key is used for cross-referencing"
- "Multiple types can be listed by using an array"
---



## About cross-references

In a RO-Crate Metadata Document, entities are cross-referenced using `@id` reference objects, rather than using deeply nested JSON objects.
In short, this _flattened JSON-LD_ style (shown below) allows any entity to reference any other entity, and RO-Crate consumers can directly find all the descriptions of a given entity as a single JSON object. 


![JSON block with id `ro-crate-metadata.json` has some attributes, `conformsTo` RO-Crate 1.2, and `about` referencing id `./`. In second JSON block with id <code>./</code> we see additional attributes such as its name and description.](../fig/introduction-figure-1.svg "showing RO-Crate Metadata descriptor's <code>about</code> property pointing at the RO-Crate Root entity with matching <code>@id</code>")


> ## Add cross-reference to data entity
>
> Consider the root Data Entity `./`, and add such a cross-reference to the file `data.csv` using the _property_ called `hasPart`:
> 
> > ## Solution
> >
> > ```json
> > {
> >     "@id": "./",
> >     "@type": "Dataset",
> >     "hasPart": [ 
> >       {"@id": "data.csv"} 
> >     ],
> >     "…": "…"
> > }
> > ```
> {: .solution}
{: .challenge}


The RO-Crate root is always typed `Dataset`, though `@type` may in some cases have additional types by using a JSON array instead of a single value.  Most entities can have such more specific types, e.g. chosen from [schema.org type list](https://schema.org/docs/full.html).

> ## Add an additional type
> 
> 1. Navigate the schema.org type list to find a subtype of `CreativeWork` that is suitable for a learning resource.
> 2. Modify the root entity's `@type` to be an array.
> 3. Add the type name for learning resource at the end of the array.
> 
> > ## Solution
> >
> > ```json
> > {
> >     "@id": "./",
> >     "@type": ["Dataset", "LearningResource"],
> >     "hasPart": [ 
> >       {"@id": "data.csv"} 
> >     ],
> >     "…": "…"
> > }
> > ```
> {: .solution}
{: .challenge}

The root has several metadata properties that describe the RO-Crate as a whole, considering it as a Research Object of collected resources. The section on [root data entity](https://www.researchobject.org/ro-crate/1.1/root-data-entity.html) details further the required and recommended properties of the root `./`. 



{% include links.md %}

