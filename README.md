# Pangeo Binder Environment

This repository provides a base image for use on Pangeo's binder. It allows
gallery authors to quickly iterate on content for Pangeo Gallery by avoiding
costly image rebuilds.

## Usage

To use this with your own binder, you need to craft a URL providing

1. The binder to run it on
2. The git repostiory with the content

See https://pangeo-binder.readthedocs.io/en/prod/ for more on how to create
links using pangeo's binder with this image. In particular, use the "Binder" tab
on https://jupyterhub.github.io/nbgitpuller/link.html to generate the links.

For example, the following URL runs the content from
the `pangeo-gallery/example-gallery` repository at https://github.com/pangeo-gallery/example-gallery
on the binder.pangeo.io binder with the ``2020.10.10`` version of this image.

https://binder.pangeo.io/v2/gh/pangeo-gallery/default-binder/2020.10.10/?urlpath=git-pull?repo=https://github.com/pangeo-gallery/example-gallery%26amp%3Burlpath=lab/tree/example-gallery

## Releasing

We strongly recommend using a specific tagged version of the images here,
rather than just pointing to ``master``.
https://github.com/pangeo-gallery/default-binder/tags has a list of the tags.
This ensures that updates to the image don't unexpectedly break your notebooks.

