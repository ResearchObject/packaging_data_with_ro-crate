---
title: "Visualizing a crate as HTML preview"
teaching: 0
exercises: 0
questions:
- "Key question (FIXME)"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---

## HTML preview

An RO-Crate can be distributed on disk, in a packaged format such as a zip file or disk image, or placed on a static website. In any of these cases, an RO-Crate can have an accompanying HTML version (`ro-crate-metadata.html`) designed to be human-readable. 

![Example dataset for RO-Crate specification](../fig/ro-crate-preview-example.png){: .image-with-shadow }

> ## Navigate the RO-Crate preview
> 
> Try navigating the [preview of the running example](../files/rainfall-1.2.1/ro-crate-preview.html) and find:
>
> 1. What is the license of the rainfall CSV?
> 2. What is the affiliation of the crate's author?
> 3. What does the Validity Check inspect
> 4. What is not covered by this check?
> 
> > ## Solution
> >
> > 1. CC BY-NC-SA 4.0 International
> > 2. Brown University
> > 3. The context, and for root dataset: existance, valid identifier, name, description, license and date published.  
> > 4. The other entities were not checked, e.g. the `affiliation` of the author.
> {: .solution}
{: .challenge}


## Advanced: Generating HTML preview

If you have [Node JS](https://nodejs.org/) installed, you can install and try the [ro-crate-html](https://www.npmjs.com/package/ro-crate-html) tool on your `crate1` folder:

```bash
npm i -g ro-crate-html
rochtml crate1/ro-crate-metadata.json
```

Or if you have [Docker](https://www.docker.com/), something like:

```bash
docker pull simleo/rochtml
docker run -v $(pwd):/crate -it simleo/rochtml -c ro-crate-preview_files /crate/ro-crate-metadata.json
```

The above will generate a `ro-crate-preview.html` file within your RO-Crate Root. Experiment with modifying the Metadata file and re-generating the HTML preview to see how your rendering differs from the [running example](../files/rainfall-1.2.1/ro-crate-preview.html).


{% include links.md %}

