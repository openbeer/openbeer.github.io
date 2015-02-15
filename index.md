---
layout: default
title: Welcome
---

# {{ page.title }}

<div class="toc" markdown="1">
Contents:

* [What's `beer.db`?](#whatis)
* [Web Admin App](#webadmin)
* [Web Service / HTTP JSON API](#webservice)
* [Command Line Tool - Build Your Own `beer.db` Copy](#build)
* [Talks - Slide Decks](#talks)
* [About, License - Questions? Comments?](#license)
</div>


## What's `beer.db`?   {#whatis}

A free open public domain beer database & schema
for use in any (programming) language
(e.g. uses plain text data sets).


**Schema Diagram**

![](i/beerdb-models.png)

**Datasets Examples**

### Breweries

"Classic" comma-separated values single-line record style

~~~
alaskan, Alaskan Brewing Co., 1986, AK, Juneau | AK 99801-9540 // 5429 Shaune Dr.
brooklyn, Brooklyn Brewery, 1987, NY, Brooklyn | NY 11249 // #1 Brewers Row // 79 N 11th St.
dixie, Dixie Brewing Co., 1907, LA, New Orleans | LA 70119 // 2401 Tulane Ave.
~~~

or

"Modern" comma-separated values multi-line record style

~~~
[alaskan]
  Alaskan Brewing Co., 1986
  5429 Shaune Dr. // Juneau, AK 99801-9540

[brooklyn]
  Brooklyn Brewery, 1987
  #1 Brewers Row // 79 N 11th St. // Brooklyn, NY 11249

[dixie]
  Dixie Brewing Co., 1907
  2401 Tulane Ave. // New Orleans, LA 70119
~~~


### Beers

~~~
_________________________________
- Alaskan Brewing Co., Juneau

Alaskan Pale,  5.2%, golden_ale
Alaskan Amber, 5.3%, alt
Alaskan IPA|Alaskan India Pale Ale, 6.2%,  ipa|india_pale_ale
Alaskan Smoked Porter, 6.5%,   porter

_______________________
- Brooklyn Brewery

Brooklyn Lager,     5.2%, lager|american_amber_lager
Brooklyn Brown Ale, 5.6%,  brown_ale|american_brown_ale
Brooklyn East India Pale Ale,  6.9%,  ipa|india_pale_ale
Brooklyn Pilsner,  5.1%,   pilsner|golden_lager
Brooklyn Black Chocolate Stout,  10.0%,  imperial_stout
Brooklyn Dry Irish Stout, 4.7%,  dry_irish_stout
Brooklyn Oktoberfest, 5.5%,   maerzen|oktoberfest

___________________________________
- Dixie Brewing Co., New Orleans

Dixie|Dixie Lager, 4.6%, american_lager
Dixie Blackened Voodoo|Dixie Blackened Voodoo Lager,  5.0%,  munich_dunkel|dark_lager
~~~


## Web Admin App {#webadmin}

Try the `beer.db` Web Admin app running
on Heroku [`prost.herokuapp.com`](http://prost.herokuapp.com).

![](i/beer_db_admin_screenshoot.png)


## Web Service / HTTP JSON API - `GET /beer/guinness`   {#webservice}

Try the `beer.db` HTTP JSON API running
on Heroku [`prost.herokuapp.com/api`](http://prost.herokuapp.com/api).

Example:

~~~
GET /beer/guinness

{
  "key":"guinness",
  "title":"Guinness",
  "synonyms": "Guinness Draught",
  "abv":"4.2",
  "srm":null,
  "og":null,
  "tags":["irish_dry_stout","dry_stout","stout"],
  "brewery":
  {
    "key": "guinness",
    "title": "St. James's Gate Brewery / Guinness Brewery"
  },
  "country":
  {
    "key":"ie",
    "title":"Irland"
  }
}
~~~


## Command Line Tool - Build Your Own `beer.db` Copy   {#build}

Use the `beerdb` command line tool to build your own `beer.db` copy from the plain text fixtures. Example:

Step 1:  Get a copy of the `world.db` fixtures

    $ git clone git://github.com/openmundi/world.db.git

Step 2:  Get a copy of the Austrian beers 'n' breweries data set

    $ git clone git://github.com/openbeer/at-austria.git

Step 3:  Let's build the `beer.db`

    $ beerdb setup --include ./at-austria --worldinclude ./world.db

That's it. See the [`beerdb` command line tool project](https://github.com/geraldb/beer.db.ruby)
for more.


## Talks - Slide Decks   {#talks}

- [`beer.db` - Using Open Beer & Brewery Data in Ruby](https://github.com/openbeer/talks/blob/master/beer_db_intro.md)


## Real World Usage

- [beer.db.admin](https://github.com/geraldb/beer.db.admin) - `beer.db` Web Admin Tool in Ruby on Rails (version 3.2 and up).


## Alternatives

- [BreweryDB.com](http://www.brewerydb.com) -  beer and brewery data API by PintLabs Inc - (API use only - no database available for download; free demo; $ for use)
- [Open Beer Database](https://github.com/openbeerdatabase/openbeerdatabase)  - free, public beer and brewery data API by Tristan Dunn (work-in-progress; API use only - no database available for download)
- [Open Beer Database (`openbeerdb.com`)](http://openbeerdb.com)  - free, public beer and brewery database (archive, no longer active)

## License {#license}

The `beer.db` schema, data and scripts are dedicated to the public domain.
Use it as you please with no restrictions whatsoever.


{% include questions.md %}
