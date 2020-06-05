---
layout: default
title: OneDM Overview
overview: true
---

# Under construction — straw man text

The goal of oneDm is to standardize the data models so that conversions of models between instances of devices of the various organisations is not needed. 
There is just a single model selected/created of the participating organisations that everyone can adopt.

However that is the end goal, to achieve that goal the first step to take is how to write down a model. Since all participating organizations are doing this currently differently, it makes sense to have a single way to describe models. Hence Semantic Definition Format (SDF) is created. The definition format syntax is described in the SDF repository.
SDF is JSON formatting of the models. Using JSON as language has a few
advantages:

- The content is machine readable
- Various qualifiers already are in existence in JSON schema.
- The files can be validated by a schema validator. 
- Abundant of tools and libraries are available on the internet to produce/consume JSON, so tooling can be created to use the SDF models.

To make sure that SDF is up to the task to convey the different models that are currently in use the playground repository has been created.
The playground repo contains contributed models of various organisations in SDF format. 
These models are most of the time automatically generated from the source materials of the participating organisations. 
Most of the participating organisations have created tooling to convert their models to and from SDF. 
Hence full round tripping is available to verify if the SDF syntax can convey all the needed information. 
The playground repository has an CI system in place to verify pull request on syntax. Hence all models in the playground are valid SDF files.

Next steps for oneDM (conducted in parallel):

- Standardize the Semantic Definition Format (SDF) in IETF. 
- Selecting models in the playground to for oneDM
- Improve SDF so that more complex models can be created.


Repository overview

| repo name          |  Description                                                         |
|--------------------|----------------------------------------------------------------------|
| SDF                | Semantic Definition Format (SDF) for Data and Interactions of Things |
| tools              | SDF tools                                                            |
| playground         | playground of non-official oneDM data models, correct SDF syntax     |
| exploratory        | Link to text or embedded text containing license terms               |
| unit_test          | repo with SDF models for (error) testing                             |
