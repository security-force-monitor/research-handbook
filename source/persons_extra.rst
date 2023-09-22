Person Extra Data
#################

.. warning::
    This is a draft claim type not yet formally implemented in the SFM data model. Date attributes will be changed to match SFM's updated approaches. Attributes that contain URLs may be revised to become citations.

The "Persons Extra" claim type describes a person's extended biographical information, including  social media and other online accounts, official webpages, and media materials containing information about how the person looks and sounds. 

It also serves the purpose of grouping resources that are *ipso facto* - resources that are valuable in themselves, and not only as sources for other data points. This provides the Staff Analyst with a collection of audiovisual media resources that can be used to identify and further research the person.

This is a draft claim type not yet formally implemented in the SFM data model.

Person Extra Data: Summary of claim attributes 
**********************************************


The table below summarises the following dimensions of Unit Identity claims:

 - Attribute label: a human readable label for the attribute
 - Attribute name: a unique machine-readable name for the attribute, used during data capture
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the attribute
 - Conformed name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-personsextra-attributes.csv
   :header-rows: 1
   :delim: tab

Person Extra Data: Details of claim attributes
**********************************************

This section contains further information about each attribute, including descriptions, examples of use, and Guidance on use.

Person Extra Data: Unique Identifier
==================================

Attribute name
~~~~~~~~~~~~~~

``::extra:id``

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


Person Extra Data: Claim Citation Identifier
==========================================

Attribute name
~~~~~~~~~~~~~~

``::extra:claim:citation:id``

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


Person Extra Data: Person Unique Identifier
===========================================

Attribute name
~~~~~~~~~~~~~~~

``::extra:person:id``

Description
~~~~~~~~~~~

A unique 32 character code assigned to each person in the dataset.

Attribute type
~~~~~~~~~~~~~~

String in UUID format, selected from existing person records.

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``a848de4e-ebeb-49d6-9099-7e68ca3b57fc``

Guidance on use
~~~~~~~~~~~~~~~

This attribute is used to store the UUID of the person about whom extra information is being entered. The person must already have an entry in the dataset.

Person Extra Data: Person Gender
================================

Attribute Name
~~~~~~~~~~~~~~

``::extra:gender``


Description
~~~~~~~~~~~

Indicators of a person's sex or gender identity, as inferred from pronouns used in the text of available sources.

Attribute type
~~~~~~~~~~~~~~

Open list, single choice

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``Male``, ``Female``, ``Other``

Guidance on use
~~~~~~~~~~~~~~~

This attribute is used to capture data about the gender of a person, as determined only by the pronouns ("her", "she", "his", "him", etc) used in any available textual sources about this person. We do not infer a person's gender from their name or images of them. 

Echoing the definition used in the `FOAF standard<http://xmlns.com/foaf/spec/#term_gender>`__, the `Person Extra Data: Gender`_ attribute is not intended to capture the full range of possible biological, social and sexual associated with the word "gender". In the majority of cases the value recorded in this attribute will be ``male`` or ``female``. However, we have left this attribute open to include alternatives that are expressed within the available sources about a person.

Where the sources contain no textual indication about the person's gender, the attribute should be left blank.

Person Extra Data: Date of Birth
================================

Attribute name
~~~~~~~~~~~~~~

``::extra:date_of_birth``

Description
~~~~~~~~~~~

The date on which a person was born.

Attribute type
~~~~~~~~~~~~~~

Date (YYYY-MM-DD), fuzzy

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``1985-10-01``, ``1985-10``, ``1985``

Guidance on use
~~~~~~~~~~~~~~~

This attribute is used to capture the date of birth of a person, with as much specificity as allowed by available sources. The attribute can accept a full or partial date.

.. note::
   This attribute will be updated with new rules on im/precision.

Person Extra Data: Deceased?
============================

Attribute name
~~~~~~~~~~~~~~

``::extra:is_dead``

Description
~~~~~~~~~~~

Indicates whether a person has died.

Attribute type
~~~~~~~~~~~~~~

Positive confirmation, blank if none.

Status
~~~~~~

This attribute is optional

Example of use
~~~~~~~~~~~~~~

``Y``

Guidance on use
~~~~~~~~~~~~~~~

Where sources indicate that a person has died, enter ``Y`` in this attribute. In all other cases, leave the attribute blank.

In many cases the sources used to evidence this attribute and `Person Extra Data: Date of Death`_ will be the same. In some cases, however, sources may indicate a person has died without specifying a date. In these cases, the attribute `Person Extra Data: Date of Death`_ should not be filled in. 

Person Extra Data: Date of Death
================================

Attribute name
~~~~~~~~~~~~~~

``::extra:date_of_death``

Description
~~~~~~~~~~~

A date on which a person died.

Attribute type
~~~~~~~~~~~~~~

