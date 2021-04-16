Locations
=========

What are Locations?
-------------------

Locations are unique places or positions. A named town or city can be a Location, as can an administrative area like a county, district or state. In fact, anything that be drawn on a map can be a Location: a specific point, a section of a road, a military line of control, and so on.

In the Security Force Monitor (SFM) data model, Locations are a primary entity; this means we manage them as a discrete set of datapoints that can be referenced in other parts of the dataset. Locations are the way we describe the "sites" and "areas of operation" of :ref:`Units`. Locations describe the geographic footprint of security forces, including their infrastructure (bases, facilities, checkpoints, air fields, bunkers), as well as their territorial jurisdictions and operations as they change over time. We also use Locations to describe the places where security force units are alleged to have committed human rights abuses.

To define a Location, we start with information included in the sources that underpin all our research (see :ref:`Data integrity measures` and :ref:`Sources`). The Location descriptions contained in sources vary greatly in their precision and accuracy:

 - At a precise coordinate: "Artillery Brigade deployed to latitude x, longitude y".
 - At a very specific place: "Has a checkpoint on the corner of street A and street B in Test Town".
 - At a very specific named place: "Based at Famous General Army Camp in Test Town".
 - At a nonspecific place in a particular settlement: "In Test Town".
 - In a named subdivision of a particular settlement: "Suburb A in Test Town".
 - In a named but nonspecific place near a particular settlement: "At the Smoth family borehole north of Test Town"
 - In a nonspecific place near a particular settlement: "Around Test Town".
 - In a definable area that is not a settlement: "In Test County".
 - In an area that is difficult to define: "Somewhere in the north of the country"

When we have decided on what Location is actually described in the source, we use the fields in this standard format to capture and structure data about the Location. We can do this by consulting existing sources of geospatial information like `OpenStreetMap <https://openstreetmap.org>`__, `Humanitarian Data Exchange <https://data.humdata.org/>`__, commercial mapping services like Google Maps, and (where they exist) data provided by the relevant national geospatial agencies. We reconcile the information we gain from the sources with options provided to us by a number of geospatial information sources, which we then turn into a Location.

For example. if a source describes a place called "Potiskum" in Yobe State, Nigeria we can `look it up on OpenStreetMap <https://www.openstreetmap.org/node/255322295>`__. From this record, we can capture the Location's name, object ID number (``255322295``) and its geometry type ( a "node", which is a "point" for our purposes). We enter this basic data about the Location into the Location fieldset, generate a UUID for it (``41b3aec7-d88e-4ef1-a7d8-1b7fdf81a20c``), and create a "human readable" key that we can then use to reference this specific Location in other parts of the data model (``Potiskum (osm, point) 41b3aec7-d88e-4ef1-a7d8-1b7fdf81a20c``). We can then use SFM's ``geo`` automation tool to obtain more information from OpenStreetMap about this Location, including its geometry (in this case, a coordinate pair), additional metadata (such as a name in Arabic or other local languages), and the various adminstrative areas (like states, local government areas, wards) in which it is sited. This additional information enables us to plot the Location on a map, and opens up a whole range of opportunities for geospatial analysis.

Where there is not a good option in an existing geospatial data source, and where the source contains sufficient descriptive information, we can create the Location data directly using a Geographical Information System (GIS) tool like QGIS, Earth Pro or Google My Maps. This method is useful for describing Locations that may emerge from geolocation processes, such as views portrayed in images and other subjective descriptions of a place.

We create a datasets of Locations for each country we work on. These data are stored in a spreadsheet (or delimited text file like ``.csv`` or ``.tsv``) and a corresponding ``GeoJSON`` file that contains everything in the spreadsheet as well as every Location's geometry and any additional metadata about the Location provided by the geospatial information source. The two files provide views of the data that are useful for different purposes. The ``.tsv`` can be easily updated using a spreadsheet, but it's not the right place to store the geometry; the ``GeoJSON`` is more useful to developers and can be pulled in a geographica information system (GIS) for analysis and visualisation. We keep the two files synchronised. Storing the Location data this way also means we retain a standalone copy in robust and easily-processed formats of all the data we need.

