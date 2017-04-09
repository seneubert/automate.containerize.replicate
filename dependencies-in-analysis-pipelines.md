# Dependency management in analysis pipelines

## Context
Most pipeline tools use timestamps of input and output files for dependency management (like make)

## Problem
On a cloud infrastructure (e.g. CI-server) code might be checked out fresh for each run and file timestamps might not coincide with date of last modification.

## Solution
Check repository for time of last modification

Careful: not straight forward if there are several forks.


## Related patterns
