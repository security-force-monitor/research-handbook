Location
########

Locations are unique places or positions. A named town or city can be a Location, as can an administrative area like a county, district or governorate. In fact, anything that can be drawn on a map can be a Location: a specific point, a section of a road, a military line of control, and so on.


Location: Summary of attributes
*******************************

The table below summarizes the following dimensions of Locations:

 - Attribute label: a human readable label for the attribute
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the attribute
 - Key name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-locations-attributes.csv
   :header-rows: 1

Location: Details of attributes
*******************************

This section contains further information about each attribute, including descriptions, examples of use, and Guidance on use.


status:meta
===========

Description
~~~~~~~~~~~

A field that classifies the data.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:claim/statuses``

Example of use
~~~~~~~~~~~~~~

``accepted``, ``conflict``, ``work_needed``, ``issue``

Guidance on use
~~~~~~~~~~~~~~~

Data are marked ``accepted`` when all of the data can be entered in accordance with the guidance of this handbook. The ``conflict`` flag is used whenever there is a conflicts with another location and a review shows it to be the incorrect or false location. A :ref:`public_notes:meta <notes-location>` should always accompany any ``conflict`` flag.

If the data itself cannot be brought into the SFM standard the flag ``issue`` should be used. Finally, if it cannot be established whether a location should be flagged as ``accepted`` or ``conflict`` then the flag ``work_needed`` should be used as additional research is needed.


researcher:meta
===============

Description
~~~~~~~~~~~

Field for initials or other identifier of researcher who last entered data for the location.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:meta/researchers``

Example of use
~~~~~~~~~~~~~~

``TW``, ``Jane_Doe``, ``G1`` 

Guidance on use
~~~~~~~~~~~~~~~

Every researcher should use this field to mark the claims that they have entered. Anytime a researcher modifies any data for an existing claim they should update this field so that any questions can be directed to the right person and the flow of work can be better tracked. 


internal_comments:meta
======================

Description
~~~~~~~~~~~

A field for temporary comments or notes for the researcher or research team working on the claim.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:meta/internal-comments``

Example of use
~~~~~~~~~~~~~~

``Come back to this to determine date for claim``

Guidance on use
~~~~~~~~~~~~~~~

Researchers may use this field to make temporary notes or leave temporary comments intended for others in the research team about a claim. These should eventually be addressed and the field cleared by the researcher or research team. If the claim needs an explanatory note or comment to be better understood, then that should be entered in the :ref:`public_notes:meta <notes-location>` field.


citation:refs:location
======================

Description
~~~~~~~~~~~

Field unique 32 character code assigned to citation(s) evidencing the location.

Attribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed

Example of use
~~~~~~~~~~~~~~

``69dba35b-2b70-47cf-bfda-f80225f652c6``, ``4e99308c-f9c0-49e8-b97b-14c1e7bcb99d;bedf57b2-c20b-41e3-9dcf-b7b065eaa3b7``

Guidance on use
~~~~~~~~~~~~~~~

Locations are drawn from an external gazeeter or geographic database, and because of this they do not require a citation. However, as the location data model is updated citations may be needed to evidence the creation and disbandment of locations, and perhaps other features as well which are not generally included in gazeeters or geographic databases. When two or more citations are needed to evidence a location then a corresponding explanatory note should be entered in the :ref:`public_notes:meta <notes-location>` field. This field is for the Universally Unique Identifier (UUID) for each citation, found in the :ref:`ref:source:access_point_id:admin` field in the Sources sheet. When multiple citations are needed every UUID should be semi-colon separated.


id:entity
=========

Description
~~~~~~~~~~~

A unique 36-character code assigned to each Location in the dataset.

Type of attribute
~~~~~~~~~~~~~~~~~

String in UUID format.

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:entity/id``

Example of use
~~~~~~~~~~~~~~

``5f55f3f1-ed83-4766-b26a-fd11bedc398c``

Guidance on use
~~~~~~~~~~~~~~~

This value is a Universally Unique Identifier (UUID) generated using a computer program. Every location has a UUID to distinguish it from any other location. This field is used in data entry for :ref:`incidents` in :ref:`incident:location:refs:assertion` and :ref:`positionings` in :ref:`positioning:location:refs:assertion`.


location:humane_id:qa
=====================

