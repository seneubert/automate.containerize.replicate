# Data provenance links

## Context
The final artifacts produced by an analysis pipeline, like plots and tables, will leave the controlled environment of the workflow and end up in presentations or documents.

## Problem
How can we trace back how an artifact was created?

## Solution

Use exif to add meta information to plots. Exif meta can contain links to the version (ref) of the code that was used to produce this version of the plot

## Related patterns
* [Analysis dossier](analysis-dossier.md)
* [Continuous analysis](continuous-analysis.md)


## Example code
`exiv2` and `exiftool` can be used to add information to `png` or `pdf` files.

```
exiv2 -M "set Exif.Photo.UserComment charset=Ascii "<my comment>" myfile.png"
exiftool -PDF:keywords+="<my comment>" myfile.pdf"
```

The comment can be used to attach a link to the version of the repository that has created the plot.

On gitlab-ci there are several variables available which can be used. For example:
```
exiv2 -M "set Exif.Photo.UserComment charset=Ascii "Created from  $CI_PROJECT_URL/commit/$CI_BUILD_REF" *.png 
```
For a complete list of variables see [here](https://docs.gitlab.com/ce/ci/variables/).

To display the information do:
```
exiv2 pr myfile.png
exiftool myfile.pdf
exiftool myfile.png # also works
```
