Relation
########

The :ref:`relation` claim type describes how a :ref:`unit` relates to another :ref:`unit`. This can be used to model a hierarchical "tree" where one :ref:`unit` is subordinate to another, or it can also be used to model joint-task force or other multi-unit grouping where the grouping is comprised of members from multiple different units.

Relation: Summary of claim attributes
*************************************

The table below summarizes the following dimensions of :ref:`relation` claims:

 - Attribute label: a human readable label for the attribute
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the attribute
 - Key name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-relation-fields.csv
   :header-rows: 1


Relation: Details of claim attributes
*************************************

This section contains further information about each attribute, including descriptions, examples of use, and guidance on use.


type:claim
==========

Description
~~~~~~~~~~~

A field that defines what type of claim is being made.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:claim/type``

Example of use
~~~~~~~~~~~~~~

``unit``, ``positioning``, ``relation``, ``person``, ``posting``, ``incident``

Guidance on use
~~~~~~~~~~~~~~~

Entering ``relation`` defines the claim and defines the relevant fields to be used in further data entry about a :ref:relation. For quality assurance purposes, entering ``relation`` should create an error if there is any entry for fields tied to other claim types, such as :ref:`unit` or :ref:`positioning`.


status:meta
===========

Description
~~~~~~~~~~~

A field that classifies the data in the claim.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:claim/statuses``

Example of use
~~~~~~~~~~~~~~

``accepted``, ``conflict``, ``work_needed``, ``issue``

Guidance on use
~~~~~~~~~~~~~~~

Claims are marked ``accepted`` when all of the data can be entered in accordance with the guidance of this handbook. The ``conflict`` flag is used whenever a claim conflicts with another claim (or claims) and a review of citations show it to be the incorrect or false claim. A :ref:`public_notes:meta <relation-public-notes>` should always accompany any ``conflict`` claim.

.. admonition:: Example

    Citations reference a unit 757 Light Infantry Battalion in 2008 and again in 2019 as part of the Myanmar Army. This conflicts with other citations before and after these dates which list all light infantry battalions of the army and do not include this unit. Further citations establish a general numbering practices of the army which provides further evidence that no such battalion exists. The ``unit`` and other claims related to the 757 Light Infantry Battalion should still be entered into the dataset, flagged with ``status:meta`` of the ``conflict``, and have the status fully explained in a ``public_notes:meta``.

If the data itself cannot be brought into the SFM standard the flag ``issue`` should be used. Finally, if the current citations cannot establish whether a claim should be flagged as ``accepted`` or ``conflict`` then the flag ``work_needed`` should be used as additional research is needed.


researcher:meta
===============

Description
~~~~~~~~~~~

Field for initials or other identifier of researcher who last entered data for the claim.

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

Researchers may use this field to make temporary notes or leave temporary comments intended for others in the research team about a claim. These should eventually be addressed and the field cleared by the researcher or research team. If the claim needs an explanatory note or comment to be better understood, then that should be entered in the :ref:`public_notes:meta <relation-public-notes>` field.

.. _relation-citation:

citation:refs:claim
===================

Description
~~~~~~~~~~~

Field unique 32 character code assigned to citation(s) evidencing the claim.

Attribute type
~~~~~~~~~~~~~~

String in UUID format.

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:claim/citation:refs``

Example of use
~~~~~~~~~~~~~~

``69dba35b-2b70-47cf-bfda-f80225f652c6``, ``4e99308c-f9c0-49e8-b97b-14c1e7bcb99d;bedf57b2-c20b-41e3-9dcf-b7b065eaa3b7``

Guidance on use
~~~~~~~~~~~~~~~

Every claim must have at least one citation to evidence the data in the claim. When two or more citations are needed to evidence a claim then a corresponding explanatory note should be entered in the :ref:`public_notes:meta <relation-public-notes>` field. This field is for the Universally Unique Identifier (UUID) for each citation, found in the :ref:`source:access_point_id:admin` field in the Sources sheet. When multiple citations are needed every UUID should be semi-colon separated.

.. _unit-about-entity:

about_entity:ref:claim
======================

Description
~~~~~~~~~~~

A unique 32 character code assigned to each entity in the dataset.

Attribute type
~~~~~~~~~~~~~~

String in UUID format.

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:claim/about-entity:ref``

Example of use
~~~~~~~~~~~~~~

``0ab0e3c3-4bd6-4607-8cc5-1cfce9502c57``

Guidance on use
~~~~~~~~~~~~~~~

Every claim has a Universally Unique Identifier (UUID) to distinguish it from any other claim. For a :ref:`relation` this UUID distinguishes them from any other :ref:`relation` in the dataset.

Every :ref:`relation` between the same two units is always treated as a contiguous, meaning it has the same UUID, unless citations establish it should be treated as non-contiguous.

