Relation
########

The ``relation`` claim type describes how a ``unit`` relates to another ``unit``. This can be used to model a hierarchical "tree" where one ``unit`` is subordinate to another, or it can also be used to model joint-task force or other multi-unit grouping where the grouping is comprised of members from multiple different units.

Unit Relation: Summary of claim attributes
******************************************

The table below summarises the following dimensions of Unit Relation claims:

 - Attribute label: a human readable label for the attribute
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the attribute
 - Key name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-relation-fields.csv
   :header-rows: 1


Unit Relation: Details of claim attributes
******************************************

This section contains further information about each attribute, including descriptions, examples of use, and guidance on use.


type:claim
==================================

Description
~~~~~~~~~~~

A field that defines what type of claim is being made.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``relation``

Guidance on use
~~~~~~~~~~~~~~~

Entering ``relation`` defines the claim and establishes the fields to be used in further data entry about a relation.


status:meta
==================================

Description
~~~~~~~~~~~

A field that classifies the data in the claim.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``accepted``, ``conflict``, ``work_needed``

Guidance on use
~~~~~~~~~~~~~~~

Claims are marked ``accepted`` when all of the data can be entered in accordance with the guidance of this handbook. The ``conflict`` flag is used whenever a claim conflicts with another claim (or claims) and a review of citations show it to be the incorrect or false claim. For example, XYZ. Finally, if the data cannot be correctly entered or no citations can establish whether a claim should be flagged as ``accepted`` or ``conflict`` then the flag ``work_needed`` should be used. This allows the researcher to either fix the issue or conduct additional research.


researcher:meta
==================================

Description
~~~~~~~~~~~

Field for initials or other identifer of researcher who last entered data for the claim.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``TW``

Guidance on use
~~~~~~~~~~~~~~~

Every researcher should use this field to mark the claims that they have entered. Anytime a researcher modifies any data for an existing claim they should update this field so that any questions can be directed to the right person and the flow of work can be better tracked. 


internal_comments:meta
==================================

Description
~~~~~~~~~~~

A field for temporary comments or notes for the researcher or research team working on the claim.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``Come back to this to determine date for claim``

Guidance on use
~~~~~~~~~~~~~~~

Researchers may use this field to make temporary notes or leave temporary comments intended for others in the research team about a claim. These should eventually be addressed and the field cleared by the researcher or research team. If the claim needs an explanatory note or comment to be better understood then that should be entered in the ``public_notes:meta`` field.


citation:refs:claim
==================================

Description
~~~~~~~~~~~

Field unique 32 character code assigned to citation(s) evidencing the claim.

Attribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``69dba35b-2b70-47cf-bfda-f80225f652c6``, ``4e99308c-f9c0-49e8-b97b-14c1e7bcb99d;bedf57b2-c20b-41e3-9dcf-b7b065eaa3b7``

Guidance on use
~~~~~~~~~~~~~~~

Every claim must have at least one citation to evidence the data in the claim. When two or more citations are needed to evidence a claim then a corresponding explanatory note should be entered in the ``public_notes:meta`` field. This field is for the Universally Unique Indentifier (UUID) for each citation, found in the ``ref:source:access_point_id:admin`` field in the Sources sheet. When multiple citations are needed every UUID should be semi-colon seperated.


about_entity:ref:claim
==================================

Description
~~~~~~~~~~~

A unique 32 character code assigned to each entity in the dataset.

Attribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``521ebf18-f161-4ac9-8c72-5a246efa0458``

Guidance on use
~~~~~~~~~~~~~~~

Every claim has an Universally Unique Indentifier (UUID) to distinguish it from any other claim. For a ``relation`` this UUID distinguishes them from any other ``relation`` in the dataset.

Every ``relation`` between the same two ``units`` is always treated as a contingious, meaning it has the same UUID, unless citations establish it should be treated as non-contigious.

.. admonition:: Example

    EXAMPLE

Two or more ``relation`` claims should always be treated as contigious if there is an overlap in the time range of the two claims, or if the time-ranges of the claims fall within 1 day of each other.

.. admonition:: Example

    The ``33 Light Infantry Division`` has multiple citations establishing that it is a mobile unit which can change ``relation`` to whatever regional command controls the area where it is operating. One claim puts in an area under ``Northeastern Regional Military Command`` from at least ``2016-03-10`` to at least ``2016-03-11``, and another citation pleaces in an area under ``Northeastern Regional Military Command`` on ``2016-03-12``. These two claims are coded as the same ``relation`` given that they fall within 1 day of each other.

about_entity:name:qa
==================================

Description
~~~~~~~~~~~

Field that provides human readible name for entity.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``21 Military Operations Command  Northern Regional Military Command``, ``Unknown Tactical Operations Command (77 Light Infantry Division)  77 Light Infantry Division``

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the ``about_entity:ref:claim`` which combines the various elements of the claim into a single text field. This field can be manually added by a researcher or automatically populated by the system after import.


relation:unit:refs:assertion
============================

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

