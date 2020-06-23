---
layout: single
title: Terminology
overview: true
permalink: /terminology/

sidebar:
  nav: "sdf_nav"

toc: true
toc_label: "Table of Contents"
toc_icon: "cog"
toc_sticky : true
---
# Terminology

| SDF Definition | [OMA IPSO/LwM2M][lwm2m-spec]      |  [Open Connectivity Foundation (OCF)][ocf-spec]|
| -------------  | ------------------- |------------------- |
| sdfThing       | LwM2M device        |    OCF Device  |
| sdfObject      | Object              |    OCF Resource    |
| sdfAction      | Resource            |    OCF Resource |
| sdfEvent       | (SEND interface?)   |    response of Observe   |
| sdfProperty    | Resource            |    JSON property   |
| sdfData        |         |     reusable definitions at #/definitions |
| sdfProduct        |         |    N/A   |

## Qualities

| Quality       | Description                                                             | OMA IPSO/LwM2M      | OCF [OpenAPI][oas]   |
| ------------- | ----------------------------------------------------------------------- | ------------------- | -------------------- |
| label          | human readable name                                                     | Name                | n (as JSON property) |
| description   | human readable description                                              | Description         | description          |
| title         | human readable title to display                                         | Name                | title                |
| $comment      | explanatory comments                                                    | XML comments        | N/A                  |
| sdfRequired   | Array of JSON Pointers to mandatory items in a valid definition         | Optional            | required             |
| sdfRef        | reference to a definition to be used as a template for a new definition | Re-usable resources | $ref                 |
| readable      | Reads are allowed                                                       | Operations: R       | readOnly, Note 1     |
| writable      | Writes are allowed                                                      | Operations: W       | readOnly, Note 1     |
| observable    | flag to indicate asynchronous notification is available                 | (always)            | (always)             |
| contentFormat | IANA media type string                                                  | text/raw/SenML      | N/A                  |
| subtype       | subtype enumeration                                                     | (Part of) Type      | N/A                  |

| units         | SenML unit code                                                         | Units               | N/A                  |
| nullable      | indicates a null value is available for this type                       | true                | N/A                  |
| scaleMinimum  | lower limit of value in units                                           | N/A                 | N/A                  |
| scaleMaximum  | upper limit of value in units                                           | N/A                 | N/A                  |
| type          | JSON data type                                                          | Type                | identical            |
| minimum       | lower limit of value in the representation format                       | RangeEnumeration    | identical, Note 2    |
| maximum       | upper limit of value in the representation format                       | RangeEnumeration    | identical, Note 2    |
| multipleOf    | indicates the resolution of the number in representation format         | N/A                 |  step, Note 2        |
| enum          | enumeration constraint                                                  | TBD: Enumeration    | identical            |
| pattern       | regular expression to constrain a string pattern                        | N/A                 | identical            |
| format        | JSON Schema formats                                                     | N/A                 | identical            |
| minLength     | shortest length string in octets                                        | RangeEnumeration    | identical            |
| maxLength     | longest length string in octets                                         | RangeEnumeration    | identical            |
| default       | specifies the default value for initialization                          | N/A                 | identical            |
| const         | specifies a constant value for a data item or property                  | N/A                 | enum with single value |

OCF is using [Open API Specification 2.0][oas] as data model mechanism.

Note 1: OpenAPI specification has different sections in the modeling lanuage which can be used to make readable and writable explicit.
When a resource can be updated and is using a single schema for the payloads then the readOnly means that that property should not occur in the update payload.

Note 2: For data definitions the JSON schema constructs are used.
However, each implementation can be further restricted by using range and step properties.

[lwm2m-spec]: http://www.openmobilealliance.org/release/LightweightM2M/V1_1_1-20190617-A/HTML-Version/OMA-TS-LightweightM2M_Core-V1_1_1-20190617-A.html
[ocf-spec]: https://openconnectivity.org/developer/specifications/
[oas]: https://github.com/OAI/OpenAPI-Specification/blob/master/versions/2.0.md
