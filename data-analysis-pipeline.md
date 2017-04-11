# Analysis pipelines
Other names: analysis workflow, recipe, protocol

## Context
An analysis consists of several analysis steps, which need to be executed in a certain order to produce the final result. Each step consumes input data (files, parameters...) and produces output artifacts (files, debug messages...). A processing step can be implemented in any programming language, using whatever tools are needed to get that particular job done. Often an analysis will use a range of different tools to produce the final paper from the input raw data.

The logic and dependencies of how the individual computing steps are combined into a complete analysis is called an *analysis pipeline*. In most practical analyses the pipeline will be described by a direct acyclic graph.

## Problem
How do you automate the execution of all analysis steps in the right order?
If you need to rerun the analysis after a change was made, how do you make sure only the minimum amount of work is done to update the result?

## Solution
A large number of tools exist to specify and automatically execute analysis pipelines. An extensive list of examples is available at the [awesome pipeline repo](https://github.com/pditommaso/awesome-pipeline)

An analysis pipeline tool usually consists of a workflow specification language and an executor. The specification language is used to describe the pipeline in machine (and human) readable form. The executor interpets the pipeline specification, builds a dependency tree and executes the pipeline.

`GNU make` is probably the most used pipeline tool. It is tailored to software build pipelines (but can be appropriated for analysis workflows as well). 

Here we collect a set of essential features of pipeline tools:
* Human and machine readable description of analysis pipeline
* Scripting or wildcards to handle multiple inputs/outputs
* Evaluate dependencies in the pipeline graph
* Allow caching of intermediate results and incremental updating of the pipeline
* Analysis code is agnostic of pipeline tool. Pipeline works as a scaffolding to execute the analysis code in the right order.
* Support for parallel computing architectures (automatic parallelization of pipeline tasks)


## Related patterns
* [Annotated analysis pipelines](annotated-pipelines.md)
* [Caching of intermediate results](caching-intermediate-results.md)
* [Dependency management](dependencies-in-analysis-pipelines.md)


## Examples

