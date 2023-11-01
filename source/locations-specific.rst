Locations
#########

Locations are unique places or positions. A named town or city can be a Location, as can an administrative area like a county, district or state. In fact, anything that be drawn on a map can be a Location: a specific point, a section of a road, a military line of control, and so on.


Location: Summary of attributes
*******************************

The table below summarises the following dimensions of Locations:

 - Attribute label: a human readable label for the attribute
 - Attribute name: a unique machine-readable name for the attribute, used during data capture
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the attribute
 - Conformed name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-locations-attributes.csv
   :header-rows: 1
   :delim: tab

Location: Details of attributes
*******************************

This section contains further information about each attribute, including descriptions, examples of use, and Guidance on use.


Location: Unique Identifier
===========================

Attribute name
~~~~~~~~~~~~~~

``::location/id``

Description
~~~~~~~~~~~

A unique 36-character code assigned to each Location in the dataset.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

Example of use
~~~~~~~~~~~~~~

``5f55f3f1-ed83-4766-b26a-fd11bedc398c``

Guidance on use
~~~~~~~~~~~~~~~

This value is a Universally Unique Indentifier (UUID) generated using a computer program. UUIDs must be created using either installable or online tools. Values stored in this attribute are referenced in attributes like :ref:`Unit: Location`.


Location: Researcher Comments
=============================

Attribute name
~~~~~~~~~~~~~~

``::location/comments``

Description
~~~~~~~~~~~

Observations specific to the process of reviewing data in this attribute, including fixes, refinements and other suggestions.

Type of attribute
~~~~~~~~~~~~~~~~~

Text

Status
~~~~~~

Example of use
~~~~~~~~~~~~~~

``Location does not exist in OpenStreetMap - alternate source needed``, ``Possible duplicate of Location 1bbdfd2b-2d7c-4677-8e1f-8fa5b0367cfe``, ``Reprocess to update geometry``

Guidance on use
~~~~~~~~~~~~~~~

Staff Researchers use this attribute to pass on feedback about the data in the attribute. This may include specific data changes and other observations that can improve the quality of the data. Data in this attribute are not intended for publication. The workflow of Location datapoints is a little different from other entities within the SFM data model, in that it is a combination of manual work by Staff Researchers and automation by developers. The comments attribute is commonly used to flag places where developers may need to provide assistance. The comments attribute is common to all main entities and claim types in the SFM data model.


Location: Unique Human-Readable Identifier
==========================================

Attribute name
~~~~~~~~~~~~~~

``::location/humane-id``

Description
~~~~~~~~~~~

A human-readable unique identifier for each Location in the dataset.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``Ta'izz Governorate (osm, poly) 5c35b342-0b5e-4648-86cd-7ad730d647fa``

Guidance on use
~~~~~~~~~~~~~~~

The values in ``::location/humane-id`` are a concatenation of four other values in the attribute of data. They provide a unique but human-readable key that can be included in Units and Incidents data to refer to a specific Location within the ``Locations`` dataset. The attribute is created by following the below format:

::

  location:name (Location:origin, Location:geotype) Location:id:admin

The value ``Ta'izz Governorate (osm, poly) 5c35b342-0b5e-4648-86cd-7ad730d647fa`` tells us that the name of the place is ``Ta'izz Governorate``, that it is a Location found in ``osm`` (short for "OpenStreetMap") that it denotes an area (``poly``); the UUID provides the hard link to a specific attribute in the Location table.

Values in ``::location/humane-id`` provide Staff Researchers with a legible way to reference a Location specifically when using spreadsheets to construct datasets. For example, when defining a ``site`` or ``area of operations`` i  :ref:`Unit: Positioning` entity, a humane ID is used. The reason for this particular formulation is the need to balance readability with uniqueness. We could choose to use the UUID in ``::location/id`` as a way to reference Locations in other tables, but this would not give any easy-to-see indication about where the Location was, or what sort of Location it was. Similarly, the values in ``::location/name`` could be used as a reference to a Location, but these are not unique enough for us to be certain that we are referencing the correction Location. The format we have chosen balances these competing needs, giving the user a quick way to see the name of a Location, what type of object it is, where we got it from, along with its UUID.


Location: Origin Object Name
============================

Attribute name
~~~~~~~~~~~~~~

``::location/name``

Description
~~~~~~~~~~~

The name of the Location as specified in the source of geospatial information from which it is taken.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

THis attribute is required.

