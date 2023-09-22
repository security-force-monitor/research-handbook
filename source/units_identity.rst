Unit Identity
#############

"Unit Identity" is a claim type that contains information about the existence and identity of the unit, such as its name, aliases, branch (or classification), the country in which is operates, and the duration of its existence. "Unit Identity" claims are grouped (or aggregated) together to create building blocks of the command chain of a branch of the security or defense forces. They are connected together with "Unit Relation" claims, resulting in a hierarchy of units.

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

Unit: Unique Identifier
=======================

Attribute name
~~~~~~~~~~~~~~

``::unit:id``

Description
~~~~~~~~~~~

A unique 32 character code assigned to each unit in the dataset. 

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

This value is a Universally Unique Indentifier (UUID) generated using a computer program. UUIDs must be created easily using either installable or online tools, for example:

- Linux and OSX users: `uuidgen` command line tool.
- On the web: `UUID Generator <https://www.uuidgenerator.net/version>`_.

The field is administrative, providing a reliable way to differentiate between different entities in the SFM data model, in this case the unit entity.

The Staff Researcher must generate a unique identifying number for that unit and copy it into the attribute ``::unit:id`` for every claim associated with that specific unit. As the data are ingested into database systems, claims that share the same UUID in ``::unit:id`` will be aggregated to create a single record for that unit.

During research, particularly when using a spreadsheet, this is a manual, copy-and-paste step and is a potential source of error. The Staff Researcher must be careful never to re-use a UUID anywhere in this or other parts of the dataset.

Unit: Claim Citation Identifier
===============================

Attribute name
~~~~~~~~~~~~~~

``::unit:claim:citation:id``

Description
~~~~~~~~~~~

A unique 32 character code of a citation from a source that evidences the other attribute(s) in this claim.

Atrribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``16d013b5-7073-4446-b22b-46b0edb25632``

Guidance on use
~~~~~~~~~~~~~~~

All claims require a citation, which is a reference to a specific part of a source (for example a page or paragraph reference). The page on citations provides more information about this evidentiary mechanism.

Unit: Name
==========

Attribute name
~~~~~~~~~~~~~~

``::unit:name``

Description
~~~~~~~~~~~

Canonical name of the unit.

Atrribute type
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

    Example: ``Police Divisions`` are a class of police units in Nigeria. There are over 1000 units of this type nationwide. However, each individual ``Police Division`` may not have a citation for their formal name such as ``Lagos Police Division``, but only have a citation (or numerous citations) for the less formal ``Lagos Division``. The Monitor would list the name of the unit as ``Lagos Police Division`` and the claim would include a comment about the methodology behind that choice. The less formal ``Lagos Division`` name would be entered in the `Unit: Other Names`_ field.

    Example: Army units of a country may follow a naming convention of a number and then name of unit: e.g. ``3 Battalion`` or ``25 Brigade``. There may be a unit of which we only have citations for a variation on that: e.g. ``Fourth Battalion``. In this case, the Monitor would list the name of the unit as ``4 Battalion`` with a note about the methodology behind that choice. The ``Fourth Battalion`` name variant would be entered in a claim about `Unit: Other Names`_.

Standardizations don't have specific sources, so we have created a specific source to use in these cases. Where a value in `Unit: Name`_ has been standardized, a citation with the following title will be associated with it: "Name standardized in accordance with Security Force Monitor research".

Additionally, wherever possible, we will choose the most complete and complex version of a unit’s name that can be evidenced by a source:

    Example: ``3 Armoured Division`` would be the entry, rather than the more informal ``3 Division`` (which may have more citations).

The Monitor does not use ordinal indicators like ``1st`` or ``3rd`` in the name of an Unit. Instead these will be listed in the `Unit: Other Names`_ field.

The Monitor uses the name in the official (local) language of the country where appropriate and/or possible.

    Example: A unit in the Mexican Army would be called by its name in Spanish (``10 Regimiento de Caballería Motorizado``), rather than the English translation ( ``10 Motorized Cavalry Regiment``).

In an effort to standardize names across all countries, the Monitor generally uses Arabic numerals in the `Unit: Name`_ field. Where warranted by sources the Monitor will use Roman numerals like ``V`` or ``XI`` instead of ``5`` or ``11`` respectively.

