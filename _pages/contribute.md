---
layout: single
title: Contribute to OneDM
overview: true
permalink: /contribute/

sidebar:
  nav: "about_nav"

toc: true
toc_label: Table of Contents
toc_icon: cog
toc_sticky : true
---

## Contribute to SDF as description format

Since Data modeling will progress, SDF as a format will have new versions.
To drive new features in the description format the [exploratory][] repo has been created.
This repo can be used to describe SDF models with new features.
The models will not pass validation intentionally, since the models describe new syntax features that are not yet part of the SDF syntax.

If the proposed syntax is accepted by the group, then the following actions needs to happen:

- Pull request on the validation tooling, adaption needs to verify the proposed feature.
- Pull request on the SDF language, pull request should describe the new feature
- Pull request to the [unit_test][] repo, having a few error test cases to verify the validation tooling.
- Tag the repositories to indicate the new used SDF version.

After the tagging:

- Move the example from the [exploratory][] to the [playground][] repo.

## Contribute Models

To make sure that SDF is up to the task to convey the different models
that are currently in use, the [playground][] repository has been
created, with models contributed by various organizations in SDF format.
Many of these models are automatically generated from the source materials of the participating organizations.
Most of the participating organizations have created tooling that supports converting their models to and from SDF.
Full round tripping is available to verify if the SDF syntax can convey all the needed information.
The [playground][], [exploratory][], and [unit_test][] repositories have a CI system in place that analyzes
pull requests and provides reports with respect to their syntax usage.
The aim is that all models in the
[playground][] are syntactically valid SDF files, while the other
repositories tolerate (or deliberately contain) deviations.

The process is captured in the following diagram:
![process flow](/assets/images/process.png "process")

### Selection process

The creation of the selection process is work in progress.
Already a preliminary investigation has been done by the various contributing organizations regarding the possible overlap of models.
The currently available models are in the [playground][]. These models are not yet final and needs feature alignment.
For example OCF range and LWM2M Min_Range_Value/Max_Range_Value are conveying the same information on the wire.
This kind of discrepancies needs to be solved.

What needs to be agreed before the actual down selection of models can take place:

- Establish a set of common tag names of a feature.
    Note that this are NOT qualities, this set of tag names is about how to use SDF consistently.

## Repository overview

| repo name       | Description                                                          |
|-----------------|----------------------------------------------------------------------|
| [playground][]  | playground of non-official data models that could be OneDM data models, but aren't yet. Correct SDF syntax.  |
| [exploratory][] | playground of non-official data models that explore new SDF features or new ways of using SDF. Not always conforming to current SDF validation syntax. |
| [unit_test][] | playground of test models to verify the SDF language. |

---

OneDM <sup>tm</sup>

![logo tm]("assets/images/onedm-tm.png")


[SDF]: https://github.com/one-data-model/SDF
[tools]: https://github.com/one-data-model/tools
[playground]: https://github.com/one-data-model/playground
[exploratory]: https://github.com/one-data-model/exploratory
[unit_test]: https://github.com/one-data-model/unit_test

[SDF language]: https://onedm.org/SDF/sdf.html

[IETF108]: https://github.com/one-data-model/ietf108

[RFC8610]: https://tools.ietf.org/html/rfc8610
