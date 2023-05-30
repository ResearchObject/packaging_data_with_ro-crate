---
title: Introduction
level: Introductory
teaching: 17
exercises: 0
requirements:
- type: none
  title: "Files and folder organization"
- type: none
  title: "Familiarity with JSON file format and editor/IDE"
- type: external
  title: "An overview of the RO-Crate concept and its implementations"
  link: "https://gallantries.github.io/video-library/videos/ro-crates/intro/slides/"
- type: "internal"
  topic_name: data-science
  tutorials:
      - cli-basics

license: Apache-2.0

copyright: © Copyright 2021-2023 University of Technology Sydney, The University of Manchester UK and RO-Crate contributors

follow_up_training: []
questions:
- How do I package data in a FAIR way?
- How can I list the authors of individual files?
- Can I use multiple licenses in the same data package?
- How can I visualize JSON-LD metadata?

objectives:
- Construct an RO-Crate by hand using JSON
- Describe each part of the Research Object
- Learn basic JSON-LD to create FAIR metadata
- Connect different parts of the Research Object using identifiers

time_estimation:  30M
keypoints:
- RO-Crate provides a structure to make FAIR data packages
- schema.org in JSON-LD provides a controlled vocabulary for FAIR metadata
- Each entity of the crate is described separately
- Cross-references between entities create a graph
- The RO-Crate specification recommends which types and keys to use

subtopic: ro-crate
contributors:
  - stain
  - ptsefton

priority: 1

abbreviations:
  FAIR: Findable, Accessible, Interoperable, Reusable; a set of principles for publishing research data and metadata
  JSON: JavaScript Object Notation, a generic structured text-based data format
  JSON-LD: JSON Linked Data, a way to express Linked Data (RDF) using regular JSON
  RO-Crate: Research Object Crate; a way to package research data with structured FAIR metadata
---


# Introduction

This tutorial assumes you have already completed [An overview of the RO-Crate concept and its implementations](https://gallantries.github.io/video-library/videos/ro-crates/intro/slides/):

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/5GYdN5B1tc8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>
  <a href="https://www.youtube.com/watch?v=5GYdN5B1tc8"><img src="https://i.ytimg.com/vi/5GYdN5B1tc8/maxresdefault.jpg" alt="An overview of the RO-Crate concept and its implementations" />
</iframe>

_Video: An overview of the RO-Crate concept and its implementations_ (see also [slides and transcript](https://doi.org/10.5281/zenodo.7828632))


## Tutorial walk-through

In this tutorial, meant to be read along with the [RO-Crate specification](https://www.researchobject.org/ro-crate/1.1/), we'll walk through the initial steps for creating a basic RO-Crate. You are invited to replicate the below steps on your local computer.




{% include links.md %}

