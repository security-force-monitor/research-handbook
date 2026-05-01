Unit
####

"Unit" is a claim type that contains information about the identity of the unit, such as its name, aliases, classification (or branch), the country in which is operates, and the duration of its existence. They are connected together with ``Relation`` claims, resulting in a hierarchy of units.

Unit Identity: Summary of claim attributes 
******************************************

The table below summarises the following dimensions of Unit Identity claims:

 - Attribute label: a human readable label for the attribute
 - Attribute name: a unique machine-readable name for the attribute, used during data capture
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the field
 - Conformed name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-unit-fields.csv
   :header-rows: 1
   :delim: tab

Unit Identity: details of claim attributes
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

``unit``

Guidance on use
~~~~~~~~~~~~~~~

Entering ``unit`` defines the claim and establishes the fields to be used in further data entry about a unit
.


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

Every entity has an Universally Unique Indentifier (UUID) to distinguish it from any other entity. For a ``unit`` this UUID distinguishes them from any other ``unit`` in the dataset. This UUID is used in other fields to tie a ``unit`` to a ``positioning``, ``relation``, ``posting``, or ``incident``.

If a unit undergoes a change in name, that unit should be treated as a seperate, distinct unit and given its own UUID. For example, 25 Division of Syria.


about_entity:name:qa
==================================

Description
~~~~~~~~~~~

Field that provides human readible name for the claim.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``510 Light Infantry Battalion``

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the ``about_entity:ref:claim`` This field can be manually added by a researcher or automatically populated by the system after import. For a ``unit`` best practice is to use the ``name:annotation`` in this field.


name:annotation
=====================

Description
~~~~~~~~~~~

Fullest name of the unit as evidenced by citations.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``3 Armoured Division``, ``3 Compañía de Infantería No Encuadrada``, ``7 Military Operations Command``

Guidance on use
~~~~~~~~~~~~~~~

As different sources will spell a unit's name in different ways the Security Force Monitor works to create a single canonical version of a unit's name based on sources and standardized to match the overall structure of and reporting about the security forces:

.. admonition:: Examples

    Example A: ``Police Divisions`` are a class of police units in Nigeria. There are over 1000 units of this type nationwide. However, each individual ``Police Division`` may not have a citation for their formal name such as ``Lagos Police Division``, but only have a citation (or numerous citations) for the less formal ``Lagos Division``. The Monitor would list the name of the unit as ``Lagos Police Division`` and the claim would include a comment about the methodology behind that choice. The less formal ``Lagos Division`` name would be entered in the `Unit Identity: Other Names`_ field.

    
    Example B: Army units of a country may follow a naming convention of a number and then name of unit: e.g. ``3 Battalion`` or ``25 Brigade``. There may be a unit of which we only have citations for a variation on that: e.g. ``Fourth Battalion``. In this case, the Monitor would list the name of the unit as ``4 Battalion`` with a note about the methodology behind that choice. The ``Fourth Battalion`` name variant would be entered in a claim about `Unit Identity: Other Names`_.

Standardizations don't have specific sources, so we have created a specific source to use in these cases. Where a value in `Unit Identity: Name`_ has been standardized, a citation with the following title will be associated with it: "Name standardized in accordance with Security Force Monitor research".

Additionally, wherever possible, we will choose the most complete and complex version of a unit’s name that can be evidenced by a source:

.. admonition:: Examples



    Example C: ``3 Armoured Division`` would be the entry, rather than the more informal ``3 Division`` (which may have more citations).

The Monitor does not use ordinal indicators like ``1st`` or ``3rd`` in the name of an Unit. Instead these will be listed in the `Unit Identity: Other Names`_ field.

The Monitor uses the name in the official (local) language of the country where appropriate and/or possible.

.. admonition:: Examples
   
   Example D: A unit in the Mexican Army would be called by its name in Spanish (``10 Regimiento de Caballería Motorizado``), rather than the English translation ( ``10 Motorized Cavalry Regiment``).

In an effort to standardize names across all countries, the Monitor generally uses Arabic numerals in the `Unit Identity: Name`_ field. Where warranted by sources the Monitor will use Roman numerals like ``V`` or ``XI`` instead of ``5`` or ``11`` respectively.

In cases where multiple units have the same name the Monitor will distinguish them by adding unique identifying text based on the unit's location or parent unit.

