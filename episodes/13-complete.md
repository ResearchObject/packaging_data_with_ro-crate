---
title: "Completed RO-Crate"
teaching: 1
exercises: 0
---

:::::::::::::::::::::::::::::::::::::::: questions
- "What should the final RO-Crate look like?"
::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: objectives
- "Compare your RO-Crate with the solution"
- "Understand the flattened nature of the JSON-LD"
::::::::::::::::::::::::::::::::::::::::::::::::::

## Complete RO-Crate Metadata Document

:::::::::::::::::::::::::::::::::::::::: challenge


The final RO-Crate Metadata Document constructed in this tutorial should look something like:

:::::::::::::::  solution
## `ro-crate-metadata.json`

```json
{
 "@context": "https://w3id.org/ro/crate/1.1/context",
 "@graph": [
   {
     "@id": "ro-crate-metadata.json",
     "@type": "CreativeWork",
     "conformsTo": {"@id": "https://w3id.org/ro/crate/1.1"},
     "about": {"@id": "./"}
   },
   {
     "@id": "./",
     "@type": ["Dataset", "LearningResource"],
     "hasPart": [
       {"@id": "data.csv"}
     ],
     "name": "Example dataset for RO-Crate specification",
     "description": "Official rainfall readings for Katoomba, NSW 2022, Australia",
     "datePublished": "2023-05-22T12:03:00+0100",
     "license": {"@id": "http://spdx.org/licenses/CC0-1.0"},
     "author": { "@id": "https://orcid.org/0000-0002-1825-0097" },
     "publisher": {"@id": "https://ror.org/05gq02987"}
   },
   {
     "@id": "data.csv",
     "@type": "File",
     "name": "Rainfall Katoomba 2022-02",
     "description": "Rainfall data for Katoomba, NSW Australia February 2022",
     "encodingFormat": "text/csv",
     "license": {"@id": "https://creativecommons.org/licenses/by-nc-sa/4.0/"}
   },
   {
     "@id": "https://creativecommons.org/licenses/by-nc-sa/4.0/",
     "@type": "CreativeWork",
     "name": "CC BY-NC-SA 4.0 International",
     "description": "Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International"
   },    
   {
     "@id": "http://spdx.org/licenses/CC0-1.0",
     "@type": "CreativeWork",
     "name": "CC0-1.0",
     "description": "Creative Commons Zero v1.0 Universal",
     "url": "https://creativecommons.org/publicdomain/zero/1.0/"
   },    
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
 ]
}
```
:::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: keypoints
- "A single RO-Crate lists all the entities"
- "The order of entities in the @graph array is not important"
::::::::::::::::::::::::::::::::::::::::::::::::::

