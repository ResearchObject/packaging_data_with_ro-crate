---
title: Visualizing a crate as HTML preview
teaching: 3
exercises: 3
---

:::::::::::::::::::::::::::::::::::::::: questions
- How can an RO-Crate be rendered without showing the JSON?
- How can I generate a preview of the RO-Crate?
::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: objectives
- Explore a HTML preview of an RO-Crate
::::::::::::::::::::::::::::::::::::::::::::::::::

## HTML preview

An RO-Crate can be distributed on disk,
in a packaged format such as a zip file or disk image,
or placed on a static website.
In any of these cases,
an RO-Crate can have an accompanying HTML version (`ro-crate-metadata.html`) designed to be human-readable. 

![Example dataset for RO-Crate specification](../fig/ro-crate-preview-example.png){alt='' .image-with-shadow }

:::::::::::::::::::::::::::::::::::::::: challenge
## Navigate the RO-Crate preview

Try navigating the [preview of the running example](../files/rainfall-1.2.1/ro-crate-preview.html) and find:

1. What is the license of the rainfall CSV?
2. What is the affiliation of the crate's author?
3. What does the Validity Check inspect
4. What is not covered by this check?

:::::::::::::::  solution
1. CC BY-NC-SA 4.0 International
2. Brown University
3. The context, and for root dataset: existance, valid identifier, name, description, license and date published.  
4. The other entities were not checked, e.g. the `affiliation` of the author.
:::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::::


## Advanced: Generating HTML preview

The [LDACA RO-Crate Playground](https://ro-crate.ldaca.edu.au/) is a web-based tool that lets you upload an RO-Crate and view a structured HTML summary of its metadata.

Navigate to the [LDACA RO-Crate Playground](https://ro-crate.ldaca.edu.au/) Click "Start Packaging", then click "Examples." From the examples list, click "Try it" for "sample-crate."
You will see a tab called "HTML Preview" that contains a preview of the RO-Crate metadata.

If you want to generate a preview of your own RO-Crate, you can click "Create New" to create a new RO-Crate, where you can upload your data files and add metadata. Once you have added your data files and metadata, click the "HTML Preview" button at the top of the page.

The tool will generate a preview of your RO-Crate, which you can then download as an HTML file. This preview will show the entities in your RO-Crate, including the root dataset, data files, licenses, authors, and any other contextual entities you have added. You can save the resulting HTML page using your browser’s “Save As” feature, or extract the generated preview for distribution.



:::::::::::::::::::::::::::::::::::::::: keypoints
- RO-Crate can be rendered into a HTML preview
- RO-Crate previews tend to show each entity separately
- The preview HTML can be added as part of the RO-Crate
::::::::::::::::::::::::::::::::::::::::::::::::::