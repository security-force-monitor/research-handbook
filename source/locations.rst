Locations
=========

What are locations?
-------------------

Text on what locations are.


Location: Research Status
-------------------------

**Description**

The place of a row of data in the research workflow.

**Type of field**

Number range from 0 to 3

**Example of use**

``3```

**Spreadsheet column name**

``location:status:admin``

**Shortcode**

``l_sta_a``

**Sources**

No

**Confidence**

No

**Guidance on use**

This administrative field is only used in spreadsheets. Staff Researchers use this field to indicate where a row of data stands in the research workflow between the first cut of a row of data, review by other researchers, and final readiness for publication. Values in this field are taken from the below controlled list:

- `0`: First commit. This row of data has just been added and needs review.
- `1`: Fixes needed. A reviewer has made comments that need to be addressed, which will be recorded in the ``locations:comments:admin`` field.
- `2`: Fixes made. The owner of this data has addressed the reviewer's comments.
- `3`: Clean. A final check has been made by a reviewer, and this row of data can be published.

Location: Research Comments
------------------

**Description**

Observations specific to the process of reviewing data in this row, including fixes, refinements and other suggestions.

**Type of field**

Text

**Example of use**

``Location does not exist in Open Street Map - alternate gazeteer needed``, ``Possible duplicate of location 1bbdfd2b-2d7c-4677-8e1f-8fa5b0367cfe``

**Spreadsheet column name**

``location:comments:admin``

**Shortcode**

``l_c_a``

**Sources**

No

**Confidence**

No

**Guidance on use**

This is an administrative field specific to data created in spreadsheets. Staff researchers use it to pass on feedback about the data in the row. This may included changes needed to specific fields in that row, references to sources that the owner of the row might look at, and other observations that can improve the quality of the data. Data in this field are not intended for publication.

Location: Unique Identifier
---------------------------

**Description**

A unique 36-character code assigned to each location in the dataset.

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

This value is a Universally Unique Indentifier (UUID) generated using a computer program. UUIDs can be created easily using either installable or online tools, for example:
  - Linux and OSX users: `uuidgen` command line tool.
  - On the web: `UUID Generator <https://www.uuidgenerator.net/version>`_.

The field is administrative, providing a reliable way to differentiate between different locations. 

When a new location is created in a spreadsheet, the Staff Researcher must generate a unique identifying number for the locations and copy it into the field ``location:id:admin``. This manual, copy-and-paste step is a potential source of error and the Staff Researcher must be careful not to re-use a UUID.

 Bulk updates made to WhoWasInCommand.com by spreadsheet import are based on the values in this field. For example, changes made in the row ``a407be6a-28e6-4237-b4e9-307f27b120e`` in the spreadsheet will be applied to the location with that UUID in WhoWasInCommand.

Location: "Humane" Unique Identifier
------------------------------------

**Description**

A human-readable identifier for each location in the dataset.


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

Location: Gazeteer Object Name
------------------------------

**Description**

The name of the location as specified in the gazeteer from which it is taken.

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


Location: Gazeteer Object Identifier
-----------------------------------

**Description**

The identifier for the location as specified in the gazeteer from which it is taken.

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


Location: Gazeteer Object Geometry Type
------------------------------

**Description**

The two-dimensional geometric primative of the location, as provided by the gazeteer from which it is taken.

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

This field used a controlled vocabulary to describe the type of geometry used to represent the location on a map. The Staff Researcher can choose from the following three options?

 - ``point``: the location is a single distinct point on a map, represented by a single pair of geographic coordinates.
 - ``poly``: the location is a closed area on a map, its boundary described by a sequence of geographic coordinates.
 - ``line``: the location is a line on a map, described by a sequence of geographic coordinates. A ``line`` may also be closed.

The gazeteer used as the source of geometry may used different terminology to describe the location. For example, in Open Street Map the boundaries of administrative areas (such as counties or states) `are described <https://wiki.openstreetmap.org/wiki/Relation>`_ using an object called a ``relation``; although this can be a complex mix of different objects, for our purposes it is a ``poly`` because it describes an area.

Along with the values in ``location:name``, ``location:id`` and ``location:id:admin`` the value entered in ``location:geo_type`` becomes part of the Location's "humane id", a human-readable unique identified that acts as a reference for a location when it is used in other parts of the data model (like ``units`` for example).

Location: Origin
----------------

**Description**

The service that provides information about this location.

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

