Person Identity
###############

"Person Identity" is a claim type describing basic identifying information about a person, such as their name and aliases. Claims of this type are grouped together with :ref:`Person Posting` (describing ranks and positiongs in different units) and a draft claim type called :ref:`Person Extra Data` (extended biographical information) claims, which creates a fuller dataset on the person's career in the security and defence forces

Person Identity: Summary of claim attributes 
*****************************************

The table below summarises the following dimensions of Person Identity claims:

 - Attribute label: a human readable label for the attribute
 - Attribute name: a unique machine-readable name for the attribute, used during data capture
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the field
 - Conformed name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-person-fields.csv
   :header-rows: 1
   :delim: tab


Person Identity: Details of claim attributes
********************************************

This section contains further information about each attribute, including descriptions, examples of use, and Guidance on use.


Person Identity: Unique Identifier
==================================

Attribute name
~~~~~~~~~~~~~~

``::person:id``

Description
~~~~~~~~~~~

A unique 32 character code assigned to each person in the dataset.

Attribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``a848de4e-ebeb-49d6-9099-7e68ca3b57fc``

Guidance on use
~~~~~~~~~~~~~~~

This value is a Universally Unique Indentifier (UUID) generated using a computer program. UUIDs can be created easily using either installable or online tools, for example:

- Linux and OSX users: `uuidgen` command line tool.
- On the web: `UUID Generator <https://www.uuidgenerator.net/version>`_.

The attribute is administrative, providing a reliable way to differentiate between different persons. 

The Staff Researcher must generate a unique identifying number for that person and add it to every claim associated with that specific person. This manual, copy-and-paste step is a potential source of error and the Staff Researcher must be careful not to re-use a UUID. As the data are ingested into database systems, claims that share the same UUID in ``::unit:id`` will be aggregated to create a single record for that person.


Person Identity: Claim Citation Identifier
==========================================

Attribute name
~~~~~~~~~~~~~~

``::person:claim:citation:id``

Description
~~~~~~~~~~~

A unique 32 character code of a citation from a source that evidences the other attribute(s) in this claim.

Attribute type
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

Person Identity: Name
=====================

Attribute name
~~~~~~~~~~~~~~

``::person:name``

Description
~~~~~~~~~~~

Full name of the person, including given, patronym and surnames.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``Magaji Musa Majia'a``

Guidance on use
~~~~~~~~~~~~~~~

Different sources will spell the name of a person in different ways, so we choose a name to be a canonical entry for that person. Whenever possible, the canonical entry will contain the most complicated or complete version of a person's name, even if it has the smallest number of citations. For example ``Magaji Musa Majia'a`` will be used instead of ``Magaji Majiaa``. Other names will be placed in the `Person Identity: Other Names`_ attribute. Titles, roles, honorifics and other attributes that are more correctly linked to a person's posting in a unit are recorded in `Person Posting`_ claims.

Person Identity: Other Names
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

Different sources will spell a person's name in different ways. We choose and record a canonical version of a person's name in the `Person Identity: Name` field. All other spellings that we have found are treated as aliases and stored in this field. Titles, roles, honorifics and other attributes that are more correctly linked to a person's posting in a unit are recorded in `Person Posting`_ claims.

Person Identity: Country
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

Values for this field are chosen from the list of ISO 3166-1 alpha-2 codes, which can be found (`on the ISO website <https://www.iso.org/obp/ui/#search/code/>`__ and on `Wikipedia <https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Officially_assigned_code_elements>`__. This field does not denote the citizenship or country of origin of a person. Rather, it denotes where a unit they are a member of is located. For example, if ``1 Batallón de Infantería`` is located in Juarez, Mexico, the unit will be assigned a value of ``mx`` in the field `Unit Identity: Country`_. Any person who is a member of that unit will be assigned a value of ``mx`` in the field `Person Identity: Country`_ as well. A person may have multiple entries for `Person Identity: Country`_ where our research shows they or a unit they are a member of is deployed to different countries.

Person Identity: Earliest Precise Date
======================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Person Identity: Latest Precise Date
====================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Person Identity: Earliest Imprecise Date
========================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Person Identity: Latest Imprecise Date
======================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Person Identity: Date range is a Start Date
===========================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Person Identity: Date range is an End Date
==========================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Person Identity: Research Comments
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

Person Identity: Research Owner
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

Person Identity: Research Status
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