.. admonition:: Examples

  Example E: There are multiple "Central Police Station" formations across Nigeria, some based in the same state. To better distinguish these are separate, distinct units the Monitor added information on where the units were located to the name field for instance ``Central Police Station (Awka, Anambra State).``\ In Myanmar there have been different units through time both the name Central Regional Military Command. To distinguish them the Monitor added information on when the unit came into existence to the name: ``Central Regional Military Command (post 199)``.


In some cases, we are aware that a unit exist because of what sources tell us about the general organizational structure. However, in some cases sources do not provide us with sufficient information to give these units a name, or to be precise about the nature of relationships between units. To resolve issues of this nature we use the concepts of "Unnamed" and "Unknown" units. We have written more about this in the Handbook page :ref:`Unknown and unnamed units`.


unit:names:assertion
============================

Description
~~~~~~~~~~~

Any name given for a unit from citation.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``Deuxième RM``, ``GFSN``, ``IB-148``, ``IB (148)``, ``Infantry Battalion 148``

Guidance on use
~~~~~~~~~~~~~~~

Any name for a unit used in the citation should be entered in this field. While the ``name:annotation`` field is only used for a single, most complex value, this field is used for any name a citation uses for a unit. Thus this field serves to capture "aliases" of a unit, which also includes any typos or mispellings that may exist in the citation.

Ordinal indicators like "2nd" or "10/o" should be entered in this field.


unit:classifications:assertion
====================

Attribute name
~~~~~~~~~~~~~~

``::unit:classifications``

Description
~~~~~~~~~~~

A general descriptor for the unit, often matches a branch or branches of the unit.

Atrribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``Army``, ``Ejército``, ``Police``, ``Military``, ``Military Police``, ``Joint Operation``


Guidance on use
~~~~~~~~~~~~~~~

We use classifications to describe the basic nature of a specific unit and to assist investigations of potential linkages between reports of human rights abuses and the Security Force Monitor's dataset. As alleged perpetrators are usually identified in general terms of "soldiers" and "police" this field is important as a first step to understand potential linkages between units, persons and incidents. `Unit Identity: Classification` values are useful supplements to those in the `Unit Relations`_ claim type in connecting different units together.

The `Unit Identity: Classification`_ field will contain a mix of standard terms and country-specific terms used to describe security force branches. In choosing terms to include in the `Unit Identity: Classification`_ field we try to include terms that are used by country experts as well as those that are common terms. We also try to be economical and create as few, distinct terms as possible.

.. admonition:: Example

   A standard term we would apply to army units is ``Army``. The equivalent in Mexico would be ``Ejécito``. We would capture both terms in the `Unit Identity: Classification``_ field.

Units may have more than one classification. Usually this will be when a unit can have both "generic" and "specific" classifications.

.. admonition:: Example

    Units which are part of the army of a country may be coded as having a classification of ``Army`` as well as a classification of ``Military``, whereas units which are part of the navy of a country would have classifications of of ``Navy`` and ``Military``. For both the army and navy unit their respective classifications are correct, the army and the navy are part of the military. Critically, this enables the Monitor or users of the Monitor's data to properly analyze allegations against "soldiers" and "members of the army" in the country. In the case of "soldiers" this analysis should include every unit with the classification of ``Military`` while if there is greater specificity of "members of the army" would mean excluding any unit with the classification of ``Navy`` and focusing only on those units with a classification of ``Army.``


country:annotation
=============

Attribute name
~~~~~~~~~~~~~~

``::unit:country``

Description
~~~~~~~~~~~

ISO 3166 two letter code for the country from  which a unit originates.

Atrribute type
~~~~~~~~~~~~~~

String from controlled vocabulary.

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``mx``, ``ug``, ``ng``

Guidance on use
~~~~~~~~~~~~~~~

The `Unit Identity: Country` attribute identifies the country fromt which this unit originates. All entries in this attribute will be two-letter country codes taken from `ISO 3166 <https://www.iso.org/obp/ui/#search>`__. For example, a unit from Nigeria would have the code ``ng`` and a unit from Brazil would have the code ``br``

A unit may only contain a single value in the `Unit Identity: Country`_ attribute. A unit's operations in another country are described using the `Unit Identity: Positioning`_ claim type.


