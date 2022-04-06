# Roadmap

Our aim is to create a reliable, free, machine-actionable data collection of apparent equilibrium constants of enzyme-catalyzed reactions, with a clear change process to integrate new data and correct errors.

This document collects on-going work, ideas for future work, and invites for contributions. Any feedback? Send an email or open an Issue!

Do you want to contribute? We are happy to get in touch via opentecr@googlegroups.com!



# Table of Content

- [On-going work](#on-going-work)
  * [Community facilitation](#community-facilitation)
  * [Curation of data](#curation-of-data)
    + [Curation - TECR-DB](#curation---tecr-db)
    + [Curation - literature from 2007 to 2021](#curation---literature-from-2007-to-2021)
  * [Literature identification & storage](#-literature-identification---storage)
  * [Outreach](#outreach)
  * [Persistent Identifiers](#persistent-identifiers)
  * [Schema](#schema)
- [Proposals for future work](#proposals-for-future-work)
  * [Graphical User Interface / Website](#graphical-user-interface---website)
  * [Python package](#python-package)
  * [Sanity checks / Quality Control](#sanity-checks---quality-control)


# On-going work

## Community facilitation

* catch up with the community regularly through the Google Groups (https://groups.google.com/g/opentecr)
* find out needs of community members
* welcome new community members individually
* organize community convenings
* care for the roadmap

_working on this_: [@rgiessmann](https://github.com/rgiessmann)


## Curation of data

* storage in github (https://github.com/opentecr/opentecr-data)
* adheres to schema (see below)


### Curation - TECR-DB

* TECR-DB is the legacy data source from NIST
* clarify copyright situation with NIST
* release the data under an open license if possible
* massage the data:
  * transforming to openTECR schema
  * cleaning up errors, e.g. duplicates, nonsense reactions, ...
  * annotate literature references with DOI, PMID, title of the paper, ...
  * map the reactions to Rhea reactions (https://www.rhea-db.org/)
  * check with and archive the primary literature
* partial overlap with [Literature identification & storage](#-literature-identification---storage)

_working on this_: [@FreiburgerMSU](https://github.com/FreiburgerMSU) , [@rgiessmann](https://github.com/rgiessmann)


### Curation - literature from 2007 to 2021

* extract equilibrium constants, experimental conditions, etc. from provided literature references
* create corresponding json files in a separate branch on https://github.com/opentecr/opentecr-data
* literature list available under: https://github.com/roberts-farm-of-ideas/8/blob/main/materials/pubmed%20opentecr%20review/pubmed%20search%20results%20evaluated.ods

_working on this_: [@rgiessmann](https://github.com/rgiessmann)


## Literature identification & storage

* for more details, see [the specific document](./roadmap/literature_identification_and_storage.md)
* archive primary literature on Zenodo with restricted access (due to potential copyright infringement if access would not be restricted)
  * 1054 PDF files, named according to the Goldberg shorthand keys (e.g. 26QUA_WOO) are available at: https://doi.org/10.5281/zenodo.5776216 -- you need to request access to those files via Zenodo with your email address; access will be granted to you based on German copyright law
* identify just-published primary literature containing equilibrium measurements
  * already set-up: check a weekly PubMed notification
* grade literature based on title and abstract, respectively, and after curation (aim: create a predictive model of "curation worthiness")

_working on this_: [@rgiessmann](https://github.com/rgiessmann)


## Outreach

* speaking about the group on conferences, talks, ...
  * slides e.g. here: [1](https://doi.org/10.5281/zenodo.5355130), [2](https://doi.org/10.5281/zenodo.5566376)

_working on this_: ...


## Persistent Identifiers

* we want to provide persistent identifiers for our data elements, so we can speak about them and have them machine-actionable, too
* for this we use w3id.org identifiers
* w3id.org identifiers have to be "minted" by creating pull requests to https://github.com/perma-id/w3id.org
  * discussion is on-hold whether each individual identifier shall be submitted to w3id.org: see https://github.com/perma-id/w3id.org/pull/2314

_working on this_: [@rgiessmann](https://github.com/rgiessmann)


## Schema

schema repository: https://github.com/opentecr/opentecr-schema

* source requirements from the community
* define a data model and corresponding schema for data entry / storage
* provide means to confirm the adherence of data files to the schema

_working on this_: [@midnighter](https://github.com/midnighter), [@rgiessmann](https://github.com/rgiessmann)


# Proposals for future work

## Graphical User Interface / Website

* source requirements from the community
* build a web backend (likely needed) and a front-end to fulfill the requirements (e.g. search for compounds, search for reactions, filter according to experimental conditions, ...)


## Python package

* source requirements from the community
* build a Python module to fulfill the requirements (e.g. search the data for compounds, transformation of data into other formats, ...)


## Sanity checks / Quality Control

* implement an automated calculation / prediction of atom mapping -- see whether the prediction appears highly non-sensible, and thus likely an error exists in the InChIs
* check whether publication data (authors, title, ...) is in-sync with our source-of-truth (unclear what exactly our source-of-truth is: PubMed? DataCite?)
