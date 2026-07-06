Equipment
#########

.. warning::

   This is a draft claim field set currently in development. We are in the process of integrating this dataset into our primary research. The format described in this documentation is a transition format.

The :ref:`equipment` claim type describes links a :ref:`unit` to the :ref:`materiel` it uses.


Equipment: Summary of claim attributes 
**************************************

The table below summarizes the following dimensions of :ref:`equipment` claims:

 - Attribute label: a human readable label for the attribute
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the attribute
 - Key name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-equipment-fields.csv
   :header-rows: 1


Equipment: Details of claim attributes
**************************************

This section contains further information about each attribute, including descriptions, examples of use, and Guidance on use.


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

``materiel``, ``equipment``, ``component``

Guidance on use
~~~~~~~~~~~~~~~

Entering ``equipment`` defines the claim and defines the relevant fields to be used in further data entry about a :ref:`equipment`. For quality assurance purposes, entering ``equipment`` should create an error if there is any entry for fields tied to other claim types, such as :ref:`materiel` or :ref:`component`.


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

Claims are marked ``accepted`` when all of the data can be entered in accordance with the guidance of this handbook. The ``conflict`` flag is used whenever a claim conflicts with another claim (or claims) and a review of citations show it to be the incorrect or false claim. A :ref:`public_notes:meta <equipment-public-notes>` should always accompany any ``conflict`` claim.

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

Researchers may use this field to make temporary notes or leave temporary comments intended for others in the research team about a claim. These should eventually be addressed and the field cleared by the researcher or research team. If the claim needs an explanatory note or comment to be better understood, then that should be entered in the :ref:`public_notes:meta <equipment-public-notes>` field.


citation:refs:claim
===================

Description
~~~~~~~~~~~

Field unique 32 character code assigned to citation(s) evidencing the claim.

Attribute type
~~~~~~~~~~~~~~

String in UUID format

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

Every claim must have at least one citation to evidence the data in the claim. When two or more citations are needed to evidence a claim then a corresponding explanatory note should be entered in the :ref:`public_notes:meta <equipment-public-notes>` field. This field is for the Universally Unique Identifier (UUID) for each citation, found in the :ref:`source:access_point_id:admin` field in the Sources sheet. When multiple citations are needed every UUID should be semi-colon separated.

.. _equipment-about-entity:

about_entity:ref:claim
======================

Description
~~~~~~~~~~~

A unique 32 character code assigned to each entity in the dataset.

Attribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:claim/about-entity:ref``

Example of use
~~~~~~~~~~~~~~

``521ebf18-f161-4ac9-8c72-5a246efa0458``

Guidance on use
~~~~~~~~~~~~~~~

Every entity has a Universally Unique Identifier (UUID) to distinguish it from any other entity. For :ref:`equipment` this UUID distinguishes them from any other :ref:`equipment` in the dataset.


about_entity:name:qa
====================

Description
~~~~~~~~~~~

Field that provides human readable name for entity.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``n/a``

Example of use
~~~~~~~~~~~~~~

``n/a``

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the :ref:`about_entity:ref:claim <equipment-about-entity>` which combines the various elements of the claim into a single text field. This field can be manually added by a researcher or automatically populated by the system after import.


equipment:materiel:refs:assertion
=================================

Description
~~~~~~~~~~~

The unique 32 character code assigned to the materiel with the :ref:`equipment` which is the focus of the claim.

Attribute type
~~~~~~~~~~~~~~

String in UUID format.

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``ca19cc03-1180-469d-b87a-94fb54d657fb``

Guidance on use
~~~~~~~~~~~~~~~

The UUID used in :ref:`equipment:materiel:refs:assertion` must be for :ref:`materiel` which already exists in the dataset.


equipment:materiel:names:qa
===========================

Description
~~~~~~~~~~~

The human readable name of the materiel that is used by the unit.

Attribute type
~~~~~~~~~~~~~~

Text string.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``AAQ-14 Sharpshooter``

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the :ref:`equipment:materiel:refs:assertion`. This field can be manually added by a researcher or automatically populated by the system after import. Best practice for this field is to use the :ref:`name:annotation <unit-name-annotation>` of the :ref:`materiel`.


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


equipment:id:assertion
=====================

Description
~~~~~~~~~~~

An identifier for the materiel as specified in the citation from which it is taken.

Attribute type
~~~~~~~~~~~~~~

Text string.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``3018``, ``101``

Guidance on use
~~~~~~~~~~~~~~~

This attribute is used to capture any seriel number, tail number, or other idenitifer for a specific piece of materiel.


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


.. _equipment-public-notes:

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

For a :ref:`equipment` the only allowed entry for this field is ``claim``.