The Location model described in this documentation replaces an earlier approach that stored the full metadata about a Location alongside the data on Units and Incidents. Maintaining the Location information using the earlier approach involved a great deal of duplication and introduced more opportunities for error. This updated approach brings the management of Location information into a single place and idiom, enables more effective use of automation tools, and extends the range of data we can capture and manage about Locations.

Location: Research Status
-------------------------

**Description**

The place of a row of Location data in the research workflow.

**Type of field**

Text and numbers; controlled vocabulary.

**Example of use**

``3``, ``X``

**Spreadsheet column name**

``location:status:admin``

**Shortcode**

``l_sta_a``

**Sources**

No

**Confidence**

No

**Guidance on use**

Staff Researchers use this field to indicate where a row of data stands in the research workflow between the first cut of a row of data, review by other researchers, and final readiness for publication. Values in this field are taken from the below controlled list:


- `X`: Row should be deleted.
- `0`: First commit. This row of data has just been added and needs review.
- `1`: Fixes needed. A reviewer has made comments that need to be addressed, which will be recorded in the ``Locations:comments:admin`` field.
- `2`: Fixes made. The owner of this data has addressed the reviewer's comments.
- `3`: Clean. A final check has been made by a reviewer, and this row of data can be published.

This field is common to all main entities in the SFM data model.

Location: Research Comments
---------------------------

**Description**

Observations specific to the process of reviewing data in this row, including fixes, refinements and other suggestions.

**Type of field**

Text

**Example of use**

``Location does not exist in OpenStreetMap - alternate gazeteer needed``, ``Possible duplicate of Location 1bbdfd2b-2d7c-4677-8e1f-8fa5b0367cfe``, ``Reprocess to update geometry``

**Spreadsheet column name**

``location:comments:admin``

**Shortcode**

``l_com_a``

**Sources**

No

**Confidence**

No

**Guidance on use**

Staff Researchers use this administrative field to pass on feedback about the data in the row. This may included changes needed to specific fields in that row, references to sources that the owner of the row might look at, and other observations that can improve the quality of the data. Data in this field are not intended for publication. The workflow of Location datapoints is a little different from other entities within the SFM data model, in that it is a combination of manual work by Staff Researchers and automation work by developers. The comments field is commonly used to flag places where developers may need to provide assistance. The comments field is common to all main entities in the SFM data model.

Location: Unique Identifier
---------------------------

**Description**

A unique 36-character code assigned to each Location in the dataset.

**Type of field**

Text and numbers

**Example of use**

``5f55f3f1-ed83-4766-b26a-fd11bedc398c``

**Spreadsheet column name**

``location:id:admin``

**Shortcode**

``l_id_a``

**Sources**

No

**Confidence**

No

**Guidance on use**

This value is a Universally Unique Indentifier (UUID) generated using a computer program. UUIDs must be created using either installable or online tools, for example:

  - Linux and OSX/MacOS users: `uuidgen` command line tool.
  - On the web: `UUID Generator <https://www.uuidgenerator.net/version>`_.

The field is administrative, providing a reliable way to differentiate between different Locations. ID fields are common to all main entities in the SFM data model.

When a new Location is created in a spreadsheet, the Staff Researcher must generate a unique identifying number for the Locations and copy it into the field ``location:id:admin``. This manual, copy-and-paste step is a potential source of error and the Staff Researcher must be careful not to re-use a UUID.

 Bulk updates made to WhoWasInCommand.com by spreadsheet import are based on the values in this field. For example, changes made in the row ``a407be6a-28e6-4237-b4e9-307f27b120e`` in the spreadsheet will be applied to the Location with that UUID in WhoWasInCommand.

