---
title: Describing the root entity
teaching: 4
exercises: 4
---
:::::::::::::::::::::::::::::::::::::::: questions
- How can I describe the crate?
- How do I specify the license of the RO-Crate?
::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: objectives
- Learn about required metadata for the RO-Crate Root
- Understand license identifiers using SPDX
::::::::::::::::::::::::::::::::::::::::::::::::::

## Describing the root entity

When describing the [root entity](https://www.researchobject.org/ro-crate/specification/1.2/root-data-entity.html#direct-properties-of-the-root-data-entity),
the properties generally apply to the whole of the crate.
For instance it is a good idea to give a description of why these resources are gathered in a crate,
as well as giving the crate a name and license for FAIR reuse and citation.

:::::::::::::::::::::::::::::::::::::::: challenge
## Add metadata to root entity

Try to add the `name`, `description` and `datePublished` properties,
and for `license` as a cross-reference,
use [SPDX](https://spdx.org/licenses/) license list to find the identifier for Creative Commons Zero
or another license of your choice:

:::::::::::::::  solution
```json
{
  "@id": "./",
  "@type": "Dataset",
  "hasPart": [ ],
  "name": "Example crate",
  "description": "I created this example by following the tutorial",
  "datePublished": "2023-05-22",
  "license": { "@id": "http://spdx.org/licenses/CC0-1.0"}  
}
```
:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::


:::::::::::::::::::::::::::::::::::::::: callout
## License identifiers

In the above solution,
the identifier for CC0-1.0 <http://spdx.org/licenses/CC0-1.0> is slightly
different from their listed web page URI <https://spdx.org/licenses/CC0-1.0.html>
-- the former is chosen to align with [SPDX JSON-LD identifiers](https://github.com/spdx/license-list-data/tree/main/jsonld),
which unfortunately are not shown directly on their website as _permalinks_. 
It is not a requirement in RO-Crate to use permalinks for `@id` of entities like licenses, 
it is nevertheless best practice to propagate permalinks where known.
::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: discussion
## Choosing a license

Choosing a license appropriate for your dataset can be non-trivial,
particularly if third-party data/software and multiple organizations are involved.
See [FAIR Cookbook on licensing](https://faircookbook.elixir-europe.org/content/recipes/reusability/ATI-licensing.html).
It is worth noting that an RO-Crate permits data entities to have a `license` different from the overall Crate license.
It is still recommended to choose an overall Crate license that can legally apply across all the content in the RO-Crate Root.
::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: keypoints
- Name, description, date published and license are required for the RO-Crate Root"
- RO-Crate allows multiple licenses for different parts
::::::::::::::::::::::::::::::::::::::::::::::::::