.. admonition:: Example

    The ``33 Light Infantry Division`` has multiple citations establishing that it is a mobile unit which can change :ref:`relation` to whatever regional military command controls the area where it is operating. One citation puts the division in an area under ``Northeastern Regional Military Command`` as of ``2016-11-13`` which establishes a :ref:`relation` between the division and the regional command for the same time-range. Another citation places the division in an area under ``Northeastern Regional Military Command`` on ``2016-12-05``. Even though the related units are the same, because citations establish the division is a mobile unit that can change :ref:`relation`` these two claims are coded as separate, non-contiguous relations.

Two or more :ref:`relation` claims should always be treated as contiguous if there is an overlap in the time range of the two claims, or if the time-ranges of the claims fall within 1 day of each other.

.. admonition:: Example

    The ``33 Light Infantry Division`` has multiple citations establishing that it is a mobile unit which can change :ref:`relation` to whatever regional military command controls the area where it is operating. One citation puts the division in an area under ``Northeastern Regional Military Command`` from at least ``2016-03-10`` to at least ``2016-03-11``, which establishes a :ref:`relation` between the division and the regional command for the same time-range. Another citation places the division in an area under ``Northeastern Regional Military Command`` on ``2016-03-12``, which again establishes a :ref:`relation` between the division and the regional command for the same time-range. These two claims are coded as the same :ref:`relation` given that they fall within 1 day of each other.

A :ref:`unit` may have multiple, overlapping relations.

.. admonition:: Example

    Citations establish that regional military commands in the Myanmar Army control units that operate in their area of operations. Citations establish through time that the ``290 Infantry Battalion`` is under command of the ``Northeastern Regional Military Command`` and also based in areas under ``Northeastern Regional Military Command`` through time. Combined these citations evidence a contiguous :ref:`relation` between the battalion and ultimately the ``Northeastern Regional Military Command``. Other citations, however, evidence the battalion also operated in areas controlled by different regional military commands. These establish additional relations for the battalion during the time ranges it was operating in areas under the ``Eastern Central Regional Military Command``, ``Northern Regional Military Command``, ``Southeastern Regional Military Command`` or ``Triangle Regional Military Command``.


about_entity:name:qa
====================

Description
~~~~~~~~~~~

Field that provides human readable name for entity.

Attribute type
~~~~~~~~~~~~~~

Text string.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:claim/about-entity:ref``

Example of use
~~~~~~~~~~~~~~

``21 Military Operations Command  Northern Regional Military Command``, ``Unknown Tactical Operations Command (77 Light Infantry Division)  77 Light Infantry Division``

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the :ref:`about_entity:ref:claim <unit-about-entity>` which combines the various elements of the claim into a single text field. This field can be manually added by a researcher or automatically populated by the system after import.


relation:unit:refs:assertion
============================

Description
~~~~~~~~~~~

The unique 32 character code assigned to the unit with the :ref:`relation` which is the focus of the claim.

Attribute type
~~~~~~~~~~~~~~

String in UUID format.

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:assertion/relation:unit:refs``

Example of use
~~~~~~~~~~~~~~

``a407be6a-28e6-4237-b4e9-307f27b1202e``

Guidance on use
~~~~~~~~~~~~~~~

The UUID used in ``relation:unit:refs:assertion`` must be for a :ref:`unit` which already exists in the dataset. The nature of the relationship is clarified further using the :ref:`relation:types:assertion` and :ref:`relation:related_unit_classes:assertion` fields.


relation:unit:names:qa
======================

Description
~~~~~~~~~~~

The human readable name of the unit that is a child or member of another unit.

Attribute type
~~~~~~~~~~~~~~

Text string.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:assertion/relation:unit:refs``

Example of use
~~~~~~~~~~~~~~

``Groupement de Forces pour la Sécurisation du Nord``, ``Moriones Tondo Police Station 2``

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the :ref:`relation:unit:refs:assertion`. This field can be manually added by a researcher or automatically populated by the system after import. Best practice for this field is to use the :ref:`name:annotation <unit-name-annotation>` of the :ref:`unit`.


relation:types:assertion
========================

Description
~~~~~~~~~~~

The type of relationship that exists between two units.

Attribute type
~~~~~~~~~~~~~~

String from controlled list.

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:assertion/relation:types``

Example of use
~~~~~~~~~~~~~~

``child-of``, ``member-of``

Guidance on use
~~~~~~~~~~~~~~~

We use this field to define the nature of the relationship between the :ref:`unit` that is the subject of the claim (as described in :ref:`relation:unit:refs:assertion`) and the other :ref:`unit` described in :ref:`relation:related_unit:refs:assertion`. There are only two values that can be used by the researcher in this attribute:

 - ``child-of`` to define a hierarchic relationship. The unit specified in :ref:`relation:unit:refs:assertion` is the parent of the unit in :ref:`relation:related_unit:refs:assertion`.
 - ``member-of`` to define a membership relationship. The unit specified in :ref:`relation:unit:refs:assertion` has some personnel who are members of the unit noted in :ref:`relation:related_unit:refs:assertion`.

A ``member-of`` :ref:`relation` is used to capture instances where personnel of one unit become personnel of another unit, such as a joint task force or peacekeeping mission, that has a distinct chain of command and geographic footprint. This is important to capture in the data model as the personnel in joint task force or peacekeeping mission are no longer under the command of their "home" unit or at the minimum have an altered :ref:`relation` with their "home" chain of command.

.. admonition:: Example

    Many units of the Mexican Army sent personnel to serve as part of ``Operación Conjunta Chihuahua``, a joint task force which conducted operations in and around Ciudad Juárez in northern Mexico. While these personnel were serving as part of the operation they were part of the chain of command for that operation, and not their "home" unit which may have been across the country. Similarly, personnel of the "home" unit were not in a hierarchical :ref:`relation`, or under the command of, ``Operación Conjunta Chihuahua``.


relation:related_unit:refs:assertion
====================================

Description
~~~~~~~~~~~

The unique 32 character code of the immediate superior or parent unit of the current unit, or the unit to which the current unit is a member.

Attribute type
~~~~~~~~~~~~~~

String in UUID format.

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:assertion/relation:related-unit:refs``

Example of use
~~~~~~~~~~~~~~

``67eff2ed-2321-464f-8f85-da04db2cd1ec``

Guidance on use
~~~~~~~~~~~~~~~

The UUID used in :ref:`relation:related_unit:refs:assertion` must be for a :ref:`unit` which already exists in the dataset. The nature of the relationship is clarified further using the :ref:`relation:types:assertion` and :ref:`relation:related_unit_classes:assertion` fields.


relation:related_unit:names:qa
==============================

Description
~~~~~~~~~~~

The human readable name of the unit that is the "parent" of another :ref:`unit` or which has personnel serving within it as members drawn from another :ref:`unit`.

Attribute type
~~~~~~~~~~~~~~

Text string.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:assertion/relation:related-unit:refs``

Example of use
~~~~~~~~~~~~~~

``Opération Tourbillon Vert 2``, ``99 Light Infantry Division``

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the :ref:`relation:related_unit:refs:assertion` field. This field can be manually added by a researcher or automatically populated by the system after import. Best practice for this field is to use the :ref:`name:annotation <unit-name-annotation>` of the :ref:`unit` in the :ref:`relation:related_unit:refs:assertion` field.


relation:related_unit_classes:assertion
=======================================

Description
~~~~~~~~~~~

Quality or nature of the relationship that exists between two units.

Attribute type
~~~~~~~~~~~~~~

String, from controlled list.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:assertion/relation:related-unit-classes``

Example of use
~~~~~~~~~~~~~~

``command``, ``administrative``, ``class``

Guidance on use
~~~~~~~~~~~~~~~

Units have a ``command`` relationship when the related parent unit can order the unit to perform some operational activity. These cover both *de jure* and *de facto* relationships between units.

The ``class`` entry in this field is exclusively used for modeling the different "classes" or "intakes" of security force training or academic insitutions.

.. admonition:: Example

    The ``Philippine Military Academy`` and ``Philippine National Police Academy`` enroll students every year into a formal academic program to train them as officers. These cohorts are organized into "classes" named after the year that they will graduate, such as "Class of 1998". To model this we create a :ref:`unit` ``Class of 1998 (Philippine National Police Academy)`` which has a :ref:`relation` with ``Philippine National Police Academy`` where :ref:`relation:related_unit_classes:assertion` is ``class``. The ``Defense Services Academy`` in Myanmar enroll students every year via cohorts organized into numbered "intakes", such as "Intake 30". Similar to the example above, we create ``Intake 30 (Defense Services Academy)`` which has a :ref:`relation` with ``Defense Services Academy`` where :ref:`relation:related_unit_classes:assertion` is ``class``.

``administrative`` relationships exist where a formal, non-command relationship exists between units, or where an administrative description is more accurate of the relationship between two units.

.. admonition:: Example

    By law the ``Ministry of Defence`` in Nigeria provides administrative support to the ``Nigerian Army``, establishing a relationship we could classify as ``administrative``. The ``Standards Department`` of an ``Army Headquarters`` might be under the control of the ``Army Headquarters``, meaning the ``Army Headquarters`` could order the Department to take some sort of action. This technically means the Department is under the “command” of the Headquarters, but the Monitor would describe this relationship as ``administrative`` because the Department is not in the field conducting operations, it's an administrative organ of the ``Army Headquarters``.


first_precise:range
===================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`How Dates Work`.


last_precise:range
==================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`How Dates Work`.


first_imprecise:range
=====================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`How Dates Work`.


last_imprecise:range
====================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`How Dates Work`.


starting:range
==============

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`How Dates Work`.


ending:range
============

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`How Dates Work`.


starting_context:range
======================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`How Dates Work`.


ending_context:range
====================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`How Dates Work`.

.. _relation-public-notes:

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

This field should be used whenever any claim requires additional explanation because for a general reader the claim is not clearly and directly stated in the citation. In the "Example of Use" above a citation published on 15 July 2019 refers to something happening "last week" and as a result a researcher has determined the previous Sunday 7 July 2019 through Saturday 13 July 2019 should be entered into the appropriate fields of ``first_imprecise:range`` and ``last_imprecise:range``. That range would not be immediately clear to a public audience since neither date is directly referenced in the text of the citation. As a result, the researcher should explain how that date range was evidenced by the citation.


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

For a :ref:`relation` the only entry allowed for this field is ``claim``.