Example of use
~~~~~~~~~~~~~~

```Ta'izz Governorate```

Guidance on use
~~~~~~~~~~~~~~~

Locations are a combination of metadata entered by hand and other data obtained through use of automation tools. Locations are also derived from different data sources that may describe geographic objects in a variety of ways. The value in ``::location/name`` is to be taken directly from the geospatial data source. For example, if a Location is derived from OpenStreetMap, we take the value from OSM's own ``name`` attribute and place it in ``::location/name``. Along with ``::location/id`` and ``::location/geo-type``, ``::location/name`` is needed in order for automation tools toidentify the object within the geospatial data source. Where a Location is arbitrarily-defined, or is derived from a data source that does not provide a name, the Staff Researcher can provide one.


Location: Origin Object Identifier
==================================

Attribute name
~~~~~~~~~~~~~~

``::location/foreign-id``

Description
~~~~~~~~~~~

The identifier for the Location as specified in the source of geospatial information from which it is taken.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``383895``

Guidance on use
~~~~~~~~~~~~~~~

Locations are a combination of metadata entered by hand and other data obtained through use of automation. Locations are also derived from different data sources that may describe geographic objects in a variety of ways. The value in ``location:id`` is to be taken directly from the geospatial data source. For example, if a Location is derived from OpenStreetMap, we take the value from OSM's ``id`` attribute and place it in the ``::location/id`` attribute. Along with ``::location/name`` and ``::location/geo-type``, ``::location/id`` is needed in order for automation tools to identify the object within the geospatial data source. Where a Location is arbitrarily defined, or is derived from a data source that does not provide a ID number, the Staff Researcher can provide one.

Location: Geometry Type
=======================

Attribute name
~~~~~~~~~~~~~~

``::location/geo-type``

Description
~~~~~~~~~~~

The two-dimensional geometric primative of the Location, as defined in the source of geospatial information from which it is taken.

Type of attribute
~~~~~~~~~~~~~~~~~

Text

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``point``, ``poly``

Guidance on use
~~~~~~~~~~~~~~~

This attribute used a controlled vocabulary to describe the type of geometry used to represent the Location on a map. The Staff Researcher can choose from the following three options?

 - ``point``: the Location is a single distinct point on a map, represented by a single pair of geographic coordinates.
 - ``poly``: the Location is a closed area on a map, its boundary described by a sequence of geographic coordinates.
 - ``line``: the Location is a line on a map, described by a sequence of geographic coordinates. A ``line`` may also be closed.

The gazeteer used as the source of geometry may used different terminology to describe the Location. For example, in OpenStreetMap the boundaries of administrative areas (such as counties or states) `are described <https://wiki.openstreetmap.org/wiki/Relation>`_ using an object called a ``relation``; although this can be a complex mix of different objects, for our purposes it is a ``poly`` because it describes an area.

Along with the values in ``::location/name``, ``::location/origin`` and ``::location/id`` the value entered in ``::location/geo-type`` becomes part of the Location's "humane id", a human-readable unique identifier that acts as a reference for a Location when it is used in other parts of the data model (such as when defining a "site" in the :ref:`Units` data,for example).

Location: Origin
================

Attribute name
~~~~~~~~~~~~~~

``::location/origin``

Description
~~~~~~~~~~~

The geospatial information source that provides information about this Location.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is required.


Example of use
~~~~~~~~~~~~~~

``osm``, ``sfm``, ``hdx``, ``mimu``, ``khrg``

Guidance on use
~~~~~~~~~~~~~~~

SFM uses a combination of manual data entry and automated processes to manage Location information. The values in ``location:origin`` identify where automation tools should go to obtain spatial information about an object. For example, if the value ``osm`` is entered in ``location:origin`` this indicates that the automation tool should query OpenStreetMap in order to obtain spatial information about a Location. If ``osm`` were set, then the values in ``location:name`` and ``location:id`` would correspond to the object name and ID number in OpenStreetMap. Locations can be derived from comprehensive online services, as well as other sources like locally-held ``.shp`` or ``.kml`` files. The number of origins is unlimited.

Location: Country
=================

Attribute name
~~~~~~~~~~~~~~

``::location/country``

Description
~~~~~~~~~~~

Country in which the Location is situated.

Type of attribute
~~~~~~~~~~~~~~~~~

Text, controlled vocabulary

Status
~~~~~~

This attribute is optional.


Example of use
~~~~~~~~~~~~~~

``ye``, ``ng``, ``mm``

