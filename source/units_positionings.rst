Unit Positioning
################

The "Unit Positioning" (or just "positioning") type of claim describes the geographic footprint of a specific unit. This includes the areas of operation of a unit, as well as physical infrastructure like posts, bases and camps.

Unit Positioning: Summary of claim attributes
*********************************************

The table below summarises the following dimensions of Unit Positioning claims:

 - Attribute label: a human readable label for the attribute
 - Attribute name: a unique machine-readable name for the attribute, used during data capture
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the field
 - Conformed name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-positioning-fields.csv
   :header-rows: 1
   :delim: tab


Unit Positioning: Details of claim attributes
*********************************************

This section contains further information about each attribute, including descriptions, examples of use, and guidance on use.

Unit Positioning: Positioning Identifier
========================================

Attribute name
~~~~~~~~~~~~~~

``::positioning:id``

Description
~~~~~~~~~~~

A unique 32 character code assigned to each Unit Positioning in the dataset. 

Atrribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``a407be6a-28e6-4237-b4e9-307f27b1202e``

Guidance on use
~~~~~~~~~~~~~~~

This value is a Universally Unique Indentifier (UUID) generated using a computer program. UUIDs must be created easily using either installable or online tools, for example:

- Linux and OSX users: `uuidgen` command line tool.
- On the web: `UUID Generator <https://www.uuidgenerator.net/version>`_.

The field is administrative, providing a reliable way to differentiate between different entities in the SFM data model, in this case the positioning entity.

The Staff Researcher must generate a unique identifying number for that unit and copy it into the attribute ``::positioning:id`` for every claim associated with that specific unit. As the data are ingested into database systems, claims that share the same UUID in ``::positioning:id`` will be aggregated to create a single record for that unit.

During research, particularly when using a spreadsheet, this is a manual, copy-and-paste step and is a potential source of error. The Staff Researcher must be careful never to re-use a UUID anywhere in this or other parts of the dataset.

Unit Positioning: Claim Citation Identifier
===========================================

Attribute name
~~~~~~~~~~~~~~

``::positioning:claim:citation:id``

Description
~~~~~~~~~~~

A unique 32 character code of a citation from a source that evidences the other attribute(s) in this claim.

Atrribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``16d013b5-7073-4446-b22b-46b0edb25632``

Guidance on use
~~~~~~~~~~~~~~~

All claims require a citation, which is a reference to a specific part of a source (for example a page or paragraph reference). The page on citations provides more information about this evidentiary mechanism.

Unit Positioning: Unit Identifier 
=================================

Attribute name
~~~~~~~~~~~~~~

``::positioning:unit:id``

Description
~~~~~~~~~~~

The unique 32 character code assigned to the unit about which a relationship is described in the claim.

Atrribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``a407be6a-28e6-4237-b4e9-307f27b1202e``

Guidance on use
~~~~~~~~~~~~~~~

The UUID inputted into ``::positioning:unit:id`` must correspond to the UUID of a unit that already exists within the dataset.

Unit Positioning: Location Identifier
=====================================

Attribute name
~~~~~~~~~~~~~~

``::positioning:location:id``

Description
~~~~~~~~~~~

Unique 32 character identifier  of a Location where the unit has a "site" or "area of operations".

Attribute type
~~~~~~~~~~~~~~

String in UUID format, selected from ``::location:id``

Status
~~~~~~

This attribute is optional

Example of use
~~~~~~~~~~~~~~

``93dcc4a8-8335-4a21-8372-a151c4972c54`` (which is the raw ID for ``Ikorodu (osm, point) 93dcc4a8-8335-4a21-8372-a151c4972c54``)

Guidance on use
~~~~~~~~~~~~~~~

This attribute is used to store a reference to a location at which the unit has infrastructure, or has operated. The value included in this attributemust be selected from ``::location:id``. For further guidance on the creation, management and use of Locations visit the :ref:`Locations` documentation.


Unit Positioning: Type of Positioning
=====================================

Attribute name
~~~~~~~~~~~~~~

``::positioning:type``

Description
~~~~~~~~~~~

The type of Location of a unit.

Attribute type
~~~~~~~~~~~~~~

String selected from controlled list

Status
~~~~~~

This attribute is optional

Guidance on use
~~~~~~~~~~~~~~~

