---
layout: default
title: OneDM Overview
overview: true
permalink: /overview/
---

# One Data Model overview


The goal of OneDM is to arrive at a common set of data and interaction
models that describe IoT devices.
This will enable an application to work with IoT devices from
different ecosystems, without a need for converting data and interactions from the
model of one organization to that of the other.
Ideally, for every class of IoT device, there is just a single model
selected/created by the participating organisations, which everyone can adopt.

To achieve that goal the first step to take is to have a common way how to write down a model.
Since all participating organizations are  currently doing this
in their own ways, it makes sense to develop a single way to describe models.
Hence the Semantic Definition Format (SDF) is created.
The syntax and semantics of the SDF format are described in the [SDF][] repository.

SDF is representing the models in JSON.
Using JSON as a representation language has a few advantages:

- The content is machine readable, without the need to construct
  special parsers.
- The syntax of the SDF files can be validated by a validator for one
  of these data description languages.  SDF 1.0 uses both CDDL
  ([RFC8610][]) and the formats proposed at json-schema.org for this.
- The structure of the data themselves can be modelled in similar
  ways; SDF 1.0 borrows specific elements of the json-schema.org
  proposals for this.
- Abundant tools and libraries are available to produce/consume JSON,
  so tooling to work with SDF models can be created efficiently.

To make sure that SDF is up to the task to convey the different models
that are currently in use, the [playground][] repository has been
created, with models contributed by various organisations in SDF format.
Many of these models are automatically generated from the source materials of the participating organisations.
Most of the participating organisations have created tooling that supports converting their models to and from SDF.
Hence full round tripping is available to verify if the SDF syntax can convey all the needed information.
The [playground][], [exploratory][], and [unit_test][] repositories have a CI system in place that analyzes
pull requests and provides reports with respect to their syntax usage.
The aim is that all models in the
[playground][] are syntactically valid SDF files, while the other
repositories tolerate (or deliberately contain) deviations.

Next steps for OneDM (conducted in parallel):

- Standardize the Semantic Definition Format (SDF) in IETF
- Select models in the playground to for OneDM
- Further develop SDF so that more complex models can be created

## Repository overview

| repo name       | Description                                                          |
|-----------------|----------------------------------------------------------------------|
| [SDF][]         | Semantic Definition Format (SDF) for Data and Interactions of Things |
| [tools][]       | SDF tools                                                            |
| [playground][]  | playground of non-official data models that could be OneDM data models, but aren't yet. Correct SDF syntax.  |
| [exploratory][] | playground of non-official data models that explore new SDF features or new ways of using SDF. Not always conforming to current SDF validation syntax. |
| [unit_test][]   | SDF models for unit (error) testing                        |


[SDF]: https://github.com/one-data-model/SDF
[tools]: https://github.com/one-data-model/tools
[playground]: https://github.com/one-data-model/playground
[exploratory]: https://github.com/one-data-model/exploratory
[unit_test]: https://github.com/one-data-model/unit_test

[RFC8610]: https://tools.ietf.org/html/rfc8610
