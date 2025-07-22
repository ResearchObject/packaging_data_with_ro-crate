---
title: Authorship in crates
teaching: 2
exercises: 4
---

:::::::::::::::::::::::::::::::::::::::: questions
- How can I list who made the content of the crate?
- How do I affiliate a person with their place of work?
::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: objectives
- Adding and describing a Person contextual entity
- Adding a Organization contextual entity
- Understanding what it means to be an authof of the crate
- Indicating the publisher of the RO-Crate
::::::::::::::::::::::::::::::::::::::::::::::::::


## Authorship

Moving back to the RO-Crate root `./`, let's specify who are the authors of the crate.


:::::::::::::::::::::::::::::::::::::::: challenge
## Add an author and affiliation

1. Add yourself as an [`author`](https://www.researchobject.org/ro-crate/specification/1.2/contextual-entities.html#people)
   of the crate using the type `Person`
2. Include your preferred name. 
3. If you don't have an [ORCID](https://orcid.org/), you may use either the URL of your main home page at your institution,
   or a crate-local identifier like `#alice`.
4. Include your `affiliation` as a string value.

:::::::::::::::  solution
```json
{
  "@id": "./",
  "@type": ["Dataset", "LearningResource"],
  "author": {"@id": "https://orcid.org/0000-0002-1825-0097"},
  "…": "…"
},
{
  "@id": "https://orcid.org/0000-0002-1825-0097",
  "@type": "Person", 
  "name": "Josiah Carberry",
  "affiliation": "Brown University"
}
```
:::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: discussion
## Who can be authors of an RO-Crate?

When we say someone is an author of a crate,
it means they have contributed something substansively to its content (typically the data).
Agreement on what is considered authorship on a dataset can be tricky;
you may decide some people would be better represented as `contributor`.
One advantage of RO-Crate is that authorship can be declared explicitly also on each data entity,
so it can be clearer where each person have contributed (e.g. a statistician is author of an R script).
This means that generally the authors of the crate can be a broader,
more inclusive list than perhaps traditionally recognized as academic authorship.
::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: challenge
## Add an organization

1. "Unroll" your `affiliation` of the person as cross-reference to another contextual entity,
   typed as an `Organization`. 
2. You can use [ROR](https://ror.org/) to find an identifier for most educational/research institutions,
   or you can use the main web page of your organization as its `@id`.
 
:::::::::::::::  solution
```json
{
  "@id": "https://orcid.org/0000-0002-1825-0097",
  "@type": "Person", 
  "name": "Josiah Carberry",
  "affiliation": {
    "@id": "https://ror.org/05gq02987"
  }
},
{
  "@id": "https://ror.org/05gq02987",
  "@type": "Organization",
  "name": "Brown University",
  "url": "http://www.brown.edu/"
}
```
:::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::::

The reuse of existing identifiers is important for both persons and organization from a FAIR perspective,
as their names may not be globally unique.

:::::::::::::::::::::::::::::::::::::::: challenge
## Specify a publisher

1. Now imagine you are going to publish the RO-Crate on your institution's web pages. 
2. Cross-reference the same Organization entity with `publisher` from the RO-Crate Root entitity:

:::::::::::::::  solution
```json
{
   "@id": "./",
   "@type": ["Dataset", "LearningResource"],
   "publisher": {"@id": "https://ror.org/05gq02987"},
   "…": "…"
}
```
:::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::::


:::::::::::::::::::::::::::::::::::::::: keypoints
- Authors are described as separate entities
- Organization entities can be shared by multiple persons having the same affiliation
- Crate authors made (some) of the crate's content
- Publishers of an RO-Crate are typically organizations
::::::::::::::::::::::::::::::::::::::::::::::::::