Date (YYYY-MM-DD), fuzzy

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``2017-07-22``, ``2017-07``, ``2017``

Guidance on use
~~~~~~~~~~~~~~~

Use this attribute to record the full or partial date of a person's death, as recorded in a source. Where a source reports that a person has died, but does not indicate the date on which this happened, only the attribute `Person Extra Data: Deceased?`_ should be filled in.

.. note::
   This attribute will be updated with new rules on im/precision.

Person Extra Data: Account Type
===============================

Attribute name
~~~~~~~~~~~~~~

``::extra:account_type``

Description
~~~~~~~~~~~

The name of an online platform or service on which the person holds an account.

Attribute type
~~~~~~~~~~~~~~

Text and numbers, chosen from list.

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``facebook``, ``twitter``, ``telegram``, ``whatsapp``, ``youtube``, ``vkontakte``, ``wikipedia``

Guidance on use
~~~~~~~~~~~~~~~

This attribute is used to record the name of the online platform of service on which a person holds an account. The name is chosen from a list of available platforms and services, which will be updated as required. The subsequent attribute `Person Extra Data: Account Identity`_ is used to record the name of the account held by the person on the platform or service.

Where a person has more than one account, on the same or different platforms, a new claim should be created.

Person Extra Data: Account Identifier
=====================================

Attribute name
~~~~~~~~~~~~~~

``::extra:account_identifier``

Description
~~~~~~~~~~~

The account name used by the person on a specific online platform or service.

Attribute type
~~~~~~~~~~~~~~

String, formatted as a URL

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``tomcopsymes`` (on Twitter)

Guidance on use
~~~~~~~~~~~~~~~

This attribute is used to record the account name held by the person on a specific online platform or service. The name of the corresponding online platform or service is stored in `Person Extra Data: Account Type`_.

Where a person has more than one account, on the same or different platforms, a new claim should be created.

Person Extra Data: External Link Description
============================================

Attribute name
~~~~~~~~~~~~~~

``::extra:external_link_description``

Description
~~~~~~~~~~~

Short textual description of the relevent content of a URL containing information about the person.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``Official biography of General Luis Cresencio Sandoval Gonzálezi on the SEDENA website``, ``Wikipedia page for Luis Cresencio Sandoval``, 

Guidance on use
~~~~~~~~~~~~~~~

This attribute is used to store a short decription of the content found at an external URL about this person. The details of the external link are stored in the relevant source record. This attribute is used to gather together resources that provide a high level of detail about the person, and will include official websites, blogs operated by the person, the Wikipedia page about them (if they have one), or Facebook pages credibly linked to the person. Details about the social media footprint of the person are not stored in this attribute - ``Person Extra: Account Type`` and ``Person Extra: Account Identity`` are used toe capture this data.

The source attribute associated with ``Person Extra: External Link Description`` is used to store data about the resource itself, along with other material that evidences why the external link is about the person.

A new row is created for each new resource.

Person Extra Data: Media Description
====================================

Attribute name
~~~~~~~~~~~~~~

``::extra:media_description``

Description
~~~~~~~~~~~

Short textual description of material found in a media resource that provides information about a how person looks or sounds.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional

Example of use
~~~~~~~~~~~~~~

"Face and shoulders of Bosco Ntaganda, in military uniform with hat, tie and lapels, backed by two other men in combat fatigues armed with rifles. Taken at a news conference in January 2009."

Guidance on use
~~~~~~~~~~~~~~~

This attribute is used to store a brief description of the content of external. The description should be sufficient for the analyst to quickly appraise what they can expect to find in the media about what the person looks or sounds like. Details about the media type, URL and other metadata are contained in the source associated with `Person Extra Data: Media Description`_.

A new row is created for each distinct media item about the person.

Person Extra Data: Notes
========================

Attribute name
~~~~~~~~~~~~~~

``::extra:notes``

Description
~~~~~~~~~~~

Analysis, commentary and notes about the material in row of data in Persons Extra that do not fit into the data structure.

Attribute type
~~~~~~~~~~~~~~

String

Example of use
~~~~~~~~~~~~~~

"The image referenced in this row is clipped from a longer video. Should it be necessary, additional views of this individual are available in the video."

Guidance on use
~~~~~~~~~~~~~~~

We use this attribute to record information about the material recorded in Persons Extra Data that is likely to provide useful context, additional information that does not fit into the data structure, and notes about how decisions were made about which data to include. Any sources used to write the notes should be included directly inside this attribute.

Person Extra Data: Research Comments
====================================

Attribute name
~~~~~~~~~~~~~~

``::extra:claim:comments``

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

Person Extra Data: Research Owner
=================================

Attribute name
~~~~~~~~~~~~~~

``::extra:claim:reseacher``

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

Person Extra Data: Research Status
================================

Attribute name
~~~~~~~~~~~~~~

``:extra:claim:status``

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