Guidance on use
~~~~~~~~~~~~~~~

Values for this attribute are the ISO 3166-1 alpha-2 country codes, which can be found (`on the ISO website <https://www.iso.org/obp/ui/#search/code/>`__ and on `Wikipedia <https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Officially_assigned_code_elements>`__). This attribute is entered manually by the Staff Researcher and acts as a simple cross-check on the automatically-populted values in ``location/admin-level-2``.


Location: Citation
==================

Attribute name
~~~~~~~~~~~~~~

``::location/citation-id``

Description
~~~~~~~~~~~

The UUID of the citation in the source that provides information about the Location.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``20248d51-6efe-4150-a5b6-4211fd83365d``

Guidance on use
~~~~~~~~~~~~~~~

SFM uses a number of different sources of geographical information. These include OpenStreetMap, data provided by the United Nations through the Humanitarian Data Exchange or the Myanmar Information Management Unit, and Locations that are arbitrarily defined during research. Staff Researchers should use the ``::location/citation-id`` attribute to make note of exactly which dataset has been used as a source of this Location. The UUID will reference an entry in the :ref:`Citation` dataset. In this way, the ``::location/source`` attribute serves a different purpose to ``::location/origin``.


Location: Admin Level
=====================

Attribute name
~~~~~~~~~~~~~~

``::location/admin-level``

Description
~~~~~~~~~~~

The administrative level of the Location described in the attribute, if defined in the source of geographical information from which the Location is derived.

Type of attribute
~~~~~~~~~~~~~~~~~

Numbers; programatically created.

Status
~~~~~~

Example of use
~~~~~~~~~~~~~~

``2``

Guidance on use
~~~~~~~~~~~~~~~

In every country, places are organized hierarchically based on their political significance, population and other factors. This feature passes into geographical information systems. At the top of the hierarchy rests the international boundary and capital city of a country; beneath this, there are sub-national divisions like states or provinces, and regional capitals, followed by districts, counties, municipalities, towns, suburbs, wards and so on. Different countries have different ways of describing these political and administrative divisions, but they are largely hierarchical and can be cross-compared. Knowing the level(s) at which a Location sits in the overall hierarchy provides us with a useful way to group and understand Locations; it can tell us important things about political and administrative authority, governance and elections, as well as security force jurisdictions and organizational structures. 

The attribute ``::location:admin-level`` is drawn from OpenStreetMap, which has a `comprehensive table <https://wiki.openstreetmap.org/wiki/Tag:boundary=administrative>`__ that matches the divisions that exist in every state to a single ranking scheme from ``2`` (international border) to ``10`` (small villages and communities). Some countries have defined a level ``11`` division, but we do not use this. Not all levels are present in every country: for example, Mexico does not define a level 3 administrative area.

The data in ``location:admin-level`` and the other "admin_level" attributes are automatically populated using a script that queries the OSM Overpass API. The Staff Researcher does not do this manually.

Location: Admin Level 10
========================

Attribute name
~~~~~~~~~~~~~~

``::location/admin-level-10``

Description
~~~~~~~~~~~

The administrative level 10 Location within which the present Location is wholly situated.

Type of attribute
~~~~~~~~~~~~~~~~~

String; programatically generated.

Status
~~~~~~

Example of use
~~~~~~~~~~~~~~

``Zone 13 (osm, poly) b858ac31-9e46-4818-b70a-572756d60012``, a *barangay zone* `in the Philippines <https://www.openstreetmap.org/relation/11378938>`__.

Guidance on use
~~~~~~~~~~~~~~~

This attribute contains the human-readable idenfifier (``::location/humane-id``) of the level 10 adminstrative area in which the current Location is situated. Level 10 is a extrenely small adminstrative division, and is rarely specified in freely available geospatial information sources. 

The `schema used by OpenStreetMap <https://wiki.openstreetmap.org/wiki/Tag:boundary=administrative>`__, for example, includes *quartiers* (Belgium), *asumid* (subdistricts of Talinn, Estonia) and *الحي* (neighbourhoods of Damascus, Syria) in the list of types of level 10 administrative area.

This attribute is programmatically generated using a geospatial query; the Staff Researcher does not enter this manually.


Location: Admin Level 9
=======================

Attribute name
~~~~~~~~~~~~~~

``::location/admin-level-9``

Description
~~~~~~~~~~~

The administrative level 9 Location within which the present Location is wholly situated.

Type of attribute
~~~~~~~~~~~~~~~~~

String; programatically generated.

Status
~~~~~~

Example of use
~~~~~~~~~~~~~~

``Zone 13 (osm, poly) b858ac31-9e46-4818-b70a-572756d60012``, a *barangay zone* `in the Philippines <https://www.openstreetmap.org/relation/11378938>`__.

Guidance on use
~~~~~~~~~~~~~~~

This attribute contains the human-readable idenfifier (``::location/humane-id``) of the level 9 adminstrative area in which the current Location is situated. Level 9 is a extrenely small adminstrative division, and is rarely specified in freely available geospatial information sources. 

The `schema used by OpenStreetMap <https://wiki.openstreetmap.org/wiki/Tag:boundary=administrative>`__, for example, includes *arangay zones* (Philippines), *Sectores y Barrios de 1° nivel* (Venezuela) and *မြို့နယ်* (townships in Myanmar) in the list of types of level 9 administrative area.

This attribute is programmatically generated using a geospatial query; the Staff Researcher does not enter this manually.

Location: Admin Level 8
=======================

Attribute name
~~~~~~~~~~~~~~

``::location/admin-level-8``

Description
~~~~~~~~~~~

The administrative level 8 Location within which the present Location is wholly situated.

Type of attribute
~~~~~~~~~~~~~~~~~

String; programatically generated.

Status
~~~~~~

Example of use
~~~~~~~~~~~~~~

``Ermita (osm, poly) 9989ba43-3b03-473a-8226-511a8eb82c3d``, an `administrative district of Manila <https://www.openstreetmap.org/relation/103706#map=15/14.5852/120.9821>`__ in the Philippines.

Guidance on use
~~~~~~~~~~~~~~~

This attribute contains the human-readable idenfifier (``::location/humane-id``) of the level 8 adminstrative area in which the current Location is situated. Level 9 is a relatively small adminstrative division, and may not be commonly found in freely available geospatial information sources.

The `schema used by OpenStreetMap <https://wiki.openstreetmap.org/wiki/Tag:boundary=administrative>`__, for example, includes *city corporations* (Bangladesh), *cantons* (Chad) and *kebele* (Ethiopia) in the list of types of level 8 administrative area.

This attribute is programmatically generated using a geospatial query; the Staff Researcher does not enter this manually.

Location: Admin Level 7
=======================

Attribute name
~~~~~~~~~~~~~~

``::location/admin-level-7``

Description
~~~~~~~~~~~

The administrative level 7 Location within which the present Location is wholly situated.

Type of attribute
~~~~~~~~~~~~~~~~~

String; programatically generated.

Status
~~~~~~

Example of use
~~~~~~~~~~~~~~

``Wuse II (osm, poly) 111f698a-421e-4fc8-9ace-c0aa62b461b5``

Guidance on use
~~~~~~~~~~~~~~~

This attribute contains the human-readable idenfifier (``::location/humane-id``) of the level 7 adminstrative area in which the current Location is situated. Level 7 areas are commonly found in freely available geospatial information sources such as OpenStreetMap.

The `schema used by OpenStreetMap <https://wiki.openstreetmap.org/wiki/Tag:boundary=administrative>`__, for example, includes *sous-préfectures* (Chad), *arrondissements* (in the cities of Ouagadougou and Bobo Dioulasso, Burkina Faso) and *microrregiões* (micro-regions in Brazil) in the list of types of level 7 administrative area.

This attribute is programmatically generated using a geospatial query; the Staff Researcher does not enter this manually.


Location: Admin Level 6
=======================

Attribute name
~~~~~~~~~~~~~~

``::location/admin-level-6``

Description
~~~~~~~~~~~

The administrative level 6 Location within which the present Location is wholly situated.

Type of attribute
~~~~~~~~~~~~~~~~~

String; programatically generated.

Status
~~~~~~

Example of use
~~~~~~~~~~~~~~

``Arbinda (osm, poly) 659c231e-eb1e-4c46-a710-b7663ef9f2e0``, a *commune rurale* `in Burkina Faso <https://www.openstreetmap.org/relation/6199315>`__.

Guidance on use
~~~~~~~~~~~~~~~

This attribute contains the human-readable idenfifier (``::location/humane-id``) of the level 6 adminstrative area in which the current Location is situated. Level 6 areas are commonly found in freely available geospatial information sources such as OpenStreetMap.

