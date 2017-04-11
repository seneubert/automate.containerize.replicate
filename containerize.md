# Containerize

## Context
In order to be able to rerun an analysis the complete runtime environment on top of which the analysis was built needs to be preserved.
This includes the operating system and all software packages in their right versions.

## Problem
How do you encapuslate setting up the runtime environment, such that it can be executed on any given computing infrastructure?

## Solution
Linux containers. For example [Docker](https://www.docker.com/what-docker).

## Related Patterns
* [Continuous analysis](continuous-analysis.md)
