---
layout: single
title: Data model usage
overview: true
permalink: /usage/

toc: true
toc_label: Table of Contents
toc_icon: cog
toc_sticky : true
---

## IPSO


## OCF

OCF defines resources in Open API specification format.
This is a rest full description of resource.
It describes per URI which methods are possible and which payloads are used for request and responses.
This information is machine-readable (using the JSON variant of OAS2.0) and thus can be used to convert to SDF,
also the tooling can convert from SDF [playground][] to OAS2.0.
The [OCF SDFtooling][] publicly available.

### Involved Repositories of OCF SDF conversion

| repo name          | Description                                                          |
|--------------------|----------------------------------------------------------------------|
| [OCF SDFtooling][] | conversion tooling between OAS2.0 and SDF |
| [OAS2.0 files][]   | Information for the standardization work for IETF meeting 108        |
| [playground][]     | OneDM Playground         |

[OCF SDFtooling]: https://github.com/openconnectivityfoundation/SDFtooling
[OAS2.0 files]: https://github.com/openconnectivityfoundation/IoTDataModels
[playground]: https://github.com/one-data-model/playground