In cases where multiple units have the same name the Monitor will distinguish them by adding unique identifying text based on the unit's location or parent unit.

    Example: There are multiple "Central Police Station" formations across Nigeria, some based in the same state. To better distinguish these are separate, distinct units the Monitor added information on where the units were located to the name field for instance ``Central Police Station (Awka, Anambra State).``\ In Myanmar there have been different units through time both the name Central Regional Military Command. To distinguish them the Monitor added information on when the unit came into existence to the name: ``Central Regional Military Command (post 199)``.

Unit: Other Names
=================

Attribute name
~~~~~~~~~~~~~~

``::unit:other_names``

Description
~~~~~~~~~~~

Other names for a unit, including aliases, alternative spellings and abbreviations.

Atrribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

If ``3 Armoured Division`` is used as the canonical `Unit: Name`_ of a unit, entries in the `Unit: Other Names`_ field may include ``3 Div`` and ``Three Division``.


Guidance on use
~~~~~~~~~~~~~~~

Different sources will spell a unit's name in different ways. We choose and record a canonical version of a unit's name in the `Unit: Name`_ field. All other spellings that we have found are treated as aliases and stored in this field.

Although we do not use ordinal indicators like ``2nd`` or ``10/o`` in the canonical name we choose for a unit, where a source uses an ordinal we record it as an alias.

    Example: We find a version of the unit name ``3 Armoured Division`` that has an Ordinal indicator: ``10/o. Regimiento de Caballería Motorizado.`` We would record this in the `Unit: Other Names`_ field.

Unit: Classification
====================

Attribute name
~~~~~~~~~~~~~~

``::unit:classifications``

Description
~~~~~~~~~~~

The branch or branches of the security services that the unit a part of or a general descriptor for the unit.

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

We use classifications to describe the basic nature of a specific unit and to assist investigations of potential linkages between reports of human rights abuses and the Security Force Monitor's dataset. As alleged perpetrators are usually identified in general terms of "soldiers" and "police" this field is important as a first step to understand potential linkages between units, persons and incidents. `Unit: Classification` values are useful supplements to those in the `Unit Relations`_ claim type in connecting different units together.

The `Unit: Classification`_ field will contain a mix of standard terms and country-specific terms used to describe security force branches. In choosing terms to include in the `Unit: Classification`_ field we try to include terms that are used by country experts as well as those that are common terms. We also try to be economical and create as few, distinct terms as possible.

    Example: a standard term we would apply to army units is ``Army``. The equivalent in Mexico would be ``Ejécito``. We would capture both terms in the `Unit: Classification``_ field.

Units may have more than one classification. Usually this will be when a unit can have both "generic" and "specific" classifications.

    Example: Units which are part of the army of a country may be coded as having a classification of ``Army`` as well as a classification of ``Military``, whereas units which are part of the navy of a country would have classifications of of ``Navy`` and ``Military``. For both the army and navy unit their respective classifications are correct, the army and the navy are part of the military. Critically, this enables the Monitor or users of the Monitor's data to properly analyze allegations against "soldiers" and "members of the army" in the country. In the case of "soldiers" this analysis should include every unit with the classification of ``Military`` while if there is greater specificity of "members of the army" would mean excluding any unit with the classification of ``Navy`` and focusing only on those units with a classification of ``Army.``

Unit: Country
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

The `Unit: Country` attribute identifies the country fromt which this unit originates. All entries in this attribute will be two-letter country codes taken from `ISO 3166 <https://www.iso.org/obp/ui/#search>`__.

    For example, a unit from Nigeria would have the code ``ng`` and a unit from Brazil would have the code ``br``

A unit may only contain a single value in the `Unit: Country`_ attribute. A unit's operations in another country are described using the `Unit: Positioning`_ claim type.


Unit: Date Range is a Start Date
================================

.. note::
   To Do.

Unit: Date Range is an Ending Date
==================================

.. note::
   To Do.

Unit: Earliest Precise Date
===========================

.. note::
   To Do.

Unit: Latest Precise Date
=========================

.. note::
   To Do.

Unit: Earliest Imprecise Date
=============================

.. note::
   To Do.

Unit: Latest Imprecise Date
===========================

.. note::
   To Do.

Unit: Research Comments
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

Unit: Research Owner
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

Unit: Research Status
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
