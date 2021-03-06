---
published: true # change to true once ready to post

title: "Climate Change API Area Indicators" # project title inside quotes
excerpt: "A high performance Scala API for calculating climate indicators over geospatial areas" # shows on project list page

# project attributes
requirements: # bullet list of requirements – one requirement per line – follow below format
  - "Familiarity building or working with APIs"
  - "Interest and/or exerience in functional programming required (Haskell, Scala, ML, etc.)"
  - "Scala programming experience not required but preferred"
  - "Python programming experience not required but preferred"
tags: # one tag per line – spaces are allowed in tags – follow below format
  - "scala"
  - "climate change"
difficulty: "Hard" # easy, medium, hard – pick one
mentors: # github username without the @ – example: designmatty
  - "pcaisse"
  - "jisantuc"
  - "fungjj92"

# This file uses Kramdown. See https://kramdown.gettalong.org/syntax.html for syntax
---

The [Climate Change API](https://climate.azavea.com/) allows for simple location-based access to low temperature, high temperature and precipitation as well as 22 climate indicators derived from that data. It does this by preprocessing select parts of NetCDF data for individual locations, importing them into a SQL database, and performing queries on that data using an API written in Python. That approach has some limitations, so we built a proof-of-concept prototype. The prototype is written in Scala and uses [GeoTrellis](https://geotrellis.io) with a simpler ingest process to avoid needing a database, greatly reducing ingest and hosting costs, as well as allowing calculations on areas instead of just single points.

This purpose of this project is to build on that existing proof-of-concept project to complete the features needed to bring it to parity with the existing API.

## Milestones

#### Preparation

In the beginning of the project you will prepare by:

- Familiarization with the [Climate Change API](https://docs.climate.azavea.com/)
- Familiarization with the [proof-of-concept code](https://github.com/azavea/climate-backend)
- Audit the proof-of-concept for completeness in terms of features required to act as a drop-in replacement for the existing API
- Create a project roadmap

#### Project Phase 1

In this phase you will update the existing proof-of-concept to be ready for continued development:

- Refactor the prototype to use http4s instead of AkkaHTTP
- Update GeoTrellis and other dependencies
- Create a reproducible build environment using Docker
- Update the [existing ingest script](https://gist.github.com/jamesmcclain/d7301ba770477296348765a6d73feabf) to ingest more data

#### Project Phase 2

In this phase of the project, you will update the prototype code to have all the features needed for use with our climate change adaptation application, [Temperate](https://temperate.io):

 - Add support for all filter parameters
 - Add support for historical scenarios
 - Add endpoints for listing available cells, models, scenarios, indicators, and datasets

As an optional stretch-goal, depending on time, you will add the features necessary to reach full feature parity with existing API:
 - Add endpoints for accessing raw temperature and precipitation data
 - Add endpoints for accessing available regions
 - Add endpoints for accessing dataset metadata

#### Project Phase 3

In the final project phase, you'll work with the Climate Change team to create a roadmap for how your efforts will be integrated into the production API, and time permitting will work with them to follow it through. You will also document your experience in a blog post.