Location: Human-Readable Unique Identifier
------------------------------------------

**Description**

A human-readable unique identifier for each Location in the dataset.

**Type of field**

Text and numbers

**Example of use**

``Ta'izz Governorate (osm, poly) 5c35b342-0b5e-4648-86cd-7ad730d647fa``

**Spreadsheet column name**

``location:humane_id:admin``

**Shortcode**

``l_hid_a``

**Sources**

No

**Confidence**

No

**Guidance on use**

The values in ``location:humane_id:admin`` are a concatenation of four other values in the row of data. They provide a unique but human-readable key that can be included in Units and Incidents data to refer to a specific Location within the ``Locations`` dataset. The field is created by following the below format:

::

  location:name (Location:origin, Location:geotype) Location:id:admin

The value ``Ta'izz Governorate (osm, poly) 5c35b342-0b5e-4648-86cd-7ad730d647fa`` tells us that the name of the place is ``Ta'izz Governorate``, that it is a Location found in ``osm`` (short for "OpenStreetMap") that it denotes an area (``poly``); the UUID provides the hard link to a specific row in the Location table.

Values in ``location:humane_id:admin`` are used by Staff Researchers to reference a Location in other data tables. For example, when defining a ``site`` or ``area of operations`` in the :ref:`Units` tables, a value from ``location:humane_id:admin`` is used. The reason for this particular formulation is the need to balance readability with uniqueness. We could choose to use the UUID in ``location:id:admin`` as a way to reference Locations in other tables, but this would not give any indication about where the Location was, or what sort of Location it was. Similarly, the values in ``location:name`` could be used as a reference to a Location, but these are not unique enough for us to be certain that we are referencing the correction Location. The format we have chosen balances these competing needs, giving the user a quick way to see the name of a Location, what type of object it is, where we got it from, along with its UUID.

Location: Object Name
---------------------

**Description**

The name of the Location as specified in the source of geospatial information from which it is taken.

**Type of field**

Text and numbers

**Example of use**

```Ta'izz Governorate```

**Spreadsheet column name**

``location:name``

**Shortcode**

``l_n``

**Sources**

No

**Confidence**

No

**Guidance on use**

Locations are a combination of metadata entered by hand and other data obtained through use of automation tools. Locations are also derived from different data sources that may describe geographic objects in a variety of ways. The value in ``location:name`` is to be taken directly from the geospatial data source. For example, if a Location is derived from OpenStreetMap, we take the value from OSM's ``name`` field and place it in ``location:name``. Along with ``location:id`` and ``location:geo_type``, ``location:name`` is needed in order for automation tools toidentify the object within the geospatial data source. Where a Location is arbitrarily-defined, or is derived from a data source that does not provide a name, the Staff Researcher can provide one.

Location: Object Identifier
---------------------------

**Description**

The identifier for the Location as specified in the source of geospatial information from which it is taken.

**Type of field**

Text and numbers

**Example of use**

``383895``

**Spreadsheet column name**

``location:id``

**Shortcode**

``l_oid``

**Sources**

No

**Confidence**

No

**Guidance on use**

Locations are a combination of metadata entered by hand and other data obtained through use of automation. Locations are also derived from different data sources that may describe geographic objects in a variety of ways. The value in ``location:id`` is to be taken directly from the geospatial data source. For example, if a Location is derived from OpenStreetMap, we take the value from OSM's ``id`` field and place it in ``location:id``. Along with ``location:name`` and ``location:geo_type``, ``location:id`` is needed in order for automation tools to identify the object within the geospatial data source. Where a Location is arbitrarily defined, or is derived from a data source that does not provide a ID number, the Staff Researcher can provide one.

Location: Object Geometry Type
------------------------------

**Description**

The two-dimensional geometric primative of the Location, as defined in the source of geospatial information from which it is taken.

**Type of field**

Text

**Example of use**

``point``, ``poly``

**Spreadsheet column name**

``location:geo_type``

