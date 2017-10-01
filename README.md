widdly [![License](http://img.shields.io/:license-gpl3-blue.svg)](http://www.gnu.org/licenses/gpl-3.0.html) [![Build Status](https://travis-ci.org/opennota/widdly.png?branch=master)](https://travis-ci.org/opennota/widdly)
======

This is a minimal self-hosted app, written in Go, that can serve as a backend
for a personal [TiddlyWiki](http://tiddlywiki.com/).

## Requirements

Go 1.7+

## Installation

    go get -u github.com/opennota/widdly

## Usage

Put `index.html` next to the executable (or, alternatively, embed `index.html`
into the executable by running `zip -9 - index.html | cat >> widdly`). Run:

    widdly -http :1337 -p letmein -db /path/to/the/database

- `-http :1337` - listen on port 1337 (by default port 8080 on localhost)
- `-p letmein` - protect by the password (optional); the username will be `widdly`.
- `-db /path/to/the/database` - explicitly specify which file to use for the
  database (by default `widdly.db` in the current directory)

## Build your own index.html

    git clone https://github.com/Jermolene/TiddlyWiki5
    cd TiddlyWiki5
    node tiddlywiki.js editions/empty --build index

Open `editions/empty/output/index.html` in a browser and install some plugins
(at the very least, the "TiddlyWeb and TiddlySpace components" plugin). You
will be prompted to save the updated index.html.

## Similar projects

For a Google App Engine TiddlyWiki server, look at [rsc/tiddly](https://github.com/rsc/tiddly).
