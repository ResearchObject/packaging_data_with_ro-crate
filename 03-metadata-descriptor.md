---
title: Making a metadata descriptor
teaching: 2
exercises: 2

---

::::::::::::::::::::::::::::::::::::::: questions
- Which RO-Crate version is used?
- How can the crate self-identify as an RO-Crate?
::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::: objectives
- Add the first entity to the JSON-LD @graph
- Indicate the version of RO-Crate
::::::::::::::::::::::::::::::::::::::::::::::::::

## RO-Crate Metadata descriptor 

The first JSON-LD _entity_ to add in the `@graph` array has the `@id` value of `ro-crate-metadata.json` to describe the JSON file itself:


```json
{
    "@id": "ro-crate-metadata.json",
    "@type": "CreativeWork",
    "conformsTo": {"@id": "https://w3id.org/ro/crate/1.1"},
    "about": {"@id": "./"}
}
```

This required entity, known as the [RO-Crate Metadata Descriptor](https://www.researchobject.org/ro-crate/1.1/root-data-entity.html#ro-crate-metadata-file-descriptor),
helps this file self-identify as an RO-Crate Metadata Document,
which is conforming to (`conformsTo`) the RO-Crate specification version 1.1.
Notice that the `conformsTo` URL corresponds to the `@context` URL version-wise,
but they have two different functions.
The context brings the defined terms into the metadata document,
while the conformance declares which RO-Crate conventions of using those terms are being followed.

::::::::::::::::::::::::::::::::::::::: callout
## RO-Crate versions
This tutorial is written for RO-Crate 1.1,
the RO-Crate website will list the [current specification version](https://www.researchobject.org/ro-crate/specification.html)
-- RO-Crates can generally be upgraded to newer versions following [semantic versioning](https://semver.org/) conventions,
but check the [change log](https://www.researchobject.org/ro-crate/1.1/appendix/changelog.html) for any important changes.
The next development version of the specification, indicated with a `-DRAFT` status,
may still be subject to changes and should only be used with caution.
::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::: keypoints
- The RO-Crate Metadata Descriptor describes the JSON-LD file itself
- RO-Crate specifications are versioned
- The version of RO-Crate is indicated using the conformsTo property
::::::::::::::::::::::::::::::::::::::::::::::::::


