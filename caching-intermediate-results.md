# Caching intermediate results

## Context
Analysis steps can involve expensive calculations. Even when the resources available on a single workstation are sufficient to perfom an analysis task in many cases it is desireable to limit recomputation of already available results to the absolut necesary. Handling the dependency graph accordingly is the main responsibility of an [analysis pipeline](data-analysis-pipeline.md) tool.

In order to allow the pipeline tool to evaluate which parts of the pipeline have to be recaculated after a change (to the code, parameters or input data) the intermediate results of all processing steps need to be cached.

On a local machine this is usually trivial. The analysis artifacts will be written to the local working directory or to a user specified folder on a shared filesystem.

## Problem
When the analysis is (re)run on a [containerized](containerize.md) system care has to be taken to provide a valid caching directory. The problem is particularily important for [continuous integration](continuous-analysis.md) systems where are rapid turn around is essential.
 
## Solution

Explicitely provide well defined caching volumes. Take care when there are [several users](multiple-developers-and-ci.md) using the same continuous integration server.

## Related patterns
* [Analysis pipelines](data-analysis-pipeline.md)
* [Expensive processing steps](expensive-processing-steps.md)
* [Continuous analysis](continuous-analysis.md)
* [Multiple CI users](multiple-developers-and-ci.md)
