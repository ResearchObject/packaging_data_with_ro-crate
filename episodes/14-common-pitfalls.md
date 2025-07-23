---
title: Avoiding Common pitfalls
teaching: 5
exercises: 1
---

:::::::::::::::::::::::::::::::::::::::: questions
- What are common mistakes to avoid when authoring RO-Crate packages?
- How can I troubleshoot errors in the metadata file?
::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: objectives
- Recognize common errors in RO-Crate metadata
- Review a checklist of requirements for RO-Crate structure and format
::::::::::::::::::::::::::::::::::::::::::::::::::

## Introduction

Creating RO-Crate packages by hand is a great way to understand their structure, but it’s easy to run into small issues that can break the crate or make it difficult to interpret. This section outlines the most frequent problems and how to avoid them.

---

## Common Mistakes

### 1. Invalid or malformed JSON

- **Problem**: Forgetting commas, quotes, or brackets.
- **Fix**: Use an editor with JSON syntax highlighting (e.g., VS Code) and test your crate in the [JSON-LD Playground](https://json-ld.org/playground/).

> Tip: Run your `ro-crate-metadata.json` through a JSON validator before uploading it anywhere.

---

### 2. Missing `@context` or `@graph`

- **Problem**: Forgetting to include the required top-level keys in the RO-Crate metadata file.
- **Fix**: Make sure every `ro-crate-metadata.json` starts like this:

```json
{
  "@context": "https://w3id.org/ro/crate/1.2/context",
  "@graph": [ /* your entities here */ ]
}
```

### 3. Using nested JSON instead of flat structure

- **Problem**: Embedding full descriptions of related entities instead of referencing them with `@id`.
- **Fix**: Use cross-referencing. Define each entity once and refer to it using its `@id`.

### 4. Repeating or mismatched @id values
- **Problem**: Accidentally defining two entities with the same @id, or referencing an entity with an @id that doesn’t exist.
- **Fix**: Ensure every @id is unique and points to an entity defined in the metadata.

### 5. Forgetting required metadata on key entities
- **Problem**: The root dataset doesn’t have name or license, or files are missing type.
- **Fix**: Always include the required fields for the root (./) and for files:
```json
{
  "@id": "./",
  "@type": "Dataset",
  "name": "My Crate",
  "description": "An example research dataset.",
  "license": { "@id": "http://spdx.org/licenses/CC0-1.0" }
}
```
:::::::::::::::::::::::::::::::::::::::: challenge
## Spot the errors
Here's an incorrect metadata example. Identify and fix the issues.

```json
{
  "@context": "https://w3id.org/ro/crate/1.2/context",
  "@graph": [
    {
      "@id": "./",
      "@type": "Folder",
      "name": "Rainfall data",
      "hasPart": {
        "@id": "data.csv",
        "name": "Rainfall Katoomba",
        "encodingFormat": "comma separated values",
      }
    }
  ]
}
```
:::::::::::::::  solution
1. The `@type` for the root should be "Dataset", not "Folder". 
2. The hasPart value should reference an @id, not contain the full entity.
3. The data.csv entity should be defined separately in the @graph.
4. The encodingFormat should be a valid IANA media type (e.g., "text/csv").
5. Missing required properties (description, datePublished, license) on the root dataset.
::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: keypoints
- Include a metadata descriptor with @id: "ro-crate-metadata.json" and @type: "CreativeWork"
- Ensure each referenced @id is also defined as an entity in @graph
- Use unique identifiers for each entity
- Ensure every entity has an @id and a meaningful @type
- Use tools like JSON validators and JSON-LD playgrounds to check your metadata
::::::::::::::::::::::::::::::::::::::::::::::::::