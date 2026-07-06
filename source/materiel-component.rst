Component
#########

.. warning::

   This is a draft claim field set currently in development. We are in the process of integrating this dataset into our primary research. The format described in this documentation is a transition format. 

The :ref:`component` claim type captures how :ref:`materiel` may include other :ref:`materiel`, for example the targeting system in a particular type of aircraft.


Component: Summary of claim attributes 
***********************************

The table below summarizes the following dimensions of :ref:`component` claims:

 - Attribute label: a human readable label for the attribute
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the attribute
 - Key name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-component-fields.csv
   :header-rows: 1


Component: Details of claim attributes
***********************************

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

Entering ``component`` defines the claim and defines the relevant fields to be used in further data entry about a :ref:`component`. For quality assurance purposes, entering ``component`` should create an error if there is any entry for fields tied to other claim types, such as :ref:`materiel` or :ref:`equipment`.


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

Claims are marked ``accepted`` when all of the data can be entered in accordance with the guidance of this handbook. The ``conflict`` flag is used whenever a claim conflicts with another claim (or claims) and a review of citations show it to be the incorrect or false claim. A :ref:`public_notes:meta <component-public-notes>` should always accompany any ``conflict`` claim.

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

Researchers may use this field to make temporary notes or leave temporary comments intended for others in the research team about a claim. These should eventually be addressed and the field cleared by the researcher or research team. If the claim needs an explanatory note or comment to be better understood, then that should be entered in the :ref:`public_notes:meta <component-public-notes>` field.


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

Every claim must have at least one citation to evidence the data in the claim. When two or more citations are needed to evidence a claim then a corresponding explanatory note should be entered in the :ref:`public_notes:meta <component-public-notes>` field. This field is for the Universally Unique Identifier (UUID) for each citation, found in the :ref:`source:access_point_id:admin` field in the Sources sheet. When multiple citations are needed every UUID should be semi-colon separated.

.. _component-about-entity:

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

Every entity has a Universally Unique Identifier (UUID) to distinguish it from any other entity. For a :ref:`component` this UUID distinguishes them from any other :ref:`component` in the dataset.


about_entity:name:qa
====================

Description
~~~~~~~~~~~

Field that provides human readable name for claim.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

n/a

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the :ref:`about_entity:ref:claim <component-about-entity>` which combines the various elements of the claim into a single text field. This field can be manually added by a researcher or automatically populated by the system after import.


component:materiel:refs:assertion
=================================

Description
~~~~~~~~~~~

The unique 32 character code of the materiel which is a component of other materiel.

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

``b00ff36f-f367-4a48-9497-897d77decb8ad``

Guidance on use
~~~~~~~~~~~~~~~

The UUID used in :ref:`component:materiel:refs:assertion` must be for :ref:`materiel` that already exists in the dataset.


component:materiel:names:qa
===========================

Description
~~~~~~~~~~~

The human readable name of the materiel which is a component of other materiel.

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

``GBU-12``

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the :ref:`component:materiel:refs:assertion` field. This field can be manually added by a researcher or automatically populated by the system after import. Best practice for this field is to use the :ref:`name:annotation <materiel-name-annotation>` of the :ref:`materiel` in the :ref:`component:materiel:refs:assertion` field.


component:types:assertion
=========================

Description
~~~~~~~~~~~

The type of relationship that exists between the materiel.

Attribute type
~~~~~~~~~~~~~~

String from controlled list.

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``component-of``

Guidance on use
~~~~~~~~~~~~~~~

We use this field to define the nature of the relationship between the :ref:`materiel` that is the subject of the claim (as described in :ref:`component:materiel:refs:assertion`) and the other :ref:`materiel` described in :ref:`component:aggregate_materiel:refs:assertion`. The only value that can be used by the researcher in this attribute is ``component-of``. As this is a draft field the number of possible entries in this field may increase. The field may also prove redundant and be removed in future updates.


component:aggregate_materiel:refs:assertion
===========================================

Description
~~~~~~~~~~~

The unique 32 character code of the materiel which is made up of the component.

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

The UUID used in :ref:`component:aggregate_materiel:refs:assertion` must be for :ref:`materiel` which already exists in the dataset.


component:aggregate_materiel:names:qa
=====================================

Description
~~~~~~~~~~~

The human readable name of the materiel which is made up of the component materiel.

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

``MiG-21UM``

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the :ref:`component:aggregate_materiel:refs:assertion` field. This field can be manually added by a researcher or automatically populated by the system after import. Best practice for this field is to use the :ref:`name:annotation <materiel-name-annotation>` of the :ref:`materiel` in the :ref:`component:aggregate_materiel:refs:assertio` field.


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


.. _component-public-notes:

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

For a :ref:`component` the only allowed entry for this field is ``claim``.