Description
~~~~~~~~~~~

A human-readable unique identifier for each Location in the dataset.

Type of attribute
~~~~~~~~~~~~~~~~~

Text string.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``Ta'izz Governorate (osm, poly) 5c35b342-0b5e-4648-86cd-7ad730d647fa``

Guidance on use
~~~~~~~~~~~~~~~

Entries for the :ref:`location:humane_id:qa` field should combine information from several other location fields to give a researcher a quick, human readable way to understand a location. Best practice is to include the :ref:`name:annotation <location-name-annotation>`, :ref:`origin:location`, :ref:`geo_type:qa` and :ref:`id:entity` as this highlights the most important information while also creating a unique name due to the inclusion of :ref:`id:entity`. SFM adopts this approach with :ref:`location:humane_id:qa` with entries in the field following the below format:

.. admonition:: Example
  
  The value ``Ta'izz Governorate (osm, poly) 5c35b342-0b5e-4648-86cd-7ad730d647fa``, which is a combination of multiple fields: ``name:annotation`` (``origin:location``, ``geo_type:qa``) ``id:entity``, tells us that the name of the place is ``Ta'izz Governorate``, that it is a Location found in ``osm`` (short for "OpenStreetMap") that it denotes an area (``poly``); the UUID provides the hard link to a specific attribute in the Location table.

.. _location-name-annotation:

name:annotation
===============

Description
~~~~~~~~~~~

The name of the Location as specified in the source of geospatial information from which it is taken.

Type of attribute
~~~~~~~~~~~~~~~~~

Text string.

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:annotation/name``

Example of use
~~~~~~~~~~~~~~

``Ta'izz Governorate``

Guidance on use
~~~~~~~~~~~~~~~

The value in :ref:`name:annotation <location-name-annotation>` is to be taken directly from the geospatial data source. For example, if a Location is derived from OpenStreetMap, we take the value from OSM's own "name" attribute and place it in :ref:`name:annotation <location-name-annotation>`. Along with :ref:`origin_id:location` and :ref:`geo_type:qa`, :ref:`name:annotation <location-name-annotation>` is needed for automation tools to identify the object within the geospatial data source. Where a Location is arbitrarily-defined, or is derived from a data source that does not provide a name, the Staff Researcher can provide one.


origin:location
===============

Description
~~~~~~~~~~~

The geospatial information source that provides information about this Location.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:location/origin``

Example of use
~~~~~~~~~~~~~~

``osm``, ``sfm``, ``hdx``, ``mimu``, ``khrg``

Guidance on use
~~~~~~~~~~~~~~~

The values in :ref:`origin:location` identify where automation tools should go to obtain spatial information about an object. For example, if the value ``osm`` is entered in :ref:`origin:location` this indicates that the automation tool should query OpenStreetMap in order to obtain spatial information about a Location. If ``osm`` were set, then the values in :ref:`name:annotation <location-name-annotation>` and :ref:`origin_id:location` would correspond to the object name and ID number in OpenStreetMap. Locations can be derived from comprehensive online services, as well as other sources like locally-held ``.shp`` or ``.kml`` files. The number of origins is unlimited.


origin_id:location
==================

Description
~~~~~~~~~~~

The identifier for the Location as specified in the source of geospatial information from which it is taken.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:location/origin-id``

Example of use
~~~~~~~~~~~~~~

``383895``

Guidance on use
~~~~~~~~~~~~~~~

The value in :ref:`origin_id:location` is to be taken directly from the geospatial data source. For example, if a Location is derived from OpenStreetMap, we take the value from OSM's "id" attribute and place it in the :ref:`origin_id:location` attribute. Along with :ref:`name:annotation <location-name-annotation>` and :ref:`geo_type:qa`, :ref:`origin_id:location` is needed in order for automation tools to identify the object within the geospatial data source. Where a Location is arbitrarily defined, or is derived from a data source that does not provide a ID number, the Staff Researcher can provide one.


geo_type:qa
===========

Description
~~~~~~~~~~~

The two-dimensional geometric primitive of the Location, as defined in the source of geospatial information from which it is taken.

Type of attribute
~~~~~~~~~~~~~~~~~

Text

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:location/geo-type``

Example of use
~~~~~~~~~~~~~~

``point``, ``poly``, ``line``