SFM uses a combination of manual data entry and automated processes to manage location information. The values in ``location:origin`` identify where automation tools should go to obtain spatial information about an object. For example, if the value ``osm`` is entered in ``location:origin`` this indicates that the automation tool should query Open Street Map in order to obtain spatial information about a location. If ``osm`` were set, then the values in ``location:name`` and ``location:id`` would correspond to the object name and ID number in Open Street Map. 

Location: Source
---------------

**Description**

The UUID of the access point in the source that provides information about the location.

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

SFM uses a number of different sources of geographical information, including Open Street Map, data provided by the United Nations through the Humanitarian Data Exchange, and locations that are arbitrarily defined during research. Staff Researchers should use the ``location:source`` field to make note of exactly which dataset has been used as a source of this location. The UUID will reference an entry in the :ref:`Sources` dataset.

Location: Country
-----------------

**Description**

Country in which the location is situated.

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

Values for this field are the English language full names of countries contained in the list of ISO 3166-1 alpha-2 codes, which can be found (`on the ISO website <https://www.iso.org/obp/ui/#search/code/>`__ and on `Wikipedia <https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Officially_assigned_code_elements>`__).

Location: Admin Level
---------------------

**Description**
**Type of field**
**Example of use**
**Spreadsheet column name**

``location:admin_level``

**Shortcode**

``l_al``

**Sources**
**Confidence**
**Guidance on use**


Location: Admin Level 10
------------------------

**Description**
**Type of field**
**Example of use**
**Spreadsheet column name**

``location:admin_level_10``

**Shortcode**

``l_al10``

**Sources**
**Confidence**
**Guidance on use**


Location: Admin Level 9
-----------------------

**Description**
**Type of field**
**Example of use**
**Spreadsheet column name**

``location:admin_level_9``

**Shortcode**

``l_al9``

**Sources**
**Confidence**
**Guidance on use**


Location: Admin Level 8
-----------------------

**Description**
**Type of field**
**Example of use**
**Spreadsheet column name**

``location:admin_level_8``

**Shortcode**

``l_al8``

**Sources**
**Confidence**
**Guidance on use**


Location: Admin Level 7
-----------------------

**Description**
**Type of field**
**Example of use**
**Spreadsheet column name**

``location:admin_level_7``

**Shortcode**

``l_al7``

**Sources**
**Confidence**
**Guidance on use**


Location: Admin Level 6
-----------------------

**Description**
**Type of field**
**Example of use**
**Spreadsheet column name**

``location:admin_level_6``

**Shortcode**

``l_al6``

**Sources**
**Confidence**
**Guidance on use**


Location: Admin Level 5
-----------------------

**Description**
**Type of field**
**Example of use**
**Spreadsheet column name**

``location:admin_level_5``

**Shortcode**

``l_al5``

**Sources**
**Confidence**
**Guidance on use**


Location: Admin Level 4
-----------------------

**Description**
**Type of field**
**Example of use**
**Spreadsheet column name**

``location:admin_level_4``

**Shortcode**

``l_al4``

**Sources**
**Confidence**
**Guidance on use**


Location: Admin Level 3
-----------------------

**Description**
**Type of field**
**Example of use**
**Spreadsheet column name**

``location:admin_level_3``

**Shortcode**

``l_al3``

**Sources**
**Confidence**
**Guidance on use**


Location: Admin Level 2
-----------------------

**Description**
**Type of field**
**Example of use**
**Spreadsheet column name**

``location:admin_level_2``

**Shortcode**

``l_al2``

**Sources**
**Confidence**
**Guidance on use**


Location: Notes
---------------

**Description**
**Type of field**
**Example of use**
**Spreadsheet column name**

``location:notes:admin``

**Shortcode**

``l_n_a``

**Sources**
**Confidence**
**Guidance on use**

Location: First Check Time
--------------------------

**Description**
**Type of field**
**Example of use**
**Spreadsheet column name**

``location:first_check_time``

**Shortcode**

``l_fct``

**Sources**
**Confidence**
**Guidance on use**


Location: Last Check Time
-------------------------

**Description**
**Type of field**
**Example of use**
**Spreadsheet column name**

``location:last_check_time``

**Shortcode**


``l_lct``

**Sources**
**Confidence**
**Guidance on use**


Location: Error
---------------

**Description**
**Type of field**
**Example of use**
**Spreadsheet column name**

``location:error``

**Shortcode**

``l_err``

**Sources**
**Confidence**
**Guidance on use**


Location: "As of" Date
----------------------

**Description**
**Type of field**
**Example of use**
**Spreadsheet column name**

``location:as_of_date``

**Shortcode**

``l_aod``

**Sources**
**Confidence**
**Guidance on use**