**Shortcode**

``l_gt``

**Sources**

No

**Confidence**

No

**Guidance on use**

This field used a controlled vocabulary to describe the type of geometry used to represent the Location on a map. The Staff Researcher can choose from the following three options?

 - ``point``: the Location is a single distinct point on a map, represented by a single pair of geographic coordinates.
 - ``poly``: the Location is a closed area on a map, its boundary described by a sequence of geographic coordinates.
 - ``line``: the Location is a line on a map, described by a sequence of geographic coordinates. A ``line`` may also be closed.

The gazeteer used as the source of geometry may used different terminology to describe the Location. For example, in OpenStreetMap the boundaries of administrative areas (such as counties or states) `are described <https://wiki.openstreetmap.org/wiki/Relation>`_ using an object called a ``relation``; although this can be a complex mix of different objects, for our purposes it is a ``poly`` because it describes an area.

Along with the values in ``location:name``, ``location:id`` and ``location:id:admin`` the value entered in ``location:geo_type`` becomes part of the Location's "humane id", a human-readable unique identifier that acts as a reference for a Location when it is used in other parts of the data model (such as when defining a "site" in the :ref:`Units` data,for example).

Location: Origin
----------------

**Description**

The geospatial information source that provides information about this Location.

**Type of field**

Text and numbers

**Example of use**

``osm``, ``sfm``, ``hdx``

**Spreadsheet column name**

``location:origin``

**Shortcode**

``l_o``

**Sources**

No

**Confidence**

No

**Guidance on use**

SFM uses a combination of manual data entry and automated processes to manage Location information. The values in ``location:origin`` identify where automation tools should go to obtain spatial information about an object. For example, if the value ``osm`` is entered in ``location:origin`` this indicates that the automation tool should query OpenStreetMap in order to obtain spatial information about a Location. If ``osm`` were set, then the values in ``location:name`` and ``location:id`` would correspond to the object name and ID number in OpenStreetMap. Locations can be derived from comprehensive online services, as well as other sources like locally-held ``.shp`` or ``.kml`` files. The number of origins is unlimited.

Location: Source
----------------

**Description**

The UUID of the access point in the source that provides information about the Location.

**Type of field**

Text and numbers

**Example of use**

``20248d51-6efe-4150-a5b6-4211fd83365d``

**Spreadsheet column name**

``location:source``

**Shortcode**

``l_s``

**Sources**

No

**Confidence**

No

**Guidance on use**

SFM uses a number of different sources of geographical information, including OpenStreetMap, data provided by the United Nations through the Humanitarian Data Exchange, and Locations that are arbitrarily defined during research. Staff Researchers should use the ``location:source`` field to make note of exactly which dataset has been used as a source of this Location. The UUID will reference an entry in the :ref:`Sources` dataset. In this way, the ``location:source`` field serves a different purpose to ``location:origin``.

Location: Country
-----------------

**Description**

Country in which the Location is situated.

**Type of field**

Text, controlled vocabulary

**Example of use**

``ye``, ``ng``, ``mm``

**Spreadsheet column name**

``location:country``

**Shortcode**

``l_c``

**Sources**

No

**Confidence**

No

**Guidance on use**

Values for this field are the ISO 3166-1 alpha-2 country codes, which can be found (`on the ISO website <https://www.iso.org/obp/ui/#search/code/>`__ and on `Wikipedia <https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Officially_assigned_code_elements>`__). This field is entered manually by the Staff Researcher and acts as a simple cross-check on the automatically-populted values in ``location:admin_level_2``.

Location: Admin Level
---------------------

**Description**

The administrative level of the Location described in the row, if defined in the source of geographical information from which the Location is derived.

**Type of field**

Numbers; programatically created.

**Example of use**

``2``

**Spreadsheet column name**

``location:admin_level``

**Shortcode**

``l_al``

**Sources**

No

**Confidence**

No

**Guidance on use**