Guidance on use
~~~~~~~~~~~~~~~

This attribute used a controlled vocabulary to describe the type of geometry used to represent the Location on a map. The Staff Researcher can choose from the following three options:

 - ``point``: the Location is a single distinct point on a map, represented by a single pair of geographic coordinates.
 - ``poly``: the Location is a closed area on a map, its boundary described by a sequence of geographic coordinates.
 - ``line``: the Location is a line on a map, described by a sequence of geographic coordinates. A ``line`` may also be closed.

The gazeteer used as the source of geometry may used different terminology to describe the Location. For example, in OpenStreetMap the boundaries of administrative areas (such as counties or states) `are described <https://wiki.openstreetmap.org/wiki/Relation>`_ using an object called a "relation"; although this can be a complex mix of different objects, for our purposes it is a ``poly`` because it describes an area.


country:annotation
==================

Description
~~~~~~~~~~~

Country in which the Location is situated.

Type of attribute
~~~~~~~~~~~~~~~~~

Text, controlled vocabulary

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:annotation/country``

Example of use
~~~~~~~~~~~~~~

``ye``, ``ng``, ``mm``

Guidance on use
~~~~~~~~~~~~~~~

Values for this attribute are the ISO 3166-1 alpha-2 country codes, which can be found `on the ISO website <https://www.iso.org/obp/ui/#search/code/>`__.


geometry:ref:entity
===================

Description
~~~~~~~~~~~

The unique id generated by importer for the geojson for this Location.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:location/geo-feature:ref``

Example of use
~~~~~~~~~~~~~~

``724f89db-98b3-5f5e-9947-7f50c049e5ea``

Guidance on use
~~~~~~~~~~~~~~~

SFM's location database gives a separate UUID for every geojson which must be matched to the location. This field enables the geographic data used to generate locations to be unique, and to connect these unique geojson to the data in the Locations sheet.


location:explicit_parent:annotation
===================================

Description
~~~~~~~~~~~

Manually entered location which contains the location.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:annotation/location:explicit-parent``

Example of use
~~~~~~~~~~~~~~

``Ilocos Norte (psa, poly) ceffdf36-f14b-410c-9fde-4c39f5a87c7c``

Guidance on use
~~~~~~~~~~~~~~~
If a geographic dataset does not establish whether locations are within one another, this field may be used to manually create the hierarchy between locations. The :ref:`location:humane_id:qa` should be used in this field.


location:admin_level:qa
=======================

Description
~~~~~~~~~~~

The administrative level of the Location described in the attribute, if defined in the source of geographical information from which the Location is derived.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``2``

Guidance on use
~~~~~~~~~~~~~~~

In every country, places are organized hierarchically based on their administrative hierarchy. This feature passes into geographical information systems. At the top of the hierarchy rests the international boundary and capital city of a country; beneath this, there are sub-national divisions like states or provinces, with their respective capitals, followed by smaller and smaller administrative divisions districts, counties, municipalities, towns, suburbs, wards and so on. Different countries have different ways of describing these political and administrative divisions, but they are largely hierarchical and can be cross-compared. Knowing the level(s) at which a Location sits in the overall hierarchy provides us with a useful way to group and understand Locations.

The attribute :ref:`location:admin_level:qa` is drawn from the geographic source, such as the UN Office for the Coordination of Humanitarian Affairs (OCHA) schema which `can be found here <https://knowledge.base.unocha.org/wiki/spaces/imtoolbox/pages/3942121476/COD-AB+lines+layers>`__. If the source lacks its own hierarchy then we use OpenStreetMap, which has a `comprehensive table <https://wiki.openstreetmap.org/wiki/Tag:boundary=administrative>`__ that matches the divisions that exist in every country.


location:admin_level_10:qa
==========================

Description
~~~~~~~~~~~

The administrative level 10 Location within which the present Location is wholly situated.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``Byaw Taw Wa Ward (osm, poly) 119ce62f-0caa-4c0d-bb30-d02f58364814``, a ward `in Myanmar <https://www.openstreetmap.org/relation/9957339>`__.

Guidance on use
~~~~~~~~~~~~~~~

This attribute contains the human-readable identifier (:ref:`location:humane_id:qa`) of the level 10 administrative area in which the current Location is situated. Level 10 is an extremely small administrative division and is rarely specified in freely available geospatial information sources. 