This field defines the relationship between a unit and a Location. The Staff Researcher must choose one of the two options below:

 - ``site``: the Locationdescribes a "site", such as a settlement or specific point, at which the unit has physical infrastructure like a station, camp, base, office or other facility.
 - ``aoo``: the Location in describes an area, such as an administrative area, where the unit is known to have conducted operations or has terratorial jurisdiction.

The type of Location may be different from the way that the Location is described. For example, a small geographic area like a suburb is a *geometric area* but it could be used to describe a "site" for a unit. Locations themselves are a mix of geographical primatives - points, lines and polygons. This is why :ref:`Locations` are defined independently of their relationship to Units and Incidents.

Unit Positioning: Base Name
===========================

Attribute name
~~~~~~~~~~~~~~

``::positioning:base_name``

Description
~~~~~~~~~~~

A base is a distinctively named building or complex - like a barracks or camp - where the unit is located.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional

Example of use
~~~~~~~~~~~~~~

``Leopard Base``, ``Giwa Barracks``, ``Bonny Camp``

Guidance on use
~~~~~~~~~~~~~~~

The `Unit Positioning: Base Name`_ attribute adds unit-specific context about a Location. This field is used to record data about units that are located in a distinctively-named building or complex.

    For example, ``3 Battalion`` in Nigeria is cited as being based in the ``Lubanga Barracks`` in ``Enugu, Enugu State, Nigeria``.

This field should not be used for anything that matches the name or alias of a unit. For example, ``North Sector Police Station`` should not be put in this field if the name of the unit is ``North Sector Police Station``.


Unit Positioning: Earliest Precise Date
=======================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Unit Positioning: Latest Precise Date
=====================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Unit Positioning: Earliest Imprecise Date
=========================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Unit Positioning: Latest Imprecise Date
=======================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Unit Positioning: Date Range is a Start Date
============================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Unit Positioning: Date Range is an End Date
===========================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Unit Positioning: Research Comments
===================================

Attribute name
~~~~~~~~~~~~~~

``::positioning:claim:comment``

Description
~~~~~~~~~~~

Observations specific to the process of reviewing data in this claim, including fixes, refinements and other suggestions.

Atrribute type
~~~~~~~~~~~~~~

String

Example of use
~~~~~~~~~~~~~~

``Parent unit missing``, ``Geography needs attention``, ``Possible duplicate - merge?``

Guidance on use
~~~~~~~~~~~~~~~

Staff Researchers use this attribute to exchange feedback about the data in the claim. This may included changes needed, references to sources that the owner of the claim might look at, and other observations that can improve the quality of the data. Data stored in this attribute are not intended for publication. The comments attribute is common to all claim types in the SFM data model.

Unit Positioning: Research Owner
================================

Attribute name
~~~~~~~~~~~~~~

``::positioning:claim:researcher``

Description
~~~~~~~~~~~

Initials of Staff Reseacher who created this claim about positioning.

Atrribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``TL``, ``TW``, ``MM``, ``NP``

Guidance on use
~~~~~~~~~~~~~~~

This attribute allows researchers keep track of claims they have created. It  may be used for arbitrary grouping and tagging of specific sets of claims if needed. This type of attribute is common to all types of claim in the SFM data model.

Unit Positioning: Research Status
=================================

Attribute name
~~~~~~~~~~~~~~

``::positioning:claim:status``

Description
~~~~~~~~~~~

The place of the claim in the research workflow.

Atrribute type
~~~~~~~~~~~~~~

String from controlled vocabulary.

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``1``, ``X``

Guidance on use
~~~~~~~~~~~~~~~

Staff Researchers use this attribute to indicate where a claim stands in the research workflow between the first cut of a claim, review by other researchers, and final readiness for use in analysis or for publication. The values to be used in this attribute are taken from the below list:

- ``X``: Claim should be deleted.
- ``0``: First commit. This claim has just been added and needs review.
- ``1``: Fixes needed. A reviewer has made comments that need to be addressed, which will be recorded in the `Unit Positioning: Research Comments`_ attribute.
- ``2``: Fixes made. The owner of this data has addressed the reviewer's comments.
- ``3``: Clean. A final check has been made by a reviewer, and this claim can be used in analysis and can be published.

This type of attribute is common to all claims in the SFM data model.
