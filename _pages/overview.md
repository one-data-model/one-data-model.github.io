---
layout: single
title: Overview
overview: true
permalink: /overview/

toc: true
toc_label: "Table of Contents"
toc_icon: "cog"
toc_sticky : true
---

## One Data Model overview

The One Data Model (OneDM) group is established to solve one of the main remaining interoperability issues in IoT: incompatible data and interaction models. 

## History

OneDM emerged from Zigbee "Hive" meeting, fall 2018.
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
- Create a common representation language for existing IoT data and interaction models.
- Enable contribution of the best existing models across all participating organizations.
- Collect a set of representative models for a "pressure test" of the language.
- Convert to the new language and note any gaps.
- Organizations contribute models for evaluation.
- Process for selecting a single model per function, e.g. lighting, door lock, thermostat.
- Publication of selected models.

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

## The benefits


OneDM SDF will make it easy for device vendors and SDOs to adopt a common language and definition format.
If OneDM get descriptions of devices in a consistent format from diverse SDOs and vendors, the industry can more easily create adapter code and UI elements.
Device vendors will begin to re-use the definitions of affordances that already exist rather than create new ones.
If the devices from diverse organizations have affordances that work in similar ways, we only need to adapt protocols and can re-use the UI elements.
Existing rules, scenes, and behaviors will work correctly with new devices from a different SDO or vendor.
When the interaction affordances are standardized, 
the customer experience will be improved as well-known and popular ways of interacting with device affordances emerge.
Open source tools for OneDM and SDF will emerge as more people adopt OneDM.

- Normalized device description to make it easy to create the adapter and driver code to integrate new devices.
- Normalization of device models result in common platform code for rules, scenes, etc.
- Normalization of the data and interaction models for improved customer experience.
- Ultimate convergence of protocols, fewer adapter codes needed.

## The description format

To achieve that goal the first step to take is to have a common way how to write down a model.
Since all participating organizations are currently doing this
in their own ways, it makes sense to develop a single way to describe models.
Hence, the Semantic Definition Format (SDF) is created.
The syntax and semantics of the SDF format are described in the [SDF][] repository.
The easy readable version [SDF language][].

To track the updates in the IETF version see the [IETF draft of SDF](https://www.ietf.org/id/draft-onedm-t2trg-sdf-00.html).

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
Hence, full round tripping is available to verify if the SDF syntax can convey all the needed information.
The [playground][], [exploratory][], and [unit_test][] repositories have a CI system in place that analyzes
pull requests and provides reports with respect to their syntax usage.
The aim is that all models in the
[playground][] are syntactically valid SDF files, while the other
repositories tolerate (or deliberately contain) deviations.

Next steps for OneDM (conducted in parallel):

- Standardize the Semantic Definition Format (SDF) in IETF
- Select models in the playground to for OneDM
- Further develop SDF so that more complex models can be created

## converted Models per organisation

| repo name       | Converted  | Description                                             |
|-----------------|-----------|---------------------------------------------------------|
| [OCF][]         | OCF   |  OCF converted models in SDF format |
| [OMA][]         | OMA | OMA converted models in SDF format    |

## Repository overview

| repo name       | Type      | Description                                             |
|-----------------|-----------|---------------------------------------------------------|
| [SDF][]         | Language   |  Semantic Definition Format (SDF) for Data and Interactions of Things |
| [ASDF][]        | Language work group | Information for the standardization work for IETF ASDF workgroup     |
| [IETF108][]     | Language   | Information for the standardization work for IETF meeting 108        |
| [tools][]       | Language   | SDF tools                                                            |
| [playground][]  | Data Models | Playground of non-official data models that could be OneDM data models, but aren't yet. Correct SDF syntax.  |
| [exploratory][] | Data Models | Playground of non-official data models that explore new SDF features or new ways of using SDF. Not always conforming to current SDF validation syntax. |
| [unit_test][]   | Data Models | SDF models for unit (error) testing                        |


[OCF]: https://github.com/one-data-model/ocf-models
[OMA]: https://github.com/one-data-model/oma-models

[SDF]: https://github.com/one-data-model/SDF
[tools]: https://github.com/one-data-model/tools
[playground]: https://github.com/one-data-model/playground
[exploratory]: https://github.com/one-data-model/exploratory
[unit_test]: https://github.com/one-data-model/unit_test

[SDF language]: https://github.com/ietf-wg-asdf/SDF
[IETF SDF]: https://datatracker.ietf.org/doc/draft-ietf-asdf-sdf/
[ASDF]: https://datatracker.ietf.org/wg/asdf/about/
[IETF editors version of SDF]: https://github.com/ietf-wg-asdf/SDF

[IETF108]: https://github.com/one-data-model/ietf108

[RFC8610]: https://tools.ietf.org/html/rfc8610
