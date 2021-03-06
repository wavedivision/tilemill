---
layout: docs
section: help
category: reference
tag: Reference
title: Files & directories
permalink: /docs/manual/files-directories
---
By default TileMill manages project files, data and exports in a `MapBox` directory in your user's Documents directory. TileMill will create this directory and its contents automatically when you first start the program. Below are the default full paths for this directory; the actual locations may be different depending on your languages settings or other system configuration.

- **Mac OS X:** `/Users/<user>/Documents/MapBox`
- **Ubuntu & other Linux:** `/home/<user>/Documents/MapBox`
- **Windows:** `C:\Documents and Settings\<user>\My Documents\MapBox`

## Directory overview

The layout of the `MapBox` directory is as follows:

    MapBox/
      cache/
      data/
      export/
      project/
      app.db

The **cache** directory contains a local copy of any remote datasources you add to your projects. For example, if you add the [http://mapbox-geodata.s3.amazonaws.com/natural-earth-1.3.0/physical/10m-rivers-north-america.zip](http://mapbox-geodata.s3.amazonaws.com/natural-earth-1.3.0/physical/10m-rivers-north-america.zip) shapefile to one of your projects, it will be saved to the cache directory and symlinked into your project's layers directory:

    MapBox/cache/5316a7a8-10m-rivers-north-america

The **data** directory is where you should place any data files you would like to use on your maps. When adding or editing a layer you will be able to use this directory in the file browser.

The **export** directory contains any export files generated by TileMill.

The **project** directory contains projects accessible by TileMill.

## Structure of a TileMill project

A TileMill project is not a single file, but a directory containing a project/layers description file (`project.mml`), one or more CartoCSS stylesheets (default: `style.mss`), and a subdirectory (`layers`) for storing the project's geographic data and/or links to such data in a separate cache.

In addition to these required components you may also wish to store additional resources required by the TileMill project in this folder (icons, patterns, fonts, etc.). You may organize these in any way you wish.

When resources are stored in a TileMill project folder, they can be _relatively referenced_ from that project. For example, if you make a folder called `icons` in a project folder, you could reference files inside of it from CartoCSS like this:

    point-file: url(icons/example.png);
