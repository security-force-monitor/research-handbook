Unit
####

A :ref:`unit` claim type contains information about the identity of the :ref:`unit`, such as its name, aliases, classification, the country in which it operates, and the duration of its existence.

Unit Identity: Summary of claim attributes 
******************************************

The table below summarizes the following dimensions of :ref:`unit` claims:

 - Attribute label: a human readable label for the attribute
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the attribute
 - Key name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-unit-fields.csv
   :header-rows: 1


Unit: details of claim attributes
*********************************

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

Entering ``unit`` defines the claim and defines the relevant fields to be used in further data entry about a :ref:`unit`. For quality assurance purposes, entering ``unit`` should create an error if there is any entry for fields tied to other claim types, such as :ref:`positioning` or :ref:`relation`.

.. _unit-status-meta:

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

Claims are marked ``accepted`` when all of the data can be entered in accordance with the guidance of this handbook. The ``conflict`` flag is used whenever a claim conflicts with another claim (or claims) and a review of citations show it to be the incorrect or false claim. A :ref:`public_notes:meta <unit-public-notes-meta>` should always accompany any ``conflict`` claim.

.. admonition:: Example

    Citations reference a unit 757 Light Infantry Battalion in 2008 and again in 2019 as part of the Myanmar Army. This conflicts with other citations before and after these dates which list all light infantry battalions of the army and do not include this unit. Further citations establish a general numbering practices of the army which provides further evidence that no such battalion exists. The :ref:`unit` and other claims related to the 757 Light Infantry Battalion should still be entered into the dataset, flagged with :ref:`status:meta <unit-status-meta>` of the ``conflict``, and have the status fully explained in a :ref:`public_notes:meta <unit-public-notes-meta>`.

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

Researchers may use this field to make temporary notes or leave temporary comments intended for others in the research team about a claim. These should eventually be addressed and the field cleared by the researcher or research team. If the claim needs an explanatory note or comment to be better understood, then that should be entered in the :ref:`public_notes:meta <unit-public-notes-meta>` field.


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

Every claim must have at least one citation to evidence the data in the claim. When two or more citations are needed to evidence a claim then a corresponding explanatory note should be entered in the :ref:`public_notes:meta <unit-public-notes-meta>` field. This field is for the Universally Unique Identifier (UUID) for each citation, found in the :ref:`ref:source:access_point_id:admin` field in the Sources sheet. When multiple citations are needed every UUID should be semi-colon separated.


.. _unit-about-entity:

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

Every entity has a Universally Unique Identifier (UUID) to distinguish it from any other entity. For a :ref:`unit` this UUID distinguishes them from any other :ref:`unit` in the dataset. This UUID is used in other fields to tie a :ref:`unit` to a :ref:`positioning`, :ref:`relation`, :ref:`posting`, or :ref:`incident`.

If a unit undergoes a change in name, that unit should be treated as a separate, distinct unit and given its own UUID.


.. admonition:: Example

    A citation establishes that a :ref:`unit`, named the ``Tiger Forces`` in Syria were renamed the ``25 Anti-Terrorism Division`` in 2019. The division continued to serve with the same general functions as before, and continued to be commanded by the same person. However, because a citation clearly evidenced that there had been a change in the name of the :ref:`unit`, the ``25 Anti-Terrorism Division`` should be treated as a distinct :ref:`unit` with a separate ``about_entity:ref:claim`` from the ``Tiger Forces``.


about_entity:name:qa
====================

Description
~~~~~~~~~~~

Field that provides human readable name for the claim.

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

``510 Light Infantry Battalion``

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the :ref:`about_entity:ref:claim <unit-about-entity>` This field can be manually added by a researcher or automatically populated by the system after import. For a :ref:`unit` best practice is to use the :ref:`name:annotation <unit-name-annotation>` in this field.

.. _unit-name-annotation:

name:annotation
===============

Description
~~~~~~~~~~~

Fullest name of the unit as evidenced by citations.

Attribute type
~~~~~~~~~~~~~~

Text string.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:annotation/name``

Example of use
~~~~~~~~~~~~~~

``3 Armoured Division``, ``3 Compañía de Infantería No Encuadrada``, ``7 Military Operations Command``

Guidance on use
~~~~~~~~~~~~~~~

