# Pangeo Binder Environment

This repository provides a base image for use on Pangeo's binder. It allows
gallery authors to quickly iterate on content for Pangeo Gallery by avoiding
costly image rebuilds.

## Usage

To use this with your own binder, you need to craft a URL providing

1. The binder to run it on
2. The git repostiory with the content

See https://pangeo-binder.readthedocs.io/en/prod/ for more on how to create
links using pangeo's binder with this image. In particular, this linn generator

https://jupyterhub.github.io/nbgitpuller/link?repo=https://github.com/pangeo-gallery/default-binder&tab=binder.

Update the "BinderHub URL" to point to one of pangeo's Binder's (e.g. https://binder.pangeo.io) and
use your Git repostiory URL for the content.

For example, the following URL runs the content from
the `pangeo-gallery/example-gallery` repository at https://github.com/pangeo-gallery/example-gallery
on the binder.pangeo.io binder with the ``2020.10.10`` version of this image.

https://binder.pangeo.io/v2/gh/pangeo-gallery/default-binder/2020.10.10/?urlpath=git-pull?repo=https://github.com/pangeo-gallery/example-gallery%26amp%3Burlpath=lab/tree/example-gallery

## Pinning

We strongly recommend using a specific tagged version of the images here,
rather than just pointing to ``master``.
https://github.com/pangeo-gallery/default-binder/tags has a list of the tags.
This ensures that updates to the image don't unexpectedly break your notebooks.

## Updating versions

Suppose you've made an update to your gallery content that relies on a feature from
a new package or an updated version of the package.

If `pangeo-gallery/default-binder` already has a [tag](https://github.com/pangeo-gallery/default-binder/tags)
with the versions you need, you can just update the `binder_ref` value in your `binder-gallery.yaml`. For
example, change `binder_ref: 2020.10.10` to `binder_ref: 2020.10.27` in https://github.com/rsignell-usgs/esip-gallery/blob/aaef02335bbea0cf3ddaccf82f482a0e0af11339/binder-gallery.yaml#L8.

If there isn't a tag available yet, you can ask the pangeo-gallery maintainers to make one.
There may be a pull request from Dependabot updating the image, or we can manually trigger
an update from https://github.com/pangeo-gallery/default-binder/network/updates. To make a
release, a maintainer will push a tag.

```
git checkout master
git pull
git tag -a <date-of-image> -m "<date-of-image>"
git push upstream master --follow-tags
```

And now you can update your `binder_ref` as described above.
