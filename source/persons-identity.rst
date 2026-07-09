Person
######

The :ref:`person` claim type describes basic identifying information about a :ref:`person`: their name, aliases and associated time ranges with them. Claims of this type are grouped together with :ref:`Posting` (describing postings to different units) which tracks the person's career. There are also several fields in development to capture other aspects about persons.

Person: Summary of claim attributes 
***********************************

The table below summarizes the following dimensions of :ref:`person` claims:

 - Attribute label: a human readable label for the attribute
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the attribute
 - Key name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-person-fields.csv
   :header-rows: 1


Person: Details of claim attributes
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

``unit``, ``positioning``, ``relation``, ``person``, ``posting``, ``incident``

Guidance on use
~~~~~~~~~~~~~~~

Entering ``person`` defines the claim and defines the relevant fields to be used in further data entry about a :ref:`person`. For quality assurance purposes, entering ``person`` should create an error if there is any entry for fields tied to other claim types, such as :ref:`posting`.


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

Claims are marked ``accepted`` when all of the data can be entered in accordance with the guidance of this handbook. The ``conflict`` flag is used whenever a claim conflicts with another claim (or claims) and a review of citations show it to be the incorrect or false claim. A :ref:`public_notes:meta <person-public-notes>` should always accompany any ``conflict`` claim.

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

Researchers may use this field to make temporary notes or leave temporary comments intended for others in the research team about a claim. These should eventually be addressed and the field cleared by the researcher or research team. If the claim needs an explanatory note or comment to be better understood, then that should be entered in the :ref:`public_notes:meta <person-public-notes>` field.


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

Every claim must have at least one citation to evidence the data in the claim. When two or more citations are needed to evidence a claim then a corresponding explanatory note should be entered in the :ref:`public_notes:meta <person-public-notes>` field. This field is for the Universally Unique Identifier (UUID) for each citation, found in the :ref:`source:access_point_id:admin` field in the Sources sheet. When multiple citations are needed every UUID should be semi-colon separated.

.. _person-about-entity:

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

Every entity has a Universally Unique Identifier (UUID) to distinguish it from any other entity. For a :ref:`person` this UUID distinguishes them from any other :ref:`person` in the dataset. This UUID is used in other fields to tie a :ref:`person` to a :ref:`posting` or :ref:`incident`.

A :ref:`person` from one citation is never assumed to be the same :ref:`person` from another citation based on an exact or near match of their name. Instead the :ref:`posting` is used to determine whether two people with the same or similar names are the same :ref:`person`. For example, if a citation states ``John Alfred Smith`` was commander of ``Police Station 1`` and another states ``John Smith`` was the commander of ``Police Station 1`` they would be treated as the same person given the match of :ref:`posting` as well as their similar names. However, if one citation stated ``John Alfred Smith`` was the commander of ``Police Station 2`` they would not be treated as the same person as the ``John Alfred Smith`` who was commander of ``Police Station 1`` since there is no match of a :ref:`posting`.

Determining whether one :ref:`person` held multiple postings is based on some match of postings among different citations. For example, if one citation stated ``John Alfred Smith`` was commander of ``Police Station 1`` and another citation stated ``J. Smith`` was commander of ``Police Station 3`` there would be no match and these should be coded as two separate people each with their own :ref:`about_entity:ref:claim <person-about-entity>`. If then a third citation stated that during the career of ``John Smith`` he was commander of ``Police Station 1``, ``Police station 15`` and ``Police Station 3`` then all of these would be treated as the same person given the match of at least one :ref:`posting` across all citations and the similar names of the person in each citation.


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

n/a

Example of use
~~~~~~~~~~~~~~