The Security Force Monitor strives to create a single canonical version of a unit's name that is based on citations, highlights differences between peer units, and makes the data easier for a general audience to understand. Similar to a :ref:`person`, wherever possible we will choose the most complex version of a unit’s name that can be evidenced by a citation.

.. admonition:: Example

    ``3 Armoured Division`` would be the entry for :ref:`name:annotation <unit-name-annotation>`, rather than the shorter ``3 Division`` (which may have more citations) would only be used in :ref:`unit:names:assertion`.

Units have several unique characteristics that require additional and unit specific methodological guidance. Units in security forces are arranged in hierarchies and share similar names with their peer units. However, while citations may establish general guidance for how units of a certain type should be named, each individual unit may not have citations evidencing the "complete" or "canonical" name of the unit.

.. admonition:: Example

    ``Police Divisions`` are a class of police units in Nigeria established by law. There are over 1000 units of this type nationwide. However, each individual ``Police Division`` may not have a citation for their full, formal name. For example, a citation references the ``Achall Division`` police unit in Anambra State. There is no citation for the fuller, more formal ``Achalla Police Division``. In this case, and similar cases, the Monitor would create a claim with ``Achalla Police Division`` in the :ref:`name:annotation <unit-name-annotation>` with citation ``50a65841-b429-4e77-b7e4-ac937dd2ae72``. This citation was created to specifically note the name for the unit has been created by the Monitor. Best practice is to also include any citations that provide contextual information for the standardized name, as well as a ``public_notes:meta``.

As many units do have standardized names, the Monitor follows several "stylistic" naming conventions for the :ref:`name:annotation <unit-name-annotation>` field:

.. admonition:: Numerals in Unit Names

    The Monitor always standardizes the :ref:`name:annotation <unit-name-annotation>` to include numerals rather than spelling out numerals.
    
    There may be a unit of which we only have citations for a ``Fourth Battalion``. In this case, the Monitor would create a claim with the :ref:`name:annotation <unit-name-annotation>` for the unit as ``4 Battalion`` using citation ``50a65841-b429-4e77-b7e4-ac937dd2ae72``.
    
    In an effort to standardize names across all countries, the Monitor generally uses Arabic numerals in the :ref:`name:annotation <unit-name-annotation>` field. Where warranted by citations the Monitor will use Roman numerals like ``V`` or ``XI`` instead of ``5`` or ``11`` respectively.

.. admonition:: Numbers Before Words in Unit Names
    
    The Monitor lists the numeral in any :ref:`name:annotation <unit-name-annotation>` before any textual element of the name of the unit. This is done because the number of the unit is often the most distinguishing feature of a name.
    
    Most English language sources for Myanmar Army units reference the name of the unit and then the number, for example ``Light Infantry Battalion 510``. If there was no citation for ``510 Light Infantry Battalion`` the Monitor would create a claim with ``510 Light Infantry Battalion`` in the :ref:`name:annotation <unit-name-annotation>` with citation ``50a65841-b429-4e77-b7e4-ac937dd2ae72``.


.. admonition:: Ordinal Indicators
    
    The Monitor does not use ordinal indicators like ``1st`` or ``3rd`` in the :ref:`name:annotation <unit-name-annotation>` for units. Instead these will be listed in the :ref:`unit:names:assertion` field.


.. admonition:: Language of Unit Names
    
    The Monitor uses the name in the official or most commonly used language of the country where possible. Generally this is based on the Monitor's capacity at the time of the particular research project.
    A unit in the Mexican Army would be called by its name in Spanish (``10 Regimiento de Caballería Motorizado``), rather than the English translation ( ``10 Motorized Cavalry Regiment``).


.. admonition:: Distinguishing Units with Same Name
    
    In cases where multiple units have the same name the Monitor will distinguish them by adding unique identifying text in parentheses based on the unit's location or parent unit.
    For example, there are multiple "Central Police Station" formations across Nigeria, some based in the same state. To better distinguish these are separate, distinct units the Monitor added information on where the units were located to the name field for instance ``Central Police Station (Awka, Anambra State)``. Another example is in Myanmar where there are multiple different units all called "1 Tactical Operations Command". To distinguish them the Monitor added the parent unit inside of parentheses for each tactical operations command, such as ``1 Tactical Operations Command (1 Military Operations Command)``.

