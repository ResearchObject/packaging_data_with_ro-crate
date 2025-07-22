---
title: Contextual entities
teaching: 2
exercises: 2
---

:::::::::::::::::::::::::::::::::::::::: questions
- How can I describe contextual information about how data was created?
- How can I represent an instrument used to generate a data file?
::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: objectives
- Understand the difference between contextual and data entities
- Add a contextual entity to the RO-Crate
::::::::::::::::::::::::::::::::::::::::::::::::::


## Contextual entities

Entities that we have added under `hasPart` are considered _data entities_,
while entities only referenced from those are considered _contextual entities_

A contextual entity might describe:
- The software that processed the data
- The instrument that captured it
- The project that funded it

These entities don’t contain data themselves but give semantic context to the data you’re describing.

You may notice the subtle difference between a _data entity_ that is conceptually part of the RO-Crate and is file-like (containing bytes),
while a _contextual entity_ is a representation of a real-life organization that can't be downloaded:
following the URL, we would only get its _description_.
The section [contextual entities](https://www.researchobject.org/ro-crate/specification/1.2/contextual-entities.html)
explores several of the entities that can be added to the RO-Crate to provide it with a **context**,
for instance how to link to authors and their affiliations.
Simplifying slightly, a data entity is referenced from `hasPart` in a `Dataset`,
while a contextual entity is referenced using any other defined property.

## Instrument details

For example, the instrument used to capture weather data is not itself part of the dataset, but knowing what device created the measurements helps the data consumer interpret and validate the data.

:::::::::::::::::::::::::::::::::::::::: challenge
## Add an instrument as a contextual entity

In your data.csv entity, use instrument to reference the equipment used.
Then define the instrument entity in the @graph.
 
:::::::::::::::  solution
```json
{
  "@id": "data.csv",
  "@type": "File",
  "name": "Rainfall Katoomba 2022-02",
  "description": "Rainfall data for Katoomba, NSW Australia February 2022",
  "encodingFormat": "text/csv",
  "instrument": { "@id": "https://example.org/instrument/ws-2000" }
},    
{
  "@id": "https://example.org/instrument/ws-2000",
  "@type": "ThiIndividualProductng",
  "name": "WS-2000 Weather Station",
  "description": "Automated weather station used to record temperature and rainfall data in Katoomba, Australia.",
  "url": "https://example.org/instrument/ws-2000"
},
```  
:::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::::


:::::::::::::::::::::::::::::::::::::::: keypoints
- Contextual entities are not considered part of the crate’s file structure
- Instruments, software, and projects can be described as contextual entities
- Cntextual entities can provide provenance about data capture and processing
::::::::::::::::::::::::::::::::::::::::::::::::::


