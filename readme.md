# OpenLayers 3

[![Travis CI Status](https://secure.travis-ci.org/openlayers/ol3.png)](http://travis-ci.org/#!/openlayers/ol3)


## Hosted Examples

The examples are hosted on GitHub (as GitHub pages). See http://openlayers.github.com/ol3/master/examples/.

## Build OpenLayers 3

Run build.py:

    $ ./build.py

Windows users should run `build` instead.

## Run examples locally

Run the [Plovr](http://plovr.com/) web server with:

    $ ./build.py serve

Windows users should run `build serve` instead.

Then, either open one of the example html files from the `examples` directory directly in your browser, or start a simple webserver, for example:

    $ python -mSimpleHTTPServer

and explore the `examples/` directory, for example by opening
<http://localhost:8000/examples/side-by-side.html>.

You can turn off compilation by appending `?mode=RAW` to the URL, for example
<http://localhost:8000/examples/side-by-side.html?mode=RAW>.

## Run tests

Run the plovr web server (see above), and either open the `test/ol.html` file
in the browser (e.g. <http://localhost:8000/test/ol.html>), or run `./build.py test`
on the console (headless testing with PhantomJS, make sure to install it first from http://phantomjs.org/download.html).

See also the test-specific [readme](https://github.com/openlayers/ol3/tree/master/test).

## Run the linter

First, install the [Closure
Linter](https://developers.google.com/closure/utilities/docs/linter_howto).
Then:

    $ ./build.py lint

## Run the precommit hook before pushing a commit:

    $ ./build.py precommit

## Add examples

The examples are located in the `examples` directory. Adding a new example
implies creating two files in this directory, a `.html` file and `.js` file.
See `examples/full-screen.html` and `examples/full-screen.js` for instance.

The `.html` file needs to include a script tag with
`loader.js?id=<example_name>` as its `src`. For example, if the two files for
the examples are `myexample.js` and `myexample.html` then `id` should be set to
`myexample` in the `loader.js` URL.

`build.py serve` should be stopped and restarted for the
`loader.js?id=<example_name>` script tag to refer to a valid URL. `build.py serve`
triggers the `examples` target which creates Plovr JSON file for each example.