In some cases, we are aware that a unit exists because of what sources tell us about the general organizational structure. However, in some cases sources do not provide us with sufficient information to give these units a name, or to be precise about the nature of relationships between units. To resolve issues of this nature we use the concepts of "Unnamed" and "Unknown" units. We have written more about this in the Handbook page :ref:`Unknown and unnamed units`.


unit:names:assertion
====================

Description
~~~~~~~~~~~

Any name given for a unit from citation.

Attribute type
~~~~~~~~~~~~~~

Text string.

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:assertion/unit:names``

Example of use
~~~~~~~~~~~~~~

``Deuxième RM``, ``GFSN``, ``IB-148``, ``IB (148)``, ``Infantry Battalion 148``

Guidance on use
~~~~~~~~~~~~~~~

Any name for a unit used in the citation should be entered in this field. While the :ref:`name:annotation <unit-name-annotation>` field is only used for a single, most complex value, this field is used for any name a citation uses for a unit. Thus, this field serves to capture "aliases" of a unit, which also includes any typos or misspellings from the citation.

Ordinal indicators, such as "2nd" or "10/o", should be entered in this field.


unit:classifications:assertion
==============================

Description
~~~~~~~~~~~

A general descriptor for the unit, often matches a branch or branches of the unit.

Attribute type
~~~~~~~~~~~~~~

Text, controlled vocabulary.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:assertion/unit:classifications``

Example of use
~~~~~~~~~~~~~~

``Army``, ``Ejército``, ``Police``, ``Military``, ``Military Police``, ``Joint Operation``


Guidance on use
~~~~~~~~~~~~~~~

We use classifications to describe the basic nature of a specific unit and to assist investigations of potential linkages between reports of human rights abuses and the Security Force Monitor's dataset. As alleged perpetrators are usually identified in general terms of "soldiers" and "police" this field is important as a first step to understand potential linkages between a :ref:`unit`, :ref:`person` and :ref:`incident`.

The :ref:`unit:classifications:assertion` field will contain a mix of standard terms and country-specific terms used to describe security force branches. In choosing terms to include in the :ref:`unit:classifications:assertion` field we try to include terms that are used by country experts as well as those that are common terms that would be meaningful to a general audience. We also try to be economical and create as few, distinct terms as possible.

Units may have more than one classification. Usually this will be when a unit can have both "generic" and "specific" classifications.

.. admonition:: Example

    Units which are part of the army of a country may be coded as having a classification of ``Army`` as well as a classification of ``Military``, whereas units which are part of the navy of a country would have classifications of ``Navy`` and ``Military``. For both the army and navy unit their respective classifications are correct, the army and the navy are part of the military. Critically, this enables the Monitor or users of the Monitor's data to properly analyze allegations against "soldiers" and "members of the army" in the country. In the case of "soldiers" this analysis should include every unit with the classification of ``Military`` while if there is greater specificity of "members of the army" would mean excluding any unit with the classification of ``Navy`` and focusing only on those units with a classification of ``Army.``

Every unit which has a "specific" classification should also have the "generic" classification as well.

.. admonition:: Example

    Units that have an ``Army`` classification should also have a :ref:`unit:classifications:assertion` of ``Military``.

Classifications are "pushed up" to parent units or the :ref:`relation:related_unit:refs:assertion` units, meaning that a :ref:`unit` should have all of the :ref:`unit:classifications:assertion` of any subordinate :ref:`unit`. For example, the :ref:`unit` representing the head of state or head of government which acts as commander-in-chief of the armed forces would have a :ref:`unit:classifications:assertion` of ``Military``, among others.


country:annotation
==================

Description
~~~~~~~~~~~

Associated country of the unit used for grouping claims.

Attribute type
~~~~~~~~~~~~~~

Text, controlled vocabulary.

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

Values for this field are chosen from the list of ISO 3166-1 alpha-2 codes, which can be found (`on the ISO website <https://www.iso.org/obp/ui/#search>`_). This field is used to aid grouping units into datasets related to specific countries and does not denote the country of origin of a unit. The specific country code should be chosen based on any related :ref:`positioning` the :ref:`unit` holds, or any other contextual information from citations about the :ref:`unit`.


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

.. _unit-public-notes-meta:

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

For a :ref:`unit` the only allowed entry for this field is ``claim``.