location:admin_level_9:qa
=========================

Description
~~~~~~~~~~~

The administrative level 9 Location within which the present Location is wholly situated.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``Zone 13 (osm, poly) b858ac31-9e46-4818-b70a-572756d60012``, a *barangay zone* `in the Philippines <https://www.openstreetmap.org/relation/11378938>`__.

Guidance on use
~~~~~~~~~~~~~~~

This attribute contains the human-readable identifier (:ref:`location:humane_id:qa`)  of the level 9 administrative area in which the current Location is situated. Level 9 is an extremely small administrative division and is rarely specified in freely available geospatial information sources. 


location:admin_level_8:qa
=========================

Description
~~~~~~~~~~~

The administrative level 8 Location within which the present Location is wholly situated.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``Ermita (osm, poly) 9989ba43-3b03-473a-8226-511a8eb82c3d``, an `administrative district of Manila <https://www.openstreetmap.org/relation/103706#map=15/14.5852/120.9821>`__ in the Philippines.

Guidance on use
~~~~~~~~~~~~~~~

This attribute contains the human-readable identifier (:ref:`location:humane_id:qa`) of the level 8 administrative area in which the current Location is situated. Level 8 is a relatively small administrative division, and may not be commonly found in freely available geospatial information sources.


location:admin_level_7:qa
=========================

Description
~~~~~~~~~~~

The administrative level 7 Location within which the present Location is wholly situated.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``Wuse II (osm, poly) 111f698a-421e-4fc8-9ace-c0aa62b461b5``

Guidance on use
~~~~~~~~~~~~~~~

This attribute contains the human-readable identifier (:ref:`location:humane_id:qa`) of the level 7 administrative area in which the current Location is situated. Level 7 areas are commonly found in freely available geospatial information sources such as OpenStreetMap.


location:admin_level_6:qa
=========================

Description
~~~~~~~~~~~

The administrative level 6 Location within which the present Location is wholly situated.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``Arbinda (osm, poly) 659c231e-eb1e-4c46-a710-b7663ef9f2e0``, a *commune rurale* `in Burkina Faso <https://www.openstreetmap.org/relation/6199315>`__.

Guidance on use
~~~~~~~~~~~~~~~

This attribute contains the human-readable identifier (:ref:`location:humane_id:qa`) of the level 6 administrative area in which the current Location is situated. Level 6 areas are commonly found in freely available geospatial information sources such as OpenStreetMap.


location:admin_level_5:qa
=========================

Description
~~~~~~~~~~~

The administrative level 5 Location within which the present Location is wholly situated.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``Seti (osm, poly) 64a4dd09-36d4-4455-bd07-a77addc91946``, a `zone in Nepal <https://www.openstreetmap.org/relation/4583223>`__.

Guidance on use
~~~~~~~~~~~~~~~

This attribute contains the human-readable identifier (:ref:`location:humane_id:qa`) of the level 5 administrative area in which the current Location is situated. Level 5 areas are commonly found in freely available geospatial information sources such as OpenStreetMap.


location:admin_level_4:qa
=========================

Description
~~~~~~~~~~~

The administrative level 4 Location within which the present Location is wholly situated.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``Gombe (osm, poly) 06791bb5-c39d-4a32-a05b-f3945c4f83ea``, a `state in Nigeria <https://www.openstreetmap.org/relation/3720422>`__.

Guidance on use
~~~~~~~~~~~~~~~

This attribute contains the human-readable identifier (:ref:`location:humane_id:qa`) of the level 4 administrative area in which the current Location is situated. Level 4 areas are commonly found in freely available geospatial information sources such as OpenStreetMap, and are usually the largest sub-national administrative areas.


location:admin_level_3:qa
=========================

Description
~~~~~~~~~~~

The administrative level 3 Location within which the present Location is wholly situated.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``Central Visayas (osm, poly) 81848978-3998-48bf-87a7-bd1888912aee``, `a region of the Philippines <https://www.openstreetmap.org/relation/3625910>`__.

Guidance on use
~~~~~~~~~~~~~~~

This attribute contains the human-readable identifier (:ref:`location:humane_id:qa`) of the level 3 administrative area in which the current Location is situated. Where defined, level 3 administrative areas are commonly found in freely available geospatial information sources such as OpenStreetMap.