The ``about_entity:ref:claim`` UUID must be for a ``unit`` which already exists in the dataset. This attribute denotes one side of a relationship between units; the other is denoted in the attribute `Unit Relation: Related Unit Identifier`_. The nature of the relationship is clarified further using the `Unit Relation: Type of Relation`_ and `Unit Relation: Relation Classification`_ attributes.


relation:unit:names:qa
============================

Description
~~~~~~~~~~~

The unique 32 character code assigned to the unit about which a relationship is described in the claim.

Atrribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``Groupement de Forces pour la Sécurisation du Nord``, ``Moriones Tondo Police Station 2``

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the ``relation:unit:refs:assertion``. This field can be manually added by a researcher or automatically populated by the system after import. Best practice for this field is to use the ``name:annotation`` of the ``unit``.


relation:types:assertion
===============================

Description
~~~~~~~~~~~

The type of relationship that exists between two units.

Attribute type
~~~~~~~~~~~~~~

String from controlled list

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``child-of``, ``member-of``

Guidance on use
~~~~~~~~~~~~~~~

We use this field to define the nature of the relationship between the unit that is the subject of the claim (as described in `Unit Relation: Unit Identifier`_) and the other unit described in `Unit Relation: Related Unit Identifier`_. There are only two values that can be used by the researcher in this attribute:

 - ``child`` to define a hierarchic relationship. The unit specified in `Unit Relation: Related Unit Identifier`_ is the parent of the unit in `Unit Relation: Unit Identifier`_.
 - ``member`` to define a membership relationship. The unit specified in `Unit Relation: Unit Identifier`_ is a member of the unit noted in `Unit Relation: Related Unit Identifier`_.

The values included in this field are used to build the organizational structure of a branch of the security forces. This is discussed in more detail in the documentation for the attribute `Unit Relation: Related Unit Identifier`_.


relation:related_unit:refs:assertion
======================================

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

In some cases, we are aware that a unit exist because of what sources tell us about the general organizational structure. However, in some cases sources do not provide us with sufficient information to give these units a name, or to be precise about the nature of relationships between units. To resolve issues of this nature we use the concepts of "Unnamed" and "Unknown" units. We have written more about this in the Handbook page :ref:`Unknown and unnamed units`.


relation:related_unit:names:qa
==============================

Description
~~~~~~~~~~~

The unique 32 character code assigned to the unit about which a relationship is described in the claim.

Atrribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``Opération Tourbillon Vert 2``, ``99 Light Infantry Division``

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the ``relation:related_unit:refs:assertion`` field. This field can be manually added by a researcher or automatically populated by the system after import. Best practice for this field is to use the ``name:annotation`` of the ``unit``.


relation:related_unit_classes:assertion
======================================

Description
~~~~~~~~~~~

Quality or nature of the relationshis that exists between two units.

Attribute type
~~~~~~~~~~~~~~

String, from controlled list.

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``command``, ``administrative``, ``class``

Guidance on use
~~~~~~~~~~~~~~~

Units have a ``Command`` relationship when the related parent unit can order the unit to perform some operational activity. These cover both *de jure* and *de facto* relationships between units.

``Informal`` relationships occur when there is a relationship outside of the legal or formal structure of security forces and where the exact nature of the relationship is unclear.

    Example: Lagos state in Nigeria has a security council which is a meeting of the governor, and the top commanders of police and military units in the state. The security council should be considered its own unit. By law a governor of a state is not in the chain of command for the military or police forces, but the security council membership establishes a relationship between the units and meetings often result in new approaches to security being taken, such as different deployments of police. In this case, we could make the determination that an informal relationship exists between the security council and the police and military units.

``Administrative`` relationships exist where a formal, non-command relationship exists between units, or where an administrative description is more accurate of the relationship between two units.

    Example: By law the Ministry of Defence in Nigeria provides administrative support to the Nigerian Army, establishing a relationship we could classify as ``Administrative``. The Standards Department of an Army Headquarters might be under the control of the Army Headquarters, meaning the Army Headquarters could order the Department to take some sort of action. This technically means the Department is under the “command” of the Headquarters, but the Monitor would describe this relationship as ``Administrative`` because the Department is not in the field conducting operations, it's an administrative organ of the Army Headquarters.


first_precise:range
===================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


last_precise:range
==================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


first_imprecise:range
=====================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


last_imprecise:range
====================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


starting:range
==============

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


ending:range
============

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


starting_context:range
======================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


ending_context:range
====================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


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

This field should be used whenever any claim requires additional explanation because for a general reader the claim is not clearly and directly stated in the citation. For the example of use above a citation published on 15 July 2019 refers to something happening "last week" and as a result a researcher has determined the previous Sunday 7 July 2019 through Saturday 13 July 2019 should be entered into the appropriate fields of ``first_imprecise:range`` and ``last_imprecise:range``. That range would not be immediately clear to a public audience since neither date is directly referenced in the text of the citation. As a result the researcher should explain how that date range was evidenced by the citation.


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

For a ``relation`` the only allowed entry for this field is ``claim``.
