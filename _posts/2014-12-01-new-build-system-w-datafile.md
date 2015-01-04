---
layout: post
title: "New beer.db Build System - Welcome ./Datafile e.g. $beerdb new at"
---


The beerdb command line tool now includes a new build system (as a
new and easier all-in-one option). To try it - use the new Datafile - a mini language
a.k.a. domain-specific language (DSL) that lets you setup new beer.db's in
minutes. For example, to setup a beer.db for Austria use:


`Datafile`:

~~~
world 'openmundi/world.db', setup: 'countries'
world 'openmundi/austria.db'

beer 'openbeer/at-austria'
~~~

That's it.  Now run

~~~
$ beerdb build
~~~

The new build command will look for the `./Datafile` script in your
working folder and

- Step 1) Download all datasets as zip archives (from GitHub) to  `./tmp`
- Step 2) Create all database tables
- Step 3) Read/import all datasets from the zip archives in `./tmp` (no need to unpack)

That's it.  Still early and rough. If you try the new Datafile
build let us know how it goes.

PS: The repo also includes new quick starter Datafile templates. Use like

~~~
$ beerdb new <name>  e.g.
$ beerdb new at
~~~

See the new quick start [Datafile repo](https://github.com/openbeer/datafile) for details.
