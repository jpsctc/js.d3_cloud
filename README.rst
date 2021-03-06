js.d3_cloud
***********

Introduction
============

This library packages the `D3 Word Cloud Layout`_ for `fanstatic`_.

.. _`fanstatic`: http://fanstatic.org
.. _`D3 Word Cloud Layout`: https://github.com/jasondavies/d3-cloud

This requires integration between your web framework and ``fanstatic``,
and making sure that the original resources (shipped in the ``resources``
directory in ``js.d3_cloud``) are published to some URL.  As a bonus, this
library also packages up a minified version of the original JavaScript.

Packaging
=========

The packaging is stored on GitHub at
https://github.com/davidjb/js.d3_cloud. If you happen to come across a bug
that corresponds to *packaging*, then please report it here. Pull requests are
more than welcome if you're fixing something yourself -- the more help the
better!

Any other bugs that relate to the library itself should be directed to the
original developers.

Updating this package
---------------------

This process requires installation of the package for development - the
suggested method to do this is via the `Buildout` within this package::

    cd js.d3_cloud
    python boostrap.py
    ./bin/buildout

For minification of resources to succeed, you require a Java installation as
this process uses the YUI Compressor library (via the ``minify``
and``yuicompressor`` Python packages).

In order to obtain a newer version of this library, do the following::

    pushd js/d3_cloud/resources
    wget https://github.com/jasondavies/d3-cloud/raw/master/d3.layout.cloud.js -O d3.layout.cloud.js
    wget https://github.com/jasondavies/d3-cloud/raw/master/LICENSE -O LICENSE
    popd
    #Edit changelog, setup.py for versions, etc
    python setup.py minify_d3_cloud
    git commit -a -m "Updated for release 1.0.1"
    git push

If you're doing this out in your own fork of the GitHub repository, then
send through a pull request so everyone can benefit.