``Ye Win Oo``

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the :ref:`about_entity:ref:claim <person-about-entity>`` which combines the various elements of the claim into a single text field. This field can be manually added by a researcher or automatically populated by the system after import. For a :ref:`person` best practice is to use the :ref:`name:annotation <person-name-annotation>` in this field.


.. _person-name-annotation:

name:annotation
===============

Description
~~~~~~~~~~~

Fullest name of the person as evidenced by citations. This may include a given name, surname, middle name(s), as well as other names depending on the specific context.

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

``Zeyar Aung``, ``Myo Moe Aung‡``

Guidance on use
~~~~~~~~~~~~~~~

As with all annotation fields, this field is the singular display name for the entity. For a :ref:`person` this field is only used if the citation evidences the fullest name of a person, which is defined as the name with the highest number of characters. Ranks, titles, or positions held should not be entered in this field as they are captured in other fields.

This field can be dynamic and change with ongoing research. For example, a researcher investigating Myanmar may first come across citation ``9f01b1c1-563f-4b40-a534-b91c7e1a5062`` for the :ref:`person` of ``Zeya Aung`` (a name which has nine characters). This would be entered in :ref:`name:annotation <person-name-annotation>`. Next, they may come across another citation ``4c0aaa5d-a147-4f1c-91d8-46d005be1a04`` that evidences the same :ref:`person` but gives a name of ``Zayar Aung`` (with 10 characters). This longer which would be entered in :ref:`name:annotation <person-name-annotation>`. ``Zeya Aung`` in the previous entry tied to citation ``9f01b1c1-563f-4b40-a534-b91c7e1a5062`` would now be entered only in :ref`person:names:assertion`, and the :ref:`name:annotation <person-name-annotation>` for that entry would be cleared. Finally, the researcher may come across citation ``c0b4b224-6432-45a5-854d-148d76af0ffa`` which would evidence the name of ``Zeyar Aung`` (with 10 characters). As there are two names, both with 10 characters each, the researcher would use the agreement of the name starting with "Zeya" to evidence ``Zeyar Aung`` as the :ref:`name:annotation <person-name-annotation>`, and ``Zayar Aung`` in the previous entry tied to citation ``4c0aaa5d-a147-4f1c-91d8-46d005be1a04`` would be cleared.

Occasionally there are two people who may be the same :ref:`person` due to a near or exact match of names, and lack of any conflicting information (such as :ref:`postings`, dates of birth or death, or any other career or biographical information), but no citations have been found to confirm they are the same :ref:`person`. In these cases the symbol ‡ can be applied after the last character in their :ref:`name:annotation <person-name-annotation>` to help visually identify them in their display name. A corresponding :ref:`public_notes:meta <person-public-notes>` should be entered to explain why the symbol ‡ has been used.


person:names:assertion
======================

Description
~~~~~~~~~~~

Any name given for person from citation.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:assertion/person:names``

Example of use
~~~~~~~~~~~~~~

``Virgilio Daniel Méndez Bazan``, ``Virgilio Daniel Mendez Bazán``

Guidance on use
~~~~~~~~~~~~~~~

Any name for a person used in the citation should be entered in this field. While the :ref:`name:annotation <person-name-annotation>` field is only used for a single, most complex value, this field is used for any name a citation uses for a person. Thus, this field serves to capture "aliases" of a person, which also includes any typos or misspellings that may exist in the citation.

Ranks, titles, or positions held should not be entered in this field as they are captured in other fields.


country:annotation
==================

Description
~~~~~~~~~~~

Country person is associated with for grouping claims.

Attribute type
~~~~~~~~~~~~~~

Text, controlled vocabulary

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:annotation/country``

Example of use
~~~~~~~~~~~~~~

``mx``, ``ph``

Guidance on use
~~~~~~~~~~~~~~~

Values for this field are chosen from the list of ISO 3166-1 alpha-2 codes, which can be found (`on the ISO website <https://www.iso.org/obp/ui/#search>`_). This field is used to aid grouping persons into datasets related to specific countries and does not denote the citizenship or country of origin of a person. The specific country code should be chosen based on any related :ref:`posting` the :ref:`person` holds, or any other contextual information from citations about the :ref:`person`.


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


person:genders:assertion
========================

Description
~~~~~~~~~~~

Indicators of a person's sex or gender identity, as inferred from pronouns used in the text of available sources.

Attribute type
~~~~~~~~~~~~~~

Open list, single choice.

Status
~~~~~~

This is a draft field, to be finalized.

Key name
~~~~~~~~

``:assertion/person:genders``

Example of use
~~~~~~~~~~~~~~

``male``, ``female``, ``other``

Guidance on use
~~~~~~~~~~~~~~~

This attribute is used to capture data about the gender of a person, as determined only by the pronouns ("her", "she", "his", "him", etc.) used in any available textual sources about this person. Data entry based on these pronouns is based on the coding of pronouns as "masculine" for ``male`` and "feminine" for ``female`` from `Global Affairs at UC Davis <https://globalaffairs.ucdavis.edu/iae/graduate/language-tips/pronouns-and-gender>`_. We do not infer a person's gender from their name or images of them. 

Echoing the definition used in the `FOAF standard <http://xmlns.com/foaf/spec/#term_gender>`_, the :ref:`person:genders:assertion` attribute is not intended to capture the full range of possible biological, social and sexual associated with the word "gender". This attribute open to include alternatives that are expressed within the available sources about a person.

Where the sources contain no textual indication about the person's gender, the attribute should be left blank.


person:account_type:assertion
=============================

Description
~~~~~~~~~~~

The name of an online platform or service on which the person holds an account.

Attribute type
~~~~~~~~~~~~~~

Open list, single choice.

Status
~~~~~~

This is a draft field, to be finalized.


Key name
~~~~~~~~

``:assertion/person:account-type``

Example of use
~~~~~~~~~~~~~~

``facebook``, ``telegram``, ``youtube``

Guidance on use
~~~~~~~~~~~~~~~

This attribute is used to record the name of the online platform of service on which a person holds an account. The name is chosen from a list of available platforms and services, which will be updated as required. Where a person has more than one account, on the same or different platforms, a new claim should be created.


person:account_id:assertion
===========================

Description
~~~~~~~~~~~

The account name used by the person on a specific online platform or service.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This is a draft field, to be finalized.

Key name
~~~~~~~~

``:assertion/person:account-id``

Example of use
~~~~~~~~~~~~~~

``CapitaineIb226`` (on X)

Guidance on use
~~~~~~~~~~~~~~~

This attribute is used to record the account name held by the person on a specific online platform or service. Where a person has more than one account, on the same or different platforms, a new claim should be created.


person:media_description:annotation
====================================

Description
~~~~~~~~~~~

Short textual description of material found in a media resource that provides information about how a person looks or sounds.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This is a draft field, to be finalized.

Key name
~~~~~~~~

``:annotation/person:media-description``

Example of use
~~~~~~~~~~~~~~

"Face and shoulders of Bosco Ntaganda, in military uniform with hat, tie and lapels, backed by two other men in combat fatigues armed with rifles. Taken at a news conference in January 2009."

Guidance on use
~~~~~~~~~~~~~~~

This attribute is used to store a brief description of the content of external media. The description should be sufficient for the analyst to quickly appraise what they can expect to find in the media about what the person looks or sounds like. A new row is created for each distinct media item about the person.

.. _person-public-notes:

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

For a :ref:`person` the only allowed entry for this field is ``claim``.
