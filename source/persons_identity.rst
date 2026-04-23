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

A ``person`` from one citation is never assumed to be the same ``person`` from another citation based on an exact or near match of their name. Instead the ``posting`` is used to determine whether two people with the same or similar names are the the same ``person``. For example, if a citation states "John Alfred Smith" was commander of "Police Station 1" and another states "John Smith" was the commander of "Police Station 1" they would be treated as the same person given the match of ``posting`` as well as their similar name. However, if one citation stated "John Alfred Smith" was the commander of "Police Station 2" they would not be treated as the same person as the "John Alfred Smith" who was commander of "Police Station 1" since there is no match of a ``posting``.

Determining whether one person held multiple postings is based on some match of postings among different citations. For example, if one citation stated "John Alfred Smith" was commander of "Police Station 1" and another citation stated "J. Smith" was commander of "Police Station 3" there would be no match and these should be coded as two seperate people each with their own `about_entity:ref:claim`. If then a third citation stated that during the career of "John Smith" he was commander of "Police Station 1", "Police station 15" and "Police Station 3" then all of these would be treated as the same person given the match of at least one ``posting`` across all citations and the similar names of the person in each citation.


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

This field provides a human readable counterpart to the ``about_entity:ref:claim`` which combines the various elements of the claim into a single text field. This field can be manually added by a researcher or automatically populated by the system after import. For a ``person`` best practice is to use the ``name:annotation`` in this field.


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

As with all annotation fields this field is the singular display name for the entity. For a ``person`` this field only used if the citation evidences the fullest name of a person, which is defined as the name with the highest number of characters. Ranks, titles, or positions held should not be entered in this field as they are captured in other fields.

This field can be dynamic and change with ongoing research. For example, a researcher investigating Myanmar may first come across citation ``9f01b1c1-563f-4b40-a534-b91c7e1a5062`` for the ``person`` of ``Zeya Aung`` (a name which has nine characters). This would be entered in ``name:annotation``. Next they may come across another citation ``4c0aaa5d-a147-4f1c-91d8-46d005be1a04`` that evidences the same person, but gives a name of ``Zayar Aung`` (with 10 characters). This longer which would be entered in ``name:annotation``, and ``Zeya Aung`` in the previous entry tied to citation ``9f01b1c1-563f-4b40-a534-b91c7e1a5062`` would be cleared. Finally, the researcher may come across citation ``c0b4b224-6432-45a5-854d-148d76af0ffa`` which would evidence the name of ``Zeyar Aung`` (with 10 characters). As there are two names, both with 10 characters each, the researcher would use the agreement of the name starting with "Zeya" to evidence ``Zeyar Aung`` as the ``name:annotation``, and ``Zeyar Aung`` in the previous entry tied to citation ``4c0aaa5d-a147-4f1c-91d8-46d005be1a04`` would be cleared.

When there are two persons who may be the same person, but citations have not confirmed they are the same person, the symbol ‡ can be applied after the last character in their ``name:annotation`` to help visually identify them in their display name. A corresponding ``public_notes:meta`` should be entered to explain why the symbol ‡ has been used.


person:names:assertion
============================

Description
~~~~~~~~~~~

Any name given for person from citation.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is required.


Example of use
~~~~~~~~~~~~~~

``Virgilio Daniel Méndez Bazan``, ``Virgilio Daniel Mendez Bazán``

Guidance on use
~~~~~~~~~~~~~~~

Any name for a person used in the citation should be entered in this field. While the ``name:annotation`` field is only used for a single, most complex value, this field is used for any name a citation uses for a person. Thus this field serves to capture "aliases" of a person, which also includes any typos or mispellings that may exist in the citation.

Ranks, titles, or positions held should not be entered in this field as they are captured in other fields.


country:annotation
========================

Description
~~~~~~~~~~~

Country person is associated with for grouping claims.

Attribute type
~~~~~~~~~~~~~~

Text, controlled vocabulary

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``mx``, ``ph``

Guidance on use
~~~~~~~~~~~~~~~

Values for this field are chosen from the list of ISO 3166-1 alpha-2 codes, which can be found (`on the ISO website <https://www.iso.org/obp/ui/#search>`). This field is used to aid grouping persons into datasets related to specific countries and does not denote the citizenship or country of origin of a person. The specific country code should be choosen based on any related `posting` the `person` holds, or any other contextual information from citations about the `person`.

first_precise:range
======================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

last_precise:range
====================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

first_imprecise:range
========================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

last_imprecise:range
======================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

starting:range
===========================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

ending:range
==========================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


starting_context:range
==========================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

ending_context:range
==========================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


public_notes:meta
============================

Description
~~~~~~~~~~~

Additional context or details about the claim for a public audience.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.


Example of use
~~~~~~~~~~~~~~

``Citation @3c981094-fb7b-4b78-b8f6-b525a03f72b5, published on 15 July 2019, states that numerous military appointments occurred "last week". This is understood to mean the week starting the previous Sunday 7 July 2019 through Saturday 13 July 2019.``

Guidance on use
~~~~~~~~~~~~~~~

This field should be used whenever any claim requires additional explanation or otherwise is not clearly and directly stated in the citation. In the example of use above a citation published on 15 July 2019 refers to something happening "last week" and as a result a researcher has determinef the previous Sunday 7 July 2019 through Saturday 13 July 2019 should be entered into the appropriate fields of ``first_imprecise:range`` and ``last_imprecise:range``. As that range would not be immediately clear to a public auidence since neither date is directly referenced in the text of the citation, the researcher should explain how those dates were identified as the dates evidenced by the citation.