In every country, places are organized hierarchically based on their political significance, population and other factors. This feature passes into geographical information systems. At the top of the hierarchy rests the international boundary and capital city of a country; beneath this, there are sub-national divisions like states or provinces, and regional capitals, followed by districts, counties, municipalities, towns, suburbs, wards and so on. Different countries have different ways of describing these political and administrative divisions, but they are largely hierarchical and can be cross-compared. Knowing the level(s) at which a Location sits in the overall hierarchy provides us with a useful way to group and understand Locations; it can tell us important things about political and administrative authority, governance and elections, as well as security force jurisdictions and organizational structures. 

The field ``location:admin_level`` is drawn from OpenStreetMap, which has a `comprehensive table <https://wiki.openstreetmap.org/wiki/Tag:boundary=administrative>`__ that matches the divisions that exist in every state to a single ranking scheme from ``2`` (international border) to ``10`` (small villages and communities). Some countries have defined a level ``11`` division, but we do not use this. Not all levels are present in every country: for example, Mexico does not define a level 3 administrative area.

The data in ``location:admin_level`` and the other "admin_level" fields are automatically populated using a script that queries the OSM Overpass API. The Staff Researcher does not do this manually.

Location: Admin Level 10
------------------------

**Description**

The administrative level 10 Location within which the present Location is wholly situated.

**Type of field**

Text and numbers; programatically created.

**Example of use**

``San Roque (osm, poly) 78dd704f-12ba-4b38-b887-41efd0d803fb``, a *barangay* `located in the Philippines <https://www.openstreetmap.org/relation/2996306>`__. 

**Spreadsheet column name**

``location:admin_level_10``

**Shortcode**

``l_al10``

**Sources**

No

**Confidence**

No

**Guidance on use**

This field contains the human-readable idenfifier (``location:humane_id:admin``) of the level 10 adminstrative area in which the current Location is situated. Level 10 is a extrenely small adminstrative division, and is rarely specified in freely available geospatial information sources. 

The `schema used by OpenStreetMap <https://wiki.openstreetmap.org/wiki/Tag:boundary=administrative>`__, for example, includes *quartiers* (Belgium), *asumid* (subdistricts of Talinn, Estonia) and *الحي* (neighbourhoods of Damascus, Syria) in the list of types of level 10 administrative area.

This field is programmatically generated using a geospatial query; the Staff Researcher does not enter this manually.

Location: Admin Level 9
-----------------------

**Description**

The administrative level 9 Location within which the present Location is wholly situated.

**Type of field**

Text and numbers; programatically generated.

**Example of use**

``Zone 13 (osm, poly) b858ac31-9e46-4818-b70a-572756d60012``, a *barangay zone* `in the Philippines <https://www.openstreetmap.org/relation/11378938>`__.

**Spreadsheet column name**

``location:admin_level_9``

**Shortcode**

``l_al9``

**Sources**

No

**Confidence**

No

**Guidance on use**

This field contains the human-readable idenfifier (``location:humane_id:admin``) of the level 9 adminstrative area in which the current Location is situated. Level 9 is a extrenely small adminstrative division, and is rarely specified in freely available geospatial information sources. 

The `schema used by OpenStreetMap <https://wiki.openstreetmap.org/wiki/Tag:boundary=administrative>`__, for example, includes *arangay zones* (Philippines), *Sectores y Barrios de 1° nivel* (Venezuela) and *မြို့နယ်* (townships in Myanmar) in the list of types of level 9 administrative area.

This field is programmatically generated using a geospatial query; the Staff Researcher does not enter this manually.

Location: Admin Level 8
-----------------------

**Description**

The administrative level 8 Location within which the present Location is wholly situated.

**Type of field**

Text and numbers; programatically generated.

**Example of use**

``Ermita (osm, poly) 9989ba43-3b03-473a-8226-511a8eb82c3d``, an `administrative district of Manila <https://www.openstreetmap.org/relation/103706#map=15/14.5852/120.9821>`__ in the Philippines.

**Spreadsheet column name**

``location:admin_level_8``

**Shortcode**

``l_al8``

**Sources**

No

**Confidence**

No

**Guidance on use**

This field contains the human-readable idenfifier (``location:humane_id:admin``) of the level 8 adminstrative area in which the current Location is situated. Level 9 is a relatively small adminstrative division, and may not be commonly found in freely available geospatial information sources.

The `schema used by OpenStreetMap <https://wiki.openstreetmap.org/wiki/Tag:boundary=administrative>`__, for example, includes *city corporations* (Bangladesh), *cantons* (Chad) and *kebele* (Ethiopia) in the list of types of level 8 administrative area.

This field is programmatically generated using a geospatial query; the Staff Researcher does not enter this manually.

Location: Admin Level 7
-----------------------

**Description**

The administrative level 7 Location within which the present Location is wholly situated.

**Type of field**

Text and numbers; programatically generated.

**Example of use**

``Wuse II (osm, poly) 111f698a-421e-4fc8-9ace-c0aa62b461b5``

**Spreadsheet column name**

``location:admin_level_7``

**Shortcode**

``l_al7``

**Sources**

No

**Confidence**

No

**Guidance on use**

This field contains the human-readable idenfifier (``location:humane_id:admin``) of the level 7 adminstrative area in which the current Location is situated. Level 7 areas are commonly found in freely available geospatial information sources such as OpenStreetMap.

The `schema used by OpenStreetMap <https://wiki.openstreetmap.org/wiki/Tag:boundary=administrative>`__, for example, includes *sous-préfectures* (Chad), *arrondissements* (in the cities of Ouagadougou and Bobo Dioulasso, Burkina Faso) and *microrregiões* (micro-regions in Brazil) in the list of types of level 7 administrative area.

This field is programmatically generated using a geospatial query; the Staff Researcher does not enter this manually.


Location: Admin Level 6
-----------------------

**Description**

The administrative level 6 Location within which the present Location is wholly situated.

**Type of field**

Text and numbers; programatically generated.

**Example of use**

``Arbinda (osm, poly) 659c231e-eb1e-4c46-a710-b7663ef9f2e0``, a *commune rurale* `in Burkina Faso <https://www.openstreetmap.org/relation/6199315>`__.

**Spreadsheet column name**

``location:admin_level_6``

**Shortcode**

``l_al6``

**Sources**

No

**Confidence**

No

**Guidance on use**

This field contains the human-readable idenfifier (``location:humane_id:admin``) of the level 6 adminstrative area in which the current Location is situated. Level 6 areas are commonly found in freely available geospatial information sources such as OpenStreetMap.

The `schema used by OpenStreetMap <https://wiki.openstreetmap.org/wiki/Tag:boundary=administrative>`__, for example, includes *départments* (Chad), *municipios* (Mexico) and local government areas (Nigeria) in the list of types of level 6 administrative area.

This field is programmatically generated using a geospatial query; the Staff Researcher does not enter this manually.

Location: Admin Level 5
-----------------------

**Description**

The administrative level 5 Location within which the present Location is wholly situated.

**Type of field**

Text and numbers; programatically generated.

**Example of use**

``Seti (osm, poly) 64a4dd09-36d4-4455-bd07-a77addc91946``, a `zone in Nepal <https://www.openstreetmap.org/relation/4583223>`__.

**Spreadsheet column name**

``location:admin_level_5``

**Shortcode**

``l_al5``

**Sources**

No

**Confidence**

No

**Guidance on use**

This field contains the human-readable idenfifier (``location:humane_id:admin``) of the level 5 adminstrative area in which the current Location is situated. Level 5 areas are commonly found in freely available geospatial information sources such as OpenStreetMap.

