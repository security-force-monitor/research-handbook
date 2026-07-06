Materiel
########

.. warning::

   This is a draft claim field set currently in development. We are in the process of integrating this dataset into our primary research. The format described in this documentation is a transition format. 

The :ref:`materiel` claim type describes basic identifying information about :ref:`materiel`: name, aliases, classifications, ids, and associated time ranges with them. Claims of this type are grouped together with :ref:`equipment` which links a :ref:`unit` to the :ref:`materiel` it uses. :ref:`component` captures how :ref:`materiel` may include other :ref:`materiel`, for example the targeting system in a particular type of aircraft.


Materiel: Summary of claim attributes 
***********************************

The table below summarizes the following dimensions of :ref:`materiel` claims:

 - Attribute label: a human readable label for the attribute
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the attribute
 - Key name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-materiel-fields.csv
   :header-rows: 1


Materiel: Details of claim attributes
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

Entering ``materiel`` defines the claim and defines the relevant fields to be used in further data entry about a :ref:`materiel`. For quality assurance purposes, entering ``materiel`` should create an error if there is any entry for fields tied to other claim types, such as :ref:`equipment` or :ref:`component`.


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

Claims are marked ``accepted`` when all of the data can be entered in accordance with the guidance of this handbook. The ``conflict`` flag is used whenever a claim conflicts with another claim (or claims) and a review of citations show it to be the incorrect or false claim. A :ref:`public_notes:meta <materiel-public-notes>` should always accompany any ``conflict`` claim.

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

Researchers may use this field to make temporary notes or leave temporary comments intended for others in the research team about a claim. These should eventually be addressed and the field cleared by the researcher or research team. If the claim needs an explanatory note or comment to be better understood, then that should be entered in the :ref:`public_notes:meta <materiel-public-notes>` field.


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

Every claim must have at least one citation to evidence the data in the claim. When two or more citations are needed to evidence a claim then a corresponding explanatory note should be entered in the :ref:`public_notes:meta <materiel-public-notes>` field. This field is for the Universally Unique Identifier (UUID) for each citation, found in the :ref:`source:access_point_id:admin` field in the Sources sheet. When multiple citations are needed every UUID should be semi-colon separated.

.. _materiel-about-entity:

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

Every entity has a Universally Unique Identifier (UUID) to distinguish it from any other entity. For :ref:`materiel` this UUID distinguishes them from any other :ref:`materiel` in the dataset. This UUID is used in other fields to tie :ref:`materiel` as :ref:`equipment` of a specific :ref:`unit` or as a :ref:`componant` (or part) of other :ref:`materiel`.


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

``MiG-21UM``

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the :ref:`about_entity:ref:claim <materiel-about-entity>` which combines the various elements of the claim into a single text field. This field can be manually added by a researcher or automatically populated by the system after import. For :ref:`materiel` best practice is to use the :ref:`name:annotation <materiel-name-annotation>` in this field.


.. _materiel-name-annotation:

name:annotation
===============

Description
~~~~~~~~~~~

Fullest name of the materiel as evidenced by citations.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:annotation/name``

Example of use
~~~~~~~~~~~~~~

``MiG-21UM``, ``Universal Water Activated Release System``

Guidance on use
~~~~~~~~~~~~~~~

As with all annotation fields, this field is the singular display name for the entity. For :ref:`materiel` this field is only used if the citation evidences the fullest name of the :ref:`materiel` which is defined as the name with the highest number of characters.


materiel:names:assertion
========================

Description
~~~~~~~~~~~

Any name given for the materiel from citation.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``MiG``, ``UWARS``

Guidance on use
~~~~~~~~~~~~~~~

Any name for :ref:`materiel` used in the citation should be entered in this field. While the :ref:`name:annotation <materiel-name-annotation>` field is only used for a single, most complex value, this field is used for any name a citation uses for :ref:`materiel`. Thus, this field serves to capture "aliases" of the :ref:`materiel`, which also includes any typos or misspellings that may exist in the citation.


materiel:classifications:assertion
==================================

Description
~~~~~~~~~~~

A general descriptor for the materiel.

Attribute type
~~~~~~~~~~~~~~

Text, controlled vocabulary.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``aircraft``, ``radar``

Guidance on use
~~~~~~~~~~~~~~~

We use classifications to describe the basic nature of specific materiel to assist investigations of potential linkages between reports of human rights abuses and the Security Force Monitor’s dataset. 


materiel:classifications:assertion
==================================

Description
~~~~~~~~~~~

Short textual description of material found in a media resource that provides information about how the materiel looks or sounds.

Attribute type
~~~~~~~~~~~~~~

Text, controlled vocabulary.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``side of aircraft``

Guidance on use
~~~~~~~~~~~~~~~

This attribute is used to store a brief description of the content of external media. The description should be sufficient for the analyst to quickly appraise what they can expect to find in the media about what the person looks or sounds like. A new row is created for each distinct media item about the materiel.


materiel:id:assertion
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


materiel:roles:assertion
========================

Description
~~~~~~~~~~~

An attribute for how the materiel is used.

Attribute type
~~~~~~~~~~~~~~

Text, controlled vocabulary.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

``close air support``, ``transport``

Guidance on use
~~~~~~~~~~~~~~~

This field is used to capture a descriptor for how the materiel is used.


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


.. _materiel-public-notes:

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

For a :ref:`materiel` the only allowed entry for this field is ``claim``.
