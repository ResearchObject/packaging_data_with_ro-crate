---
title: "Turning a folder into an RO-Crate"
teaching: 4
exercises: 3
questions:
- How can I start a new RO-Crate?
objectives:
- Creating a skeleton RO-Crate Metadata File
- Use the JSON-LD pre-amble to enable Linked Data

keypoints:
- Adding a RO-Crate Metadata file to a folder turns it into an RO-Crate
- The RO-Crate Root is the top-level folder of the crate
- RO-Crate uses schema.org as base vocabulary
- The JSON-LD context enables optional Linked Data processing
- Descriptions are listed flatly as entities in the @graph array
---


## Turning a folder into an RO-Crate

In the simplest form, to describe some data on disk, an _RO-Crate Metadata File_ is placed in a folder alongside a set of files or folders.

First create a new folder `crate1/` and add a single file `data.csv` to it to represent our dataset:

```
"Date","Minimum temperature (°C)","Maximum temperature (°C)","Rainfall (mm)"
2022-02-01,16.0,28.4,0.6
2022-02-02,16.3,17.2,12.4
```

{: .source}

Next, to turn this folder into an RO-Crate we need to add the _RO-Crate Metadata File_, which has a fixed filename.
Create the file `ro-crate-metadata.json` using [Visual Studio Code](https://code.visualstudio.com/) or your favourite editor, then add the following JSON:

```json
{
  "@context": "https://w3id.org/ro/crate/1.1/context",
  "@graph": [

  ]
}
```

Your folder should now look like this:

![Folder listing of crate1, including data.csv and ro-crate-metadata.json](../fig/crate1-folders.svg "Any folder can be made into an RO-Crate by adding <code>ro-crate-metadata.json</code>")

The presence of the reserved `ro-crate-metadata.json` filename means that `crate1` (and its children) can now be considered to be an **RO-Crate**. We call the top-level folder of the crate (i.e. `crate1`) the **RO-Crate Root** and can now refer to its content with relative file paths.

We also need to make some declarations within the JSON file to turn it into a valid _RO-Crate Metadata Document_, explained in the next episode.

> ## JSON-LD - the file format for `ro-crate-metadata.json`
>
> The `ro-crate-metadata.json` file uses a data format called [JSON-LD](https://json-ld.org). This is a format that is easy for both humans and machines to read and write, based on the widely used [JSON](https://www.json.org/json-en.html) format.
>
> The LD in JSON-LD stands for Linked Data, which is a way of interconnecting structured data across different applications (e.g. referencing an author by their [ORCID](https://orcid.org) identifier).
>
> You do not need a deep understanding of Linked Data or JSON-LD for this tutorial or for using RO-Crate in general.
{: .callout}

> ## What are `@context` and `@graph`?
>
> The `@context` provides a list of the types of data that we may include in our metadata (such as `Person` or `File`). This helps with interlinking different pieces of metadata, as we normally expect to collect different information about a person than we would about a file. The permitted types are mostly based on the [schema.org](https://schema.org/docs/full.html) vocabulary, but can be extended with [RO-Crate profiles](https://www.researchobject.org/ro-crate/profiles.html) (beyond the scope of this lesson).
>
> The `@graph` is a list that will contain our metadata. We'll populate this in the next episodes.
{: .callout}

{% include links.md %}
