Person
######

"Person" is a claim type describing basic identifying information about a person: their name, aliases and associated time ranges with them. Claims of this type are grouped together with :ref:`Person Posting` (describing postings to different units) which tracks the person's career. There are also several fields in development to capture other aspects about persons.

Person: Summary of claim attributes 
*****************************************

The table below summarises the following dimensions of Person claims:

 - Attribute label: a unique machine-readable name for the attribute, used during data capture
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the field
 - Conformed name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-person-fields.csv
   :header-rows: 1
   :delim: tab


Person: Details of claim attributes
********************************************

This section contains further information about each attribute, including descriptions, examples of use, and Guidance on use.


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

``person``

Guidance on use
~~~~~~~~~~~~~~~

Entering ``person`` defines the claim and establishes the fields to be used in further data entry about a person.


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

Every entity has an Universally Unique Indentifier (UUID) to distinguish it from any other entity. For a ``person`` this UUID distinguishes them from any other ``person`` in the dataset. This UUID is used in other fields to tie a ``person`` to a ``posting`` or ``incident``.


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

``Ye Win Oo``, ``510 Light Infantry Battalion in Nansang Township``

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the ``about_entity:ref:claim``. This field can be manually added by a researcher or automatically populated by the system after import. For a ``person`` best practice is to use the ``name:annotation`` in this field.


name:annotation
=====================

Description
~~~~~~~~~~~

Fullest name of the person as evidenced by citations. This may include a given name, surname, middle name(s), as well as other names depending on the specific context.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``Zeyar Aung``, ``Myo Moe Aung‡``

Guidance on use
~~~~~~~~~~~~~~~

For a ``person`` this field only used if the citation evidences the fullest name of a person, which is defined as the name with the highest number of characters. Ranks, titles, or positions held should not be entered in this field as they are captured in other fields.

As with all annotation fields this is the singular display name for the entity. Thus this field can be dynamic and change with ongoing research. For example, a researcher investigating Myanmar may first come across citation ``9f01b1c1-563f-4b40-a534-b91c7e1a5062`` for the ``person`` of ``Zeya Aung`` (which has nine characters) which would be entered in ``name:annotation``. Next they may come across another citation ``4c0aaa5d-a147-4f1c-91d8-46d005be1a04`` that evidences the same person, but gives a name of ``Zayar Aung`` (with 10 characters). This longer which would be entered in ``name:annotation``, and ``Zeya Aung`` in the previous entry tied to citation ``9f01b1c1-563f-4b40-a534-b91c7e1a5062`` would be cleared. Finally, the researcher may come across citation ``c0b4b224-6432-45a5-854d-148d76af0ffa`` which would evidence the name of ``Zeyar Aung`` (with 10 characters). As there are two names, both with 10 characters each, the researcher would use the agreement of the name starting with "Zeya" to evidence ``Zeyar Aung`` as the ``name:annotation``, and ``Zeyar Aung`` in the previous entry tied to citation ``4c0aaa5d-a147-4f1c-91d8-46d005be1a04`` would be cleared

When there are two persons who may be the same person, but citations have not confirmed they are the same person, the symbol ‡ can be applied after the last character in their ``name:annotation`` to help visually identify them in their display name. A corresponding ``public_notes:meta`` should be entered to explain why the symbol ‡ has been used.


Person: Other Names
============================

Attribute name
~~~~~~~~~~~~~~

``::person:other_names``

Description
~~~~~~~~~~~

Other names used to identify a person.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.


Example of use
~~~~~~~~~~~~~~

``Virgilio Daniel Méndez Bazan``, ``Virgilio Daniel Mendez Bazán``

Guidance on use
~~~~~~~~~~~~~~~

Different sources will spell a person's name in different ways. We choose and record a canonical version of a person's name in the `Person: Name` field. All other spellings that we have found are treated as aliases and stored in this field. Titles, roles, honorifics and other attributes that are more correctly linked to a person's posting in a unit are recorded in `Person Posting`_ claims.

Person: Country
========================

Attribute name
~~~~~~~~~~~~~~

``::person:country``

Description
~~~~~~~~~~~

Country where a unit that a person is a member of is located.

Attribute type
~~~~~~~~~~~~~~

Text, controlled vocabulary

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``mx``

Guidance on use
~~~~~~~~~~~~~~~

Values for this field are chosen from the list of ISO 3166-1 alpha-2 codes, which can be found (`on the ISO website <https://www.iso.org/obp/ui/#search/code/>`__ and on `Wikipedia <https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Officially_assigned_code_elements>`__. This field does not denote the citizenship or country of origin of a person. Rather, it denotes where a unit they are a member of is located. For example, if ``1 Batallón de Infantería`` is located in Juarez, Mexico, the unit will be assigned a value of ``mx`` in the field `Unit Identity: Country`_. Any person who is a member of that unit will be assigned a value of ``mx`` in the field `Person: Country`_ as well. A person may have multiple entries for `Person: Country`_ where our research shows they or a unit they are a member of is deployed to different countries.

Person: Earliest Precise Date
======================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Person: Latest Precise Date
====================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Person: Earliest Imprecise Date
========================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Person: Latest Imprecise Date
======================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Person: Date range is a Start Date
===========================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Person: Date range is an End Date
==========================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Person: Research Comments
==================================

Attribute name
~~~~~~~~~~~~~~

``::person:claim:comments``

Description
~~~~~~~~~~~

Observations specific to the process of reviewing data in this claims, including fixes, refinements and other suggestions.

Attribute type
~~~~~~~~~~~~~~

Text

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``Parent person missing``, ``Possible duplicate - merge?``

Guidance on use
~~~~~~~~~~~~~~~

Staff Researchers use this attribute to exchange feedback about the data in the claim. This may included changes needed, references to sources that the owner of the claim might look at, and other observations that can improve the quality of the data. Data stored in this attribute are not intended for publication. The comments attribute is common to all claim types in the SFM data model.

Person: Research Owner
===============================

Attribute name
~~~~~~~~~~~~~~

``::person:claim:reseacher``

Description
~~~~~~~~~~~

Initials of Staff Reseacher who first created the person.

Attribute type
~~~~~~~~~~~~~~

Text

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``TL``, ``TW``, ``MM``,``NP``

Guidance on use
~~~~~~~~~~~~~~~

This attribute allows researchers keep track of claims they have created. It  may be used for arbitrary grouping and tagging of specific sets of claims if needed. This type of attribute is common to all types of claim in the SFM data model.

Person: Research Status
================================

Attribute name
~~~~~~~~~~~~~~

``:person:claim:status``

Description
~~~~~~~~~~~

The place of a claim in the research workflow.

Attribute type
~~~~~~~~~~~~~~

Number range from 0 to 3

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``1``

Guidance on use
~~~~~~~~~~~~~~~

Staff Researchers use this attribute to indicate where a claim stands in the research workflow between the first cut of a claim, review by other researchers, and final readiness for use in analysis or for publication. The values to be used in this attribute are taken from the below list:

- ``X``: Claim should be deleted.
- ``0``: First commit. This claim has just been added and needs review.
- ``1``: Fixes needed. A reviewer has made comments that need to be addressed, which will be recorded in the `Unit Identity: Research Comments`_ attribute.
- ``2``: Fixes made. The owner of this data has addressed the reviewer's comments.
- ``3``: Clean. A final check has been made by a reviewer, and this claim can be used in analysis and can be published.

This type of attribute is common to all claims in the SFM data model.