location:admin_level_2:qa
=========================

Description
~~~~~~~~~~~

The administrative level 2 location within which the present Location is wholly situated.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``Mali (osm, poly) 8e7b492e-5346-4f43-91a0-55c1f3419468``, ``Sudan (osm, poly) 7117df90-1e52-4726-806a-8e422a0511c6``

Guidance on use
~~~~~~~~~~~~~~~

This attribute contains the human-readable identifier (:ref:`location:humane_id:qa`) of the level 2 administrative level, which for the OpenStreetMap schema is the international boundary of a country.


location:admin_level_1:qa
=========================

Description
~~~~~~~~~~~

The administrative level 1 Location within which the present Location is wholly situated.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``Dodoma (ocha, poly) 8f9d115d-ef26-4d59-85a0-905cd9582adf``

Guidance on use
~~~~~~~~~~~~~~~

This attribute contains the human-readable identifier (:ref:`location:humane_id:qa`) of the level 1 administrative level. The UN Office for the Coordination of Humanitarian Affairs (OCHA) defines the level 1 administrative level as the highest sub national boundaries of a country (OSM generally uses level 4 for these sub national boundaries). 


location:admin_level_0:qa
=========================

Description
~~~~~~~~~~~

The administrative level 0 Location - the international state boundary for OCHA - within which the present Location is wholly situated.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``United Republic of Tanzania (ocha, poly) 6f08e803-b1d8-4b8f-899a-1e20c4174441``

Guidance on use
~~~~~~~~~~~~~~~

This attribute contains the human-readable identifier (:ref:`location:humane_id:qa`) of the international boundary of a country as defined in the UN Office for the Coordination of Humanitarian Affairs (OCHA) schema.


first_precise:range
===================

Description
~~~~~~~~~~~

The first precise date in the range.

Type of attribute
~~~~~~~~~~~~~~~~~

String-date

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed

Example of use
~~~~~~~~~~~~~~

n/a - proposed

Guidance on use
~~~~~~~~~~~~~~~

Locations are treated as entities, and not claims in the data model, which means they do not require citations as the location entity is drawn from the geographic database. However, geographic databases generally do not evidence the dates a location was created, or disbanded. This information comes from other citations, which of course may have claims are in conflict with one another. Additional work is needed to update how locations are managed to capture this complexity clearly and accurately. More background on dates can be found in the section :ref:`How Dates Work`.


last_precise:range
==================

Description
~~~~~~~~~~~

The last precise date in the range.

Type of attribute
~~~~~~~~~~~~~~~~~

String-date

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed

Example of use
~~~~~~~~~~~~~~

n/a - proposed

Guidance on use
~~~~~~~~~~~~~~~

Locations are treated as entities, and not claims in the data model, which means they do not require citations as the location entity is drawn from the geographic database. However, geographic databases generally do not evidence the dates a location was created, or disbanded. This information comes from other citations, which of course may have claims are in conflict with one another. Additional work is needed to update how locations are managed to capture this complexity clearly and accurately. More background on dates can be found in the section :ref:`How Dates Work`.


first_imprecise:range
=====================

Description
~~~~~~~~~~~

The first imprecise date in the range.

Type of attribute
~~~~~~~~~~~~~~~~~

String-date

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed

Example of use
~~~~~~~~~~~~~~

n/a - proposed

Guidance on use
~~~~~~~~~~~~~~~

Locations are treated as entities, and not claims in the data model, which means they do not require citations as the location entity is drawn from the geographic database. However, geographic databases generally do not evidence the dates a location was created, or disbanded. This information comes from other citations, which of course may have claims are in conflict with one another. Additional work is needed to update how locations are managed to capture this complexity clearly and accurately. More background on dates can be found in the section :ref:`How Dates Work`.


last_imprecise:range
====================

Description
~~~~~~~~~~~

The last imprecise date in the range.

Type of attribute
~~~~~~~~~~~~~~~~~

String-date

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed

Example of use
~~~~~~~~~~~~~~

n/a - proposed

Guidance on use
~~~~~~~~~~~~~~~

Locations are treated as entities, and not claims in the data model, which means they do not require citations as the location entity is drawn from the geographic database. However, geographic databases generally do not evidence the dates a location was created, or disbanded. This information comes from other citations, which of course may have claims are in conflict with one another. Additional work is needed to update how locations are managed to capture this complexity clearly and accurately. More background on dates can be found in the section :ref:`How Dates Work`.


