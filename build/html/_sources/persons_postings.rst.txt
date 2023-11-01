Person Posting
##############

The "Person Posting" claim type holds information about a person's career in the security forces. It first defines a relationships between a person and a unit, and can be used to further describe the role the person has in the unit ("command", "administrative", etc), the rank they hold at the time of the posting, and any additional titles they may hold at the time of a posting. A person usually has a single posting at any one time, but may have multiple overlapping postings. 

Person Postings: Summary of claim attributes 
********************************************

The table below summarises the following dimensions of Unit Posting claims:

 - Attribute label: a human readable label for the attribute
 - Attribute name: a unique machine-readable name for the attribute, used during data capture
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the field
 - Conformed name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-postings-fields.csv
   :header-rows: 1
   :delim: tab

Person Postings: Details of claim attributes
********************************************

This section contains further information about each attribute, including descriptions, examples of use, and Guidance on use.

Person Posting: Unique Identifier
=================================

Attribute name
~~~~~~~~~~~~~~

``::posting:id``

Description
~~~~~~~~~~~

A unique 32 character code assigned to each posting in the dataset.

Attribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``a848de4e-ebeb-49d6-9099-7e68ca3b57fc``

Guidance on use
~~~~~~~~~~~~~~~

This value is a Universally Unique Indentifier (UUID) generated using a computer program. UUIDs can be created easily using either installable or online tools, for example:

- Linux and OSX users: `uuidgen` command line tool.
- On the web: `UUID Generator <https://www.uuidgenerator.net/version>`_.

The attribute is administrative, providing a reliable way to differentiate between different persons. 

The Staff Researcher must generate a unique identifying number for that posting and add it to every claim associated with that specific person. This manual, copy-and-paste step is a potential source of error and the Staff Researcher must be careful not to re-use a UUID. As the data are ingested into database systems, claims that share the same UUID in ``::posting:id`` will be aggregated to create a single record for that posting.

Person Posting: Claim Citation Identifier
=========================================

Attribute name
~~~~~~~~~~~~~~

``::posting:claim:citation:id``

Description
~~~~~~~~~~~

A unique 32 character code of a citation from a source that evidences the other attribute(s) in this claim.

Attribute type
~~~~~~~~~~~~~

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

Person Posting: Unit Unique Identifier
======================================

ttribute name
~~~~~~~~~~~~~~

``::posting:unit:id``

Description
~~~~~~~~~~~

The unique 32 character code assigned to a unit to which the person is posted.

Attribute type
~~~~~~~~~~~~~~

String in UUID format, selected from existing unit records

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``a848de4e-ebeb-49d6-9099-7e68ca3b57fc``

Guidance on use
~~~~~~~~~~~~~~~

This is the Universally Unique Indentifier (UUID) of the unit who is being posted to a unit. A record for the unit must already exist in the dataset. 

Guidance on use
~~~~~~~~~~~~~~~

Person Posting: Person Unique Identifier
========================================

Attribute name
~~~~~~~~~~~~~~

``::posting:person:id``

Description
~~~~~~~~~~~

The unique 32 character code assigned to a person posted to a unit.

Attribute type
~~~~~~~~~~~~~~

String in UUID format, selected from existing person records

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``a848de4e-ebeb-49d6-9099-7e68ca3b57fc``

Guidance on use
~~~~~~~~~~~~~~~

This is the Universally Unique Indentifier (UUID) of the person who is being posted to a unit. A record for the person must already exist in the dataset. 

Person Posting: Role
====================

Atttribute name
~~~~~~~~~~~~~~~

``::posting:role``

Description
~~~~~~~~~~~

The role a person plays in the unit, which is not immediate apparent their rank or title.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``Commander``

Guidance on use
~~~~~~~~~~~~~~~

The most common value we record in this attribute is ``Commander``.

There are a variety of other roles a person can have including ``Second in Command``, ``Chief of Staff`` along with other less common entries. They will vary between countries.

In nearly all cases, the value placed in this attribute is taken verbatim from the source. As a special note, heads of academic or other security force institutions will sometimes be referred to as the ``Commandant``. In these cases, ``Commandant`` should be recorded in the `Person Posting: Title`_ attribute , and their role should be recorded here as ``Commander``.

If a person is referred to as “the head”, “chief” or some other variation indicating that they are in charge of a unit, they should be regarded as the ``Commander`` for the purposes of entering a value in this attribute.

Person Posting: Title
=====================

Atttribute name
~~~~~~~~~~~~~~~

``::posting:title``

Description
~~~~~~~~~~~

A title held by a person that is separate from their rank or role.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``General Officer Commanding``, ``Jefe Del Estado Mayor``, ``Vice Chairman``

Guidance on use
~~~~~~~~~~~~~~~

The range of titles will vary from country to country. For example, commanders of army divisions in Nigeria, who usually hold the rank of ``Major General`` also hold the title of ``General Officer Commanding``. The value placed in this attribute is taken verbatim from the source and not edited or standardized.

Person Posting: Rank
====================

Atttribute name
~~~~~~~~~~~~~~~

``::posting:rank``

Description
~~~~~~~~~~~

The official position of a person in the hierarchy of a security force.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``General de División``, ``Teniente Coronel``, ``Air Vice Marshal``, ``Lieutenant Colonel``

Guidance on use
~~~~~~~~~~~~~~~

In most cases, the value placed in this attribute is taken verbatim from the source and not edited or standardized. In some cases, we remove any dashes from the entry.

    For example, we would enter ``Brigadier General`` rather than ``Brigadier-General``.

Person Posting: Earliest Precise Date
=====================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Person Posting: Latest Precise Date
===================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Person Posting: Earliest Imprecise Date
=======================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Person Posting: Latest Imprecise Date
=====================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Person Posting: Date range is a Start Date
==========================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Person Posting: Date range is an End Date
=========================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.

Person Posting: Research Comments
==================================

Attribute name
~~~~~~~~~~~~~~

``::posting:claim:comments``

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

Person Posting: Research Owner
==============================

Attribute name
~~~~~~~~~~~~~~

``::posting:claim:reseacher``

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

``TL``, ``TW``, ``MM``, ``NP``

Guidance on use
~~~~~~~~~~~~~~~

This attribute allows researchers keep track of claims they have created. It  may be used for arbitrary grouping and tagging of specific sets of claims if needed. This type of attribute is common to all types of claim in the SFM data model.

Person Posting: Research Status
================================

Attribute name
~~~~~~~~~~~~~~

``:posting:claim:status``

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
- ``0``: First commit. This ciaim has just been added and needs review.
- ``1``: Fixes needed. A reviewer has made comments that need to be addressed, which will be recorded in the `Person Posting: Research Comments`_ attribute.
- ``2``: Fixes made. The owner of this data has addressed the reviewer's comments.
- ``3``: Clean. A final check has been made by a reviewer, and this claim can be used in analysis and can be published.

This type of attribute is common to all claims in the SFM data model.