The `schema used by OpenStreetMap <https://wiki.openstreetmap.org/wiki/Tag:boundary=administrative>`__, for example, includes the *préfecture* (Togo), *Provincial legislative districts* (Philippines) and regions (Côte d'Ivoire) in the list of types of level 5 administrative area.

This field is programmatically generated using a geospatial query; the Staff Researcher does not enter this manually.

Location: Admin Level 4
-----------------------

**Description**

The administrative level 4 Location within which the present Location is wholly situated.

**Type of field**

Text and numbers; programatically generated.

**Example of use**

``Gombe (osm, poly) 06791bb5-c39d-4a32-a05b-f3945c4f83ea``, a `state in Nigeria <https://www.openstreetmap.org/relation/3720422>`__.

**Spreadsheet column name**

``location:admin_level_4``

**Shortcode**

``l_al4``

**Sources**

No

**Confidence**

Text and numbers; programatically generated.

**Guidance on use**

This field contains the human-readable idenfifier (``location:humane_id:admin``) of the level 4 adminstrative area in which the current Location is situated. Level 4 areas are commonly found in freely available geospatial information sources such as OpenStreetMap, and are usually the largest sub-national administrative areas.

The `schema used by OpenStreetMap <https://wiki.openstreetmap.org/wiki/Tag:boundary=administrative>`__, for example, includes provinces (Philippines), states (Nigeria) and *régions* (Mali) in the list of types of level 4 administrative area.

This field is programmatically generated using a geospatial query; the Staff Researcher does not enter this manually.

Location: Admin Level 3
-----------------------

**Description**

The administrative level 3 Location within which the present Location is wholly situated.

**Type of field**

Text and numbers; programatically generated.

**Example of use**

``Central Visayas (osm, poly) 81848978-3998-48bf-87a7-bd1888912aee``, `a region of the Philippines <https://www.openstreetmap.org/relation/3625910>`__.

**Spreadsheet column name**

``location:admin_level_3``

**Shortcode**

``l_al3``

**Sources**

No

**Confidence**

No

**Guidance on use**

This field contains the human-readable idenfifier (``location:humane_id:admin``) of the level 3 adminstrative area in which the current Location is situated. Where defined, level 3 administrative areas are commonly found in freely available geospatial information sources such as OpenStreetMap.

The `schema used by OpenStreetMap <https://wiki.openstreetmap.org/wiki/Tag:boundary=administrative>`__, for example, includes regions (Philippines) in the list of types of level 3 administrative area.

This field is programmatically generated using a geospatial query; the Staff Researcher does not enter this manually.

Location: Admin Level 2
-----------------------

**Description**

The administrative level 2 Location - the international state boundary - within which the present Location is wholly situated.

**Type of field**

Text and numbers; programatically generated.

**Example of use**

``Mali (osm, poly) 8e7b492e-5346-4f43-91a0-55c1f3419468``, ``Sudan (osm, poly) 7117df90-1e52-4726-806a-8e422a0511c6``

**Spreadsheet column name**

``location:admin_level_2``

**Shortcode**

``l_al2``

**Sources**

No

**Confidence**

No

**Guidance on use**

This field contains the human-readable identifier (``location:humane_id:admin``) of the international boundary of a state, also known within the OpenStreetMap schema of administrative areas as a level 2 boundary. This field is programatically generated using a geospatial query; the Staff Researcher does not enter this manually.

Location: Notes
---------------

**Description**

Analysis, commentary and notes about the Location that do not fit into the data structure.

**Type of field**

Text and numbers

**Example of use**

``Sources show Location is within the forested areas between two villages and is derived through geolocation and image analysis of source eeb13cf1-7b98-4075-a09b-530146d2ee37``

**Spreadsheet column name**

``location:notes:admin``

**Shortcode**

``l_n_a``

**Sources**

No

**Confidence**

Yes

**Guidance on use**

We use this field to record information about the Location that is likely to provide useful context, additional information that does not fit into the data structure, and notes about how decisions were made about which data to include. Any sources used should be referenced directly inside the field. Notes are intended to be published.

Location: First Check Time
--------------------------

**Description**

Timestamp of the first time that metadata and geometry for this Location was obtained programatically from OpenStreetMap Overpass API.

**Type of field**

Datetime; programatically generated.

**Example of use**

``2021-02-14T19:39:01Z``

**Spreadsheet column name**

``location:first_check_time``

**Shortcode**

``l_fct``

**Sources**

No

**Confidence**

No

**Guidance on use**

After Staff Researchers have entered the minimum metadata for a Location, we use a script to obtain further information about that object from OpenStreetMap's Overpass API. Overpass gives us the full set of metadata tags for the Location (such as its name in local languages, its last date of update and so on) as well as the geometry that we use to plot the Location on a map. As Location objects can change over time, we keep a record of the date and time at which we first obtained the extended metadata from OSM, as well as the most recent.

This is a programmatically generated field; the Staff Researcher should not enter this directly.

Location: Last Check Time
-------------------------

**Description**

Timestamp of the most recent time that metadata and geometry for this Location was obtained programatically from OpenStreetMap Overpass API.

**Type of field**

Datetime; programatically generated.

**Example of use**

``2021-02-15T20:33:02Z``

**Spreadsheet column name**

``location:last_check_time``

**Shortcode**

``l_lct``

**Sources**

No

**Confidence**

No

**Guidance on use**

After Staff Researchers have entered the minimum metadata for a Location, we use a script to obtain further information about that object from OpenStreetMap's Overpass API. Overpass gives us the full set of metadata tags for the Location (such as its name in local languages, its last date of update and so on) as well as the geometry that we use to plot the Location on a map. As Location objects can change over time, we keep a record of the date and time at which we first obtained the extended metadata from OSM, as well as the most recent.

This is a programmatically generated field; the Staff Researcher should not enter this directly.

Location: Error
---------------

**Description**

Errors encountered during automated processing of a Location.

**Type of field**

Text and numbers; programatically generated.

**Example of use**

``not found``, ``Name changed to 'Arbindah'``

**Spreadsheet column name**

``location:error``

**Shortcode**

``l_err``

**Sources**

No

**Confidence**

No

**Guidance on use**

SFM's ``geo`` tool will use this field to describe any problems it has in obtaining extended metadata about geometry of a Location from OpenStreetMap Overpass API. It populates this field each time the script it run; developers should use the messages to fix the underlying problem with the Location, after which ``geo`` can be re-run. The field is programmatically generated, and the Staff Researcher should not manually enter anything in this field.

Location: "As of" Date
----------------------

**Description**

The date and time of the old version of an OpenStreetMap item that we want to retrieve.

**Type of field**

Datetime

**Example of use**

``2009-03-24T07:50:06Z``

**Spreadsheet column name**

``location:as_of_date``

**Shortcode**

``l_aod``

**Sources**

No

**Confidence**

No

**Guidance on use**

OpenStreetMap is created by its users and every update to any object on the map is recorded and stored. This means you can see the history of an object, and that changes to the map can be observed, discussed and reverted if necessary. The version history of a map object is also important for SFM research, because it may give us a way to access earlier representations of administrative geography. Borders and boundaries change all the time, and these changes are often reflected in the map's history. It also means that we can protect the integrity of our own data by indicating that the Location is based on an OpenStreetMap object *as it was* at a particular date and time. 

The feature of OpenStreetMap that enables this is the repository of `attic data <https://wiki.openstreetmap.org/wiki/Attic_Data>`__, and it can be queried using the Overpass API (directly or by using the SFM ``geo`` tool). The value the Staff Researcher enters into ``location:as_of_date`` must correspond a value listed in the version history of an object. This information is accessible by selecting "View history" on any OSM object, followed by "Download XML". Here is `an example of the attic data for Ermita <https://www.openstreetmap.org/api/0.6/relation/103706/history>`__, a level 9 administrative area in then Philippines.
