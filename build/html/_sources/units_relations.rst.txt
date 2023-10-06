Unit Relation
#############

The "Unit Relation" (or just "Relation") claim type describes the relationships between units and the position of a unit in a hierarchical structure of a branch of the security and defence forces of a specific country. "Unit Relation" claims also describe clusters of units, such as those found in joint operations or international peacekeeping missions.

Unit Relation: Summary of claim attributes
******************************************

The table below summarises the following dimensions of Unit Relation claims:

 - Attribute label: a human readable label for the attribute
 - Attribute name: a unique machine-readable name for the attribute, used during data capture
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the field
 - Conformed name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-relation-fields.csv
   :header-rows: 1
   :delim: tab


Unit Relation: Details of claim attributes
******************************************

This section contains further information about each attribute, including descriptions, examples of use, and guidance on use.

Unit Relation: Relation Identifier
==================================

Attribute name
~~~~~~~~~~~~~~

``::relation:id``

Description
~~~~~~~~~~~

A unique 32 character code assigned to each relation in the dataset.

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

The field is administrative, providing a reliable way to differentiate between different entities in the SFM data model, in this case a unit relation entity.

The Staff Researcher must generate a unique identifying number for that relationand copy it into the attribute ``::relation:id`` for every claim associated with that specific unit. As the data are ingested into database systems, claims that share the same UUID in ``::relation:id`` will be aggregated to create a single record for that relation.

During research, particularly when using a spreadsheet, this is a manual, copy-and-paste step and is a potential source of error. The Staff Researcher must be careful never to re-use a UUID anywhere in this or other parts of the dataset.

Unit Relation: Claim Citation Identifier
========================================

Attribute name
~~~~~~~~~~~~~~

``::relation:claim:citation:id``

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

Unit Relation: Unit Identifier
==============================

Attribute name
~~~~~~~~~~~~~~

``::relation:unit:id``

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

The UUID inputted into ``::relation:unit:id`` must correspond to the UUID of a unit that already exists within the Unit Identity attribute `Unit: Name`_. This attribute denotes one side of a relationship between units; the other is denoted in the attribute `Unit Relation: Related Unit Identifier`_. The nature of the relationship is clarified further using the `Unit Relation: Type of Relation`_ and `Unit Relation: Relation Classification`_ attributes.

Unit Relation: Related Unit Identifier
======================================

Attribute name
~~~~~~~~~~~~~~

``::relation:related_unit:id``

Description
~~~~~~~~~~~

The unique 32 character code of the immediate superior or parent unit of the current unit, or the unit to which the current unit is a member.

Attribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``67eff2ed-2321-464f-8f85-da04db2cd1ec``

Guidance on use
~~~~~~~~~~~~~~~

The SFM data model includes two types of relationship between units: "Hierarchic", and "membership". 

In most cases, `Unit Relation: Related Unit Identifier`_ contains the unique identifying code for the immediate parent of the unit described in `Unit Relation: Unit Identifier`_, creating a "hierarchic" relationship. "Hierarchic" relationships are time-bound parent-child relationships between two units that are part of the same branch of a security force. When the relationship is defined in this way, the unit linked to using `Unit Relation: Related Unit Identifier`_ is synonynmous with  "parent unit" in that it describes a unit that is “above” and distinct and separate from the present unit in some way. It also exercises authority over its "child" unit(s). The aggregated upwards relationships  between units form organizational structured and command chains. 

Over time, a unit may have different parents. 

    Example: In Nigeria the ``112 Task Force Battalion`` had the parent of ``7 Division Garrison`` between 12 November 2015 and 24 March 2016. The ``112 Task Force Battalion`` was then under the ``22 Task Force Brigade`` from 14 March 2017 to 26 October 2017.

Units can also have multiple parent relationships at the same time. For example, sources could indicate a unit has a formal legal parent unit while at the same time a new security body established by decree can also directly order the unit to carry out operations, establishing a second parent relationship.

"Membership" relationships indicate that a unit is member of or attached to internal/national joint operations, international peacekeeping operations, or other multi-unit efforts. Often when there is an "operation" or "joint task force", it may not have have personnel of its own. Rather, personnel from a range of different units are assigned to it. Generally, these types of arrangements don’t put the operation “above” the unit in the organizational chart. There are two circumstances in which it is appropriate to define a relationship as a "Membership". First, where multiple units operate as part of an “operation” focused on a specific mission. Second, where multiple units “lend” or otherwise deploy personnel who operate under the command of a force composition like a "Joint Task Force" or "Operation", which usually has a commander of its own.

    Example: soldiers from ``1 Division`` are deployed to the northeast of Nigeria to operate under ``Operation BOYANA``. ``1 Division`` has a commander, but the soldiers as part of ``Operation BOYANA`` likely report to and take orders from the commander of ``Operation BOYANA``. When the soldiers are done with their rotation, after several months, they return to their “home unit” ``1 Division``. So while ``Operation BOYANA`` commands some soldiers who are part of ``1 Division`` it doesn’t technically command all of the soldiers of ``1 Division`` (otherwise it would be the parent unit).