Unit Identity: Date Range is a Start Date
=========================================

Attribute name
~~~~~~~~~~~~~~

``::unit:date-range:starting?``

Description
~~~~~~~~~~

Indicates whether date range, whether precise or imprecise, is the date that a unit was established or founded.

Attribute Type
~~~~~~~~~~~~~~

Boolean

Status
~~~~~~

This attribute is optional.


Example of use
~~~~~~~~~~~~~~

`N`

Guidance on use
~~~~~~~~~~~~~~~

Full guidance on the use of this field can be found in the Handbook page :ref:`Claims with dates`.


Unit Identity: Date Range is an Ending Date
===========================================

Attribute name
~~~~~~~~~~~~~~

``::unit:date-range:ending?``

Description
~~~~~~~~~~

Indicates whether date range, whether precise or imprecise, is the date that a unit was disbanded, dissolved, merged or replaced.

Attribute Type
~~~~~~~~~~~~~~

Boolean

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

`Y`

Guidance on use
~~~~~~~~~~~~~~~

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Unit Identity: Earliest Precise Date
====================================

Attribute name
~~~~~~~~~~~~~~

``::unit:date-range-precise:first``

Description
~~~~~~~~~~

The earliest date in a precise date range for which the claim is valid

Attribute Type
~~~~~~~~~~~~~~

Timestamp

Status
~~~~~~

This attribute is optional

Example of use
~~~~~~~~~~~~~~

``2022-01-22``


Guidance on use
~~~~~~~~~~~~~~~

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


Unit Identity: Latest Precise Date
==================================

Attribute name
~~~~~~~~~~~~~~

``::unit:date-range-precise:last``

Description
~~~~~~~~~~

The latest date in a precise date range for which the claim is valid

Attribute Type
~~~~~~~~~~~~~~

Timestamp

Status
~~~~~~

This attribute is optional

Example of use
~~~~~~~~~~~~~~

``2022-01-22``


Guidance on use
~~~~~~~~~~~~~~~

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


Unit Identity: Earliest Imprecise Date
======================================

Attribute name
~~~~~~~~~~~~~~

``::unit:date-range-imprecise:first`

Description
~~~~~~~~~~

The earliest date in an imprecise date range for which the claim is valid

Attribute Type
~~~~~~~~~~~~~~

Timestamp

Status
~~~~~~

This attribute is optional

Example of use
~~~~~~~~~~~~~~

``2022-01-22``

Guidance on use
~~~~~~~~~~~~~~~

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


Unit Identity: Latest Imprecise Date
====================================

Attribute name
~~~~~~~~~~~~~~

``::unit:date-range-imprecise:last``

Description
~~~~~~~~~~

The latest date in an imprecise date range for which the claim is valid

Attribute Type
~~~~~~~~~~~~~~

Timestamp

Status
~~~~~~

This attribute is optional

Example of use
~~~~~~~~~~~~~~

``2022-01-22``

Guidance on use
~~~~~~~~~~~~~~~

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


Unit Identity: Research Comments
=======================

Attribute name
~~~~~~~~~~~~~~

``::unit:claim:comment``

Description
~~~~~~~~~~~

Observations specific to the process of reviewing data in this claim, including fixes, refinements and other suggestions.

Atrribute type
~~~~~~~~~~~~~~

String

Example of use
~~~~~~~~~~~~~~

``Parent unit missing``, ``Geography needs attention``, ``Possible duplicate - merge?``

Guidance on use
~~~~~~~~~~~~~~~

Staff Researchers use this attribute to exchange feedback about the data in the claim. This may included changes needed, references to sources that the owner of the claim might look at, and other observations that can improve the quality of the data. Data stored in this attribute are not intended for publication. The comments attribute is common to all claim types in the SFM data model.

Unit Identity: Research Owner
====================

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

Unit Identity: Research Status
=====================

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

- ``X``: Claim should be deleted.
- ``0``: First commit. This claim has just been added and needs review.
- ``1``: Fixes needed. A reviewer has made comments that need to be addressed, which will be recorded in the `Unit Identity: Research Comments`_ attribute.
- ``2``: Fixes made. The owner of this data has addressed the reviewer's comments.
- ``3``: Clean. A final check has been made by a reviewer, and this claim can be used in analysis and can be published.

This type of attribute is common to all claims in the SFM data model.
