---
layout: single
title: Overview
overview: true
permalink: /overview/

toc: true
toc_label: "Table of Contents"
toc_icon: "cog"
---

## One Data Model overview

One Data model group is established to solve interoperability issues.
The most prominent issue with IOT is that all devices are using different semantic models for 

## History 

One DM emerged from Zigbee "Hive" meeting, fall 2018.
In this meeting a cross-industry consensus on lack of common IoT data models was identified.
Not having industry alignment is a key inhibitor to IoT growth.
Therefore, a broad industry group of SDO's and vendors wanted to cooperate to solve this issue.
The idea was not to create another legal organization, but cooperation under a liaison.
The work started with having weekly teleconferences, 4 face to face meetings, in 2019.
The work load contained creating convergence on Language, tools and models.

The goal of OneDM is to arrive at a common set of data and interaction
models that describe IoT devices.
This will enable an application to work with IoT devices from
different ecosystems, without a need for converting data and interactions from the
model of one organization to that of the other.
Ideally, for every class of IoT device, there is just a single model
selected/created by the participating organizations, which everyone can adopt.

## The Charter

The One Data Model Liaison Group will define a single application data model to support a common language for the Internet of Things. The group will define a meta-model language and a single consistent data model to describe the Internet of Things. The data model will serve multiple interaction models among devices, applications and services interacting with and communicating about the Internet of Things. To expedite time to market and wide adoption, the One Data Model will be generated based on data models contributed by participating organizations and companies which the group will select, combine, edit and enhance, in consultation with the broader ecosystem. The group will make the One Data Model available under an open source license that can be easily adopted by multiple organizations, companies, industries and ecosystems.
 
## Process

The process established was:
Create a common representation language for existing IoT data and interaction models.
Enable contribution of the best existing models across all participating organizations.
Collect a set of representative models for a "pressure test" of the language.
Convert to the new language and note any gaps.
Organizations contribute models for evaluation.
Process for selecting a single model per function, e.g. lighting, door lock, thermostat
Publication of selected models.

During this process it was identified that not too much overlap of models by various organizations.
A rough indication of the strengths of the data models is listed below:

| Category            | SDO                      |
|---------------------|--------------------------|
| Appliances          | OCF                      |
| Electronics         | TBD                      |
| Energy              | Zigbee                   |
| Healthcare          | TBD                      |
| HVAC                | TBD                      |
| Industrial Sensors  | OMA                      |
| Lighting            | Bluetooth SIG/ZigBee/OCF |
| Security            | Z-Wave                   |
| Sensors             | Bluetooth SIG/ZigBee     |

## The description format

To achieve that goal the first step to take is to have a common way how to write down a model.
Since all participating organizations are currently doing this
in their own ways, it makes sense to develop a single way to describe models.
Hence, the Semantic Definition Format (SDF) is created.
The syntax and semantics of the SDF format are described in the [SDF][] repository.
The link to the [IETF editors version of SDF][https://www.ietf.org/id/draft-onedm-t2trg-sdf-00.html].

SDF is representing the models in JSON.
Using JSON as a representation language has a few advantages:

- The content is machine-readable, without the need to construct
  special parsers.
- The syntax of the SDF files can be validated by a validator for one
  of these data description languages.  SDF 1.0 uses both CDDL
  ([RFC8610][]) and the formats proposed at json-schema.org for this.
- The structure of the data themselves can be modelled in similar
  ways; SDF 1.0 borrows specific elements of the json-schema.org
  proposals for this.
- Abundant tools and libraries are available to produce/consume JSON,
  so tooling to work with SDF models can be created efficiently.

## Validation of the description format

To make sure that SDF is up to the task to convey the different models
that are currently in use, the [playground][] repository has been
created, with models contributed by various organizations in SDF format.
Many of these models are automatically generated from the source materials of the participating organizations.
Most of the participating organizations have created tooling that supports converting their models to and from SDF.
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

| repo name       | Type      | Description                                             |
|-----------------|-----------|---------------------------------------------------------|
| [SDF][]         | Language   |  Semantic Definition Format (SDF) for Data and Interactions of Things |
| [IETF108][]     | Language   | Information for the standardization work for IETF meeting 108        |
| [tools][]       | Language   | SDF tools                                                            |
| [playground][]  | Data Models | Playground of non-official data models that could be OneDM data models, but aren't yet. Correct SDF syntax.  |
| [exploratory][] | Data Models | Playground of non-official data models that explore new SDF features or new ways of using SDF. Not always conforming to current SDF validation syntax. |
| [unit_test][]   | Data Models | SDF models for unit (error) testing                        |

[SDF]: https://github.com/one-data-model/SDF
[tools]: https://github.com/one-data-model/tools
[playground]: https://github.com/one-data-model/playground
[exploratory]: https://github.com/one-data-model/exploratory
[unit_test]: https://github.com/one-data-model/unit_test

[IETF108]: https://github.com/one-data-model/ietf108

[RFC8610]: https://tools.ietf.org/html/rfc8610