The type of relationship between units is determined by setting the value in `Unit Relation: Type of Relation``, which offers two options:

 - ``child`` to define a hierarchic relationship. The unit specified in `Unit Relation: Related Unit Identifier`_ is the parent of the unit in `Unit Relation: Unit Identifier`_.
 - ``member`` to define a membership relationship. The unit specified in `Unit Relation: Unit Identifier`_ is a member of the unit noted in `Unit Relation: Related Unit Identifier`_.


Unit Relation: Type of Relation
===============================

Attribute name
~~~~~~~~~~~~~~

``::relation:type``

Description
~~~~~~~~~~~

The type of relationship that exists between two units.

Attribute type
~~~~~~~~~~~~~~

String from controlled list

Status
~~~~~~

This attribute is optional

Example of use
~~~~~~~~~~~~~~

``child``, ``member``

Guidance on use
~~~~~~~~~~~~~~~

We use this field to define the nature of the relationship between the unit that is the subject of the claim (as described in `Unit Relation: Unit Identifier`_) and the other unit described in `Unit Relation: Related Unit Identifier`_. There are only two values that can be used by the researcher in this attribute:


 - ``child`` to define a hierarchic relationship. The unit specified in `Unit Relation: Related Unit Identifier`_ is the parent of the unit in `Unit Relation: Unit Identifier`_.
 - ``member`` to define a membership relationship. The unit specified in `Unit Relation: Unit Identifier`_ is a member of the unit noted in `Unit Relation: Related Unit Identifier`_.

The values included in this field are used to build the organizational structure of a branch of the security forces. This is discussed in more detail in the documentation for the attribute `Unit Relation: Related Unit Identifier`_.

Unit Relation: Relation Classification
======================================

Attribute name
~~~~~~~~~~~~~~

``::relation:related_unit_class``

Description
~~~~~~~~~~~

Quality or nature of the relationshis that exists between two units.

Attribute type
~~~~~~~~~~~~~~

String, from controlled list

Status
~~~~~~

This attribute is optional

Example of use
~~~~~~~~~~~~~~

``Command``, ``Administrative``, ``Informal``

Guidance on use
~~~~~~~~~~~~~~~

Units have a ``Command`` relationship when the related parent unit can order the unit to perform some operational activity. These cover both *de jure* and *de facto* relationships between units.

``Informal`` relationships occur when there is a relationship outside of the legal or formal structure of security forces and where the exact nature of the relationship is unclear.

    Example: Lagos state in Nigeria has a security council which is a meeting of the governor, and the top commanders of police and military units in the state. The security council should be considered its own unit. By law a governor of a state is not in the chain of command for the military or police forces, but the security council membership establishes a relationship between the units and meetings often result in new approaches to security being taken, such as different deployments of police. In this case, we could make the determination that an informal relationship exists between the security council and the police and military units.

``Administrative`` relationships exist where a formal, non-command relationship exists between units, or where an administrative description is more accurate of the relationship between two units.

    Example: By law the Ministry of Defence in Nigeria provides administrative support to the Nigerian Army, establishing a relationship we could classify as ``Administrative``. The Standards Department of an Army Headquarters might be under the control of the Army Headquarters, meaning the Army Headquarters could order the Department to take some sort of action. This technically means the Department is under the “command” of the Headquarters, but the Monitor would describe this relationship as ``Administrative`` because the Department is not in the field conducting operations, it's an administrative organ of the Army Headquarters.


Unit Relation: Earliest Precise Date
====================================

.. note::
   To Do.

Unit Relation: Latest Precise Date
==================================

.. note::
   To Do.

Unit Relation: Earliest Imprecise Date
======================================

.. note::
   To Do.

Unit Relation: Latest Imprecise Date
====================================

.. note::
   To Do.

Unit Relation: Date Range is a Start Date
=========================================

.. note::
   To Do.

Unit Relation: Date Range is an End Date
=======================================

.. note::
   To Do.

Unit Relation: Research Comments
================================

Attribute name
~~~~~~~~~~~~~~

``::unit:claim:comment``

Description
~~~~~~~~~~~

Observations specific to the process of reviewing data in this claim, including fixes, refinements and other suggestions.

Atrribute type
~~~~~~~~~~~~~

String

Example of use
~~~~~~~~~~~~~~

``Parent unit missing``, ``Geography needs attention``, ``Possible duplicate - merge?``

Guidance on use
~~~~~~~~~~~~~~~

Staff Researchers use this attribute to exchange feedback about the data in the claim. This may included changes needed, references to sources that the owner of the claim might look at, and other observations that can improve the quality of the data. Data stored in this attribute are not intended for publication. The comments attribute is common to all claim types in the SFM data model.

Unit Relation: Research Owner
=============================

Attribute name
~~~~~~~~~~~~~~

``::unit:claim:researcher``

Description
~~~~~~~~~~~

Initials of Staff Reseacher who first created the unit.

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

Unit Relation: Research Status
==============================

Attribute name
~~~~~~~~~~~~~~

``::unit:claim:status``

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

- ``X``: Row should be deleted.
- ``0``: First commit. This row of data has just been added and needs review.
- ``1``: Fixes needed. A reviewer has made comments that need to be addressed, which will be recorded in the `Unit Relation: Research Comments`_ attribute.
- ``2``: Fixes made. The owner of this data has addressed the reviewer's comments.
- ``3``: Clean. A final check has been made by a reviewer, and this claim can be used in analysis and published.

This type of attribute is common to all claims in the SFM data model.
