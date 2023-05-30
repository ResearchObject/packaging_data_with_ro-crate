---
title: RO-Crate - Introduction
level: Introductory
teaching: 10
exercises: 10
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


## Introduction

This tutorial assumes you have already completed [An overview of the RO-Crate concept and its implementations](https://gallantries.github.io/video-library/videos/ro-crates/intro/slides/) and have a basic understanding of working with JSON.


In this tutorial, meant to be read along with the [RO-Crate specification](https://www.researchobject.org/ro-crate/1.1/), we'll walk through the initial steps for creating a basic RO-Crate. You are invited to replicate the below steps on your local computer.



# Copyright and license

© Copyright 2021-2023 University of Technology Sydney, The University of Manchester UK and RO-Crate contributors.

Licensed under the Apache License, Version 2.0 (the “License”); you may not use this file except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an “AS IS” BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License. 

## Changes

This tutorial has been adapted from the revised [RO-Crate introduction for 1.2](https://www.researchobject.org/ro-crate/1.2-DRAFT/introduction.html) by Stian Soiland-Reyes. Changes include:
* Rewriting to tutorial style with exercises
* Adaptation to Galaxy Training Material rendering
* Explicit links to RO-Crate specifications
* Example changed to different organization and license
* Modiied for Carpentries style




{% include links.md %}

