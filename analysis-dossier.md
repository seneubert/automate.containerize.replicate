# Analysis dossier
## Context
Once an analysis can be run automatically by using an [analysis pipeline](data-analysis-pipeline.md) it becomes easy to generate results like plots, tables etc in large numbers. Furthermore the results can of course change after a change was made to the analysis code, the pipeline or the input data. Your results are tied to the version of the analysis they were produced with.

## Problem
How do you keep track of the versions of results that your pipeline is producing?

The obvious solution is to store the results in a repository and the immediate candidate is to store them in the same repository as the code. But this idea leads to several problems.
* If an analysis runs a [continuous integration service](continuous-analysis.md), checking in the results of a certain version will trigger another CI build. There are tricks to suppress this behaviour. But those tricks usually lead to an undefined status of the CI, which breaks a lot of the benefits of CI.
* The analysis results contain sensitive information, which often should not be released to the public until the analysts are satisfied with the quality of their work, the results are approved by their collaborators and any copyright issues with publishers have been cleared. On the contrary it might be desireable to be able to develop the analysis code in the open to enable diverse contributions and ideas. A separation of analysis code and analysis results helps managing these conflicting interests.

## Solution
Analysis results are commited to a separate repository, which we call *analysis dossier*.

## Related patterns
* [Code repository](code-repository.md)
* [Analysis pipeline](data-analysis-pipeline.md) 
* [Continuous interation](continuous-analysis.md)
* [Data provenance](data-provenance.md)
* [Data provenance links](data-provenance-links.md)

