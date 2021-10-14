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
SDF conveys abstract meta-model for IoT device affordances, behavior, and context,
decoupled from communication details. SDF provides:
- Common categories for affordances
- Common categories for constraints
- Common format for definitions

Initial focus on affordances is to normalize device-facing interactions across SDOs and vendors.
The choice of creating a new description format was due to that used description formats by the participating organizations where tailor made for the purpose in the organization only.
It was deemed to be too difficult to take an existing definition format and change it to in such way that it would satisfy the need of conveying data models.

The requirements that need to be fulfilled are:

- conveying RESTful and action based paradigms
- conveying type information
- conveying semantic information
- data defined has to be agnostic of the transport layer
- enable reuse of properties and components by multiple models

SDF is not created from scratch, it is using existing JSON features as much as possible.
Using JSON as a representation language has a few advantages:

- The content is machine-readable, without the need to construct
  special parsers.
- The syntax of the SDF files can be validated by a validator for one
  of these data description languages.  SDF 1.0 uses both CDDL
  ([RFC8610][]) and the formats proposed at json-schema.org for this.
- The structure of the data themselves can be modelled in similar
  ways; SDF borrows specific elements of the json-schema.org
  proposals for this.
- Abundant tools and libraries are available to produce/consume JSON,
  so tooling to work with SDF models can be created efficiently.

The syntax and semantics of SDF are described in the SDF specification.
After the initial development at the OneDM group, the SDF standardization continues now in the [IETF ASDF Working Group][ASDF]. Information about the latest published draft of SDF is available in the [IETF Data Tracker][IETF SDF]. The latest editor draft is available in the [SDF language] repository.
The [terminology][] page relates the SDF terms against terms used in other SDOs.

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



[tools]: https://github.com/one-data-model/tools
[playground]: https://github.com/one-data-model/playground
[exploratory]: https://github.com/one-data-model/exploratory
[unit_test]: https://github.com/one-data-model/unit_test

[SDF language]: https://github.com/ietf-wg-asdf/SDF
[IETF SDF]: https://datatracker.ietf.org/doc/draft-ietf-asdf-sdf/
[ASDF]: https://datatracker.ietf.org/wg/asdf/about/
[RFC8610]: https://tools.ietf.org/html/rfc8610


[terminology]: /terminology

<!--  LocalWords:  SDF RESTful
 -->
