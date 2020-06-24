---
layout: single
title: Semantic Definition Format
overview: true
permalink: /sdflanguage/

sidebar:
  nav: "sdf_nav"

toc: true
toc_label: "Table of Contents"
toc_icon: "cog"
toc_sticky : true
---
## Introduction

Semantic Definition Format (SDF) is a new description format to describe abstract data models.
SDF conveys abstract meta-model for IoT device affordances, behavior, and context
Decoupled from network bindings, protocol-agile
- Common categories for affordances 
- Common categories for constraints
- Common format for definitions

Initial focus on affordances is to normalize device-facing interactions across SDO's and vendors.
The choice of creating a new description format was due to that used description formats by the participating organizations where tailor made for the purpose in the organization only.
It was deemed to be too difficult to take an existing definition format and change it to in such way that it would satisfy the need of conveying data models.

The requirements that needs to be full filled are:
- conveying rest-full and action based paradigmns
- conveying type information
- conveying semantic information
- data defined has to be agnostic of the transport layer
- enable reuse of properties and components by multiple models

SDF is not created from scratch, it is using JSON as much as possible.
Using JSON as a representation language has a few advantages:

- The content is machine-readable, without the need to construct
  special parsers.
- The syntax of the SDF files can be validated by a validator for one
  of these data description languages.  SDF 1.0 uses both CDDL
  ([RFC8610][]) and the formats proposed at json-schema.org for this.
- The structure of the data themselves can be modelled in similar
  ways; [SDF language][] 1.0 borrows specific elements of the json-schema.org
  proposals for this.
- Abundant tools and libraries are available to produce/consume JSON,
  so tooling to work with SDF models can be created efficiently.

The syntax and semantics of the SDF format are described in the [SDF][] repository.
The [terminology][] page relates the SDF terms against SDO used terms.

## Verification of SDF

To make sure that SDF is up to the task to convey the different models
that are currently in use within the participating organizations, the [playground][] repository has been
created. The playground repository contains SDF models contributed by the participating organizations.
Many of these models are automatically generated from the source materials of the participating organizations to verify that automatic translation is obtainable with SDF.

## Syntax validation

The [playground][], [exploratory][], and [unit_test][] repositories have a CI system in place that analyzes
pull requests and provides reports with respect to their syntax usage.
All models in the [playground][] are syntactically valid SDF files, while the other
repositories tolerate (or deliberately contain) deviations.

## Future steps

Next steps for SDF development (conducted in parallel):

- Standardize the Semantic Definition Format (SDF) in IETF
- enhance SDF to convey complex models

## Repository overview

| repo name       | Description                                                          |
|-----------------|----------------------------------------------------------------------|
| [SDF][]         | Semantic Definition Format (SDF) for Data and Interactions of Things |
| [IETF108][]     | Information for the standardization work for IETF meeting 108        |
| [tools][]       | SDF tools                                                            |
| [playground][]  | playground of non-official data models that could be OneDM data models, but aren't yet. Correct SDF syntax.  |
| [exploratory][] | playground of non-official data models that explore new SDF features or new ways of using SDF. Not always conforming to current SDF validation syntax. |
| [unit_test][]   | SDF models for unit (error) testing                        |


[SDF]: https://github.com/one-data-model/SDF
[tools]: https://github.com/one-data-model/tools
[playground]: https://github.com/one-data-model/playground
[exploratory]: https://github.com/one-data-model/exploratory
[unit_test]: https://github.com/one-data-model/unit_test


[SDF language]: https://onedm.org/SDF/sdf.html
[IETF SDF]: https://www.ietf.org/id/draft-onedm-t2trg-sdf-00.html
[IETF108]: https://github.com/one-data-model/ietf108

[RFC8610]: https://tools.ietf.org/html/rfc8610


[terminology]: /terminology