starting:range
==============

Description
~~~~~~~~~~~

Flag for if first date in range is the start date or not.

Type of attribute
~~~~~~~~~~~~~~~~~

Y/N boolean

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed

Example of use
~~~~~~~~~~~~~~

n/a - proposed

Guidance on use
~~~~~~~~~~~~~~~

Locations are treated as entities, and not claims in the data model, which means they do not require citations as the location entity is drawn from the geographic database. However, geographic databases generally do not evidence the dates a location was created, or disbanded. This information comes from other citations, which of course may have claims are in conflict with one another. Additional work is needed to update how locations are managed to capture this complexity clearly and accurately. More background on dates can be found in the section :ref:`How Dates Work`.


ending:range
============

Description
~~~~~~~~~~~

Flag for if last date in range is the start date or not.

Type of attribute
~~~~~~~~~~~~~~~~~

Y/N boolean

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed

Example of use
~~~~~~~~~~~~~~

n/a - proposed

Guidance on use
~~~~~~~~~~~~~~~

Locations are treated as entities, and not claims in the data model, which means they do not require citations as the location entity is drawn from the geographic database. However, geographic databases generally do not evidence the dates a location was created, or disbanded. This information comes from other citations, which of course may have claims are in conflict with one another. Additional work is needed to update how locations are managed to capture this complexity clearly and accurately. More background on dates can be found in the section :ref:`How Dates Work`.


starting_context:range
======================

Description
~~~~~~~~~~~

Simple description of start date.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed

Example of use
~~~~~~~~~~~~~~

n/a - proposed

Guidance on use
~~~~~~~~~~~~~~~

Locations are treated as entities, and not claims in the data model, which means they do not require citations as the location entity is drawn from the geographic database. However, geographic databases generally do not evidence the dates a location was created, or disbanded. This information comes from other citations, which of course may have claims are in conflict with one another. Additional work is needed to update how locations are managed to capture this complexity clearly and accurately. More background on dates can be found in the section :ref:`How Dates Work`.


ending_context:range
====================

Description
~~~~~~~~~~~

Simple description of end date.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed

Example of use
~~~~~~~~~~~~~~

n/a - proposed

Guidance on use
~~~~~~~~~~~~~~~

Locations are treated as entities, and not claims in the data model, which means they do not require citations as the location entity is drawn from the geographic database. However, geographic databases generally do not evidence the dates a location was created, or disbanded. This information comes from other citations, which of course may have claims are in conflict with one another. Additional work is needed to update how locations are managed to capture this complexity clearly and accurately. More background on dates can be found in the section :ref:`How Dates Work`.


.. _notes-location:

public_notes:meta
=================

Description
~~~~~~~~~~~

Additional context or details about the claim for a public audience.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:meta/public-notes``

Example of use
~~~~~~~~~~~~~~

``Citation @3c981094-fb7b-4b78-b8f6-b525a03f72b5, published on 15 July 2019, states that numerous military appointments occurred "last week". This is understood to mean the week starting the previous Sunday 7 July 2019 through Saturday 13 July 2019.``

Guidance on use
~~~~~~~~~~~~~~~

This field should be used whenever any claim requires additional explanation because for a general reader the claim is not clearly and directly stated in the citation. For the example of use above a citation published on 15 July 2019 refers to something happening "last week" and as a result a researcher has determined the previous Sunday 7 July 2019 through Saturday 13 July 2019 should be entered into the appropriate fields of ``first_imprecise:range`` and ``last_imprecise:range``. That range would not be immediately clear to a public audience since neither date is directly referenced in the text of the citation. As a result, the researcher should explain how that date range was evidenced by the citation.


type:entity
===========

Description
~~~~~~~~~~~

Specifies the type of entity.

Attribute type
~~~~~~~~~~~~~~

Text, controlled vocabulary.

Status
~~~~~~

This field is required.

Key name
~~~~~~~~

``:entity/type``

Example of use
~~~~~~~~~~~~~~

``claim``

Guidance on use
~~~~~~~~~~~~~~~

For a :ref:`location` the only entry allowed for this field is ``location``.