The `schema used by OpenStreetMap <https://wiki.openstreetmap.org/wiki/Tag:boundary=administrative>`__, for example, includes *départments* (Chad), *municipios* (Mexico) and local government areas (Nigeria) in the list of types of level 6 administrative area.

This attribute is programmatically generated using a geospatial query; the Staff Researcher does not enter this manually.

Location: Admin Level 5
=======================

Attribute name
~~~~~~~~~~~~~~

``::location/admin-level-5``

Description
~~~~~~~~~~~

The administrative level 5 Location within which the present Location is wholly situated.

Type of attribute
~~~~~~~~~~~~~~~~~

String; programatically generated.

Status
~~~~~~

Example of use
~~~~~~~~~~~~~~

``Seti (osm, poly) 64a4dd09-36d4-4455-bd07-a77addc91946``, a `zone in Nepal <https://www.openstreetmap.org/relation/4583223>`__.

Guidance on use
~~~~~~~~~~~~~~~

This attribute contains the human-readable idenfifier (``::location/humane-id``) of the level 5 adminstrative area in which the current Location is situated. Level 5 areas are commonly found in freely available geospatial information sources such as OpenStreetMap.

The `schema used by OpenStreetMap <https://wiki.openstreetmap.org/wiki/Tag:boundary=administrative>`__, for example, includes the *préfecture* (Togo), *Provincial legislative districts* (Philippines) and regions (Côte d'Ivoire) in the list of types of level 5 administrative area.

This attribute is programmatically generated using a geospatial query; the Staff Researcher does not enter this manually.

Location: Admin Level 4
=======================

Attribute name
~~~~~~~~~~~~~~

``::location/admin-level-4``

Description
~~~~~~~~~~~

The administrative level 4 Location within which the present Location is wholly situated.

Type of attribute
~~~~~~~~~~~~~~~~~

String; programatically generated.

Status
~~~~~~

Example of use
~~~~~~~~~~~~~~

``Gombe (osm, poly) 06791bb5-c39d-4a32-a05b-f3945c4f83ea``, a `state in Nigeria <https://www.openstreetmap.org/relation/3720422>`__.

Guidance on use
~~~~~~~~~~~~~~~

This attribute contains the human-readable idenfifier (``::location/humane-id``) of the level 4 adminstrative area in which the current Location is situated. Level 4 areas are commonly found in freely available geospatial information sources such as OpenStreetMap, and are usually the largest sub-national administrative areas.

The `schema used by OpenStreetMap <https://wiki.openstreetmap.org/wiki/Tag:boundary=administrative>`__, for example, includes provinces (Philippines), states (Nigeria) and *régions* (Mali) in the list of types of level 4 administrative area.

This attribute is programmatically generated using a geospatial query; the Staff Researcher does not enter this manually.

Location: Admin Level 3
=======================

Attribute name
~~~~~~~~~~~~~~

``::location/admin-level-3``

Description
~~~~~~~~~~~

The administrative level 3 Location within which the present Location is wholly situated.

Type of attribute
~~~~~~~~~~~~~~~~~

String; programatically generated.

Status
~~~~~~

Example of use
~~~~~~~~~~~~~~

``Central Visayas (osm, poly) 81848978-3998-48bf-87a7-bd1888912aee``, `a region of the Philippines <https://www.openstreetmap.org/relation/3625910>`__.

Guidance on use
~~~~~~~~~~~~~~~

This attribute contains the human-readable idenfifier (``::location/humane-id``) of the level 3 adminstrative area in which the current Location is situated. Where defined, level 3 administrative areas are commonly found in freely available geospatial information sources such as OpenStreetMap.

The `schema used by OpenStreetMap <https://wiki.openstreetmap.org/wiki/Tag:boundary=administrative>`__, for example, includes regions (Philippines) in the list of types of level 3 administrative area.

This attribute is programmatically generated using a geospatial query; the Staff Researcher does not enter this manually.

Location: Admin Level 2
=======================

Attribute name
~~~~~~~~~~~~~~

``::location/admin-level-2``

Description
~~~~~~~~~~~

The administrative level 2 Location - the international state boundary - within which the present Location is wholly situated.

Type of attribute
~~~~~~~~~~~~~~~~~

String; programatically generated.

Status
~~~~~~

Example of use
~~~~~~~~~~~~~~

``Mali (osm, poly) 8e7b492e-5346-4f43-91a0-55c1f3419468``, ``Sudan (osm, poly) 7117df90-1e52-4726-806a-8e422a0511c6``

Guidance on use
~~~~~~~~~~~~~~~

This attribute contains the human-readable identifier (``::location/humane-id``) of the international boundary of a state, also known within the OpenStreetMap schema of administrative areas as a level 2 boundary. This attribute is programatically generated using a geospatial query; the Staff Researcher does not enter this manually.

Location: First Check Timestamp
===============================

Attribute name
~~~~~~~~~~~~~~

``::location/first-check-time``

Description
~~~~~~~~~~~

Timestamp of the first time that metadata and geometry for this Location was obtained programatically from OpenStreetMap Overpass API.

Type of attribute
~~~~~~~~~~~~~~~~~

Datetime; programatically generated.

Guidance on use
~~~~~~~~~~~~~~~

After Staff Researchers have entered the minimum metadata for a Location, we use a script to obtain further information about that object from OpenStreetMap's Overpass API. Overpass gives us the full set of metadata tags for the Location (such as its name in local languages, its last date of update and so on) as well as the geometry that we use to plot the Location on a map. As Location objects can change over time, we keep a record of the date and time at which we first obtained the extended metadata from OSM, as well as the most recent.

This is a programmatically generated attribute; the Staff Researcher should not enter this directly.

Location: Most Recent Check Timestamp
=====================================

Attribute name
~~~~~~~~~~~~~~

``::location/last-check-time``

Description
~~~~~~~~~~~

Timestamp of the most recent time that metadata and geometry for this Location was obtained programatically from OpenStreetMap Overpass API.

Type of attribute
~~~~~~~~~~~~~~~~~

Datetime; programatically generated.

Status
~~~~~~

Example of use
~~~~~~~~~~~~~~

``2021-02-15T20:33:02Z``

Guidance on use
~~~~~~~~~~~~~~~

After Staff Researchers have entered the minimum metadata for a Location, we use a script to obtain further information about that object from OpenStreetMap's Overpass API. Overpass gives us the full set of metadata tags for the Location (such as its name in local languages, its last date of update and so on) as well as the geometry that we use to plot the Location on a map. As Location objects can change over time, we keep a record of the date and time at which we first obtained the extended metadata from OSM, as well as the most recent.

This is a programmatically generated attribute; the Staff Researcher should not enter this directly.


Location: Attic Date
====================

Attribute name
~~~~~~~~~~~~~~

``::location/as-of-date``

Description
~~~~~~~~~~~

The date and time of the old version of an OpenStreetMap item that we want to retrieve.

Type of attribute
~~~~~~~~~~~~~~~~~

Datetime

Status
~~~~~~

Example of use
~~~~~~~~~~~~~~

``2009-03-24T07:50:06Z``

Guidance on use
~~~~~~~~~~~~~~~

OpenStreetMap is created by its users and every update to any object on the map is recorded and stored. This means you can see the history of an object, and that changes to the map can be observed, discussed and reverted if necessary. The version history of a map object is also important for SFM research, because it may give us a way to access earlier representations of administrative geography. Borders and boundaries change all the time, and these changes are often reflected in the map's history. It also means that we can protect the integrity of our own data by indicating that the Location is based on an OpenStreetMap object *as it was* at a particular date and time. 

The feature of OpenStreetMap that enables this is the repository of `attic data <https://wiki.openstreetmap.org/wiki/Attic_Data>`__, and it can be queried using the Overpass API (directly or by using the SFM ``geo`` tool). The value the Staff Researcher enters into ``location:as_of_date`` must correspond a value listed in the version history of an object. This information is accessible by selecting "View history" on any OSM object, followed by "Download XML". Here is `an example of the attic data for Ermita <https://www.openstreetmap.org/api/0.6/relation/103706/history>`__, a level 9 administrative area in then Philippines.

Location: Notes
===============

Attribute name
~~~~~~~~~~~~~~

``::location/notes``

Description
~~~~~~~~~~~

Analysis, commentary and notes about the Location that do not fit into the data structure.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

Example of use
~~~~~~~~~~~~~~

``Sources show Location is within the forested areas between two villages and is derived through geolocation and image analysis of source eeb13cf1-7b98-4075-a09b-530146d2ee37``

Guidance on use
~~~~~~~~~~~~~~~

We use this attribute to record information about the Location that is likely to provide useful context, additional information that does not fit into the data structure, and notes about how decisions were made about which data to include. Any sources used should be referenced directly inside the attribute. Notes are intended to be published.
