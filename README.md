# Pangeo Binder Environment

This repository provides a base image for use on Pangeo's binder. It allows
gallery authors to quickly iterate on content for Pangeo Gallery by avoiding
costly image rebuilds.

## Usage

To use this with your own binder, you need to craft a URL providing

1. The binder to run it on
2. The git repostiory with the content

For example, the following URL runs the content from
the `pangeo-gallery/example-gallery` repository at https://github.com/pangeo-gallery/example-gallery
on the binder.pangeo.io binder.

https://binder.pangeo.io/v2/gh/pangeo-gallery/default-binder/master/?urlpath=git-pull?repo=https://github.com/pangeo-gallery/example-gallery%26amp%3Burlpath=lab/tree/example-gallery

## Version

For reproducible builds, specify the version of `pangeo-gallery/default-binder`
in the URL: `pangeo-gallery/default-binder/2020.03.27/`. The versions here
mirror the versions of [pangeo-notebook](https://anaconda.org/conda-forge/pangeo-notebook/).
