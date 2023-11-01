Source
######

Sources are the raw material of Security Force Monitor's research. They are publicly-available, mostly digital, documents and other media that contain information that makes claims about security forces. Specific parts of a source, like page or paragraph numbers, are cited as as a required part of every claim type.

This document provides an overview of what information we store in source records. We discuss the difference how we find sources, and the differences between sources and citations in :ref:`Overview: Sources and citations`.  You can find more about how sources and citations relate to claims and the other entities in our data model in :ref:`What is a claim?`

Source: Summary of attributes
*****************************

The table below summarises the following dimensions of source records:

 - Attribute label: a human readable label for the attribute
 - Attribute name: a unique machine-readable name for the attribute, used during data capture
 - Status: whether the attribute is optional or required in a records
 - Data type: the sort of data that can be entered into the attributes
 - Conformed name: a standardized name that simplifies attribute use in SFM databases


.. csv-table::
   :file: _static/cluster-source-sources.csv
   :header-rows: 1
   :delim: tab


Source: Details of attributes
*****************************

This section contains further information about each attribute, including descriptions, examples of use, and guidance on use.

Source: Unique Identifier
=========================

Attribute name
~~~~~~~~~~~~~~

``::source/id``

Description
~~~~~~~~~~~

A unique 32 character code assigned to each sources in the dataset.

Attribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``1c03ec21-0fae-4243-9de6-686568afc2b8``

Guidance on use
~~~~~~~~~~~~~~~

This value is a Universally Unique Indentifier (UUID) generated using a computer program. 

Source: Type
============

Attribute name
~~~~~~~~~~~~~~

``::source/type``

Description
~~~~~~~~~~~

Description of the media type of the source, such as "document", "video" or "image".

Attribute type
~~~~~~~~~~~~~~

Single string value selected from contolled list

Status
~~~~~~

This attribute is optional

Example of use
~~~~~~~~~~~~~~

``document``, ``video``, ``message``, ``tweet``, ``post``


Guidance on use
~~~~~~~~~~~~~~~

Use this field to capture data about the source's basic media type. The choice of values for this attribute is defined in a controlled vocabulary.

Source: Title
=============

Attribute name
~~~~~~~~~~~~~~

``::source/title``

Description
~~~~~~~~~~~

The name of the source, as stated on the source.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``Stars on their shoulders. Blood on their hands. War crimes committed by the Nigerian military``

Guidance on use
~~~~~~~~~~~~~~~

Copy the exact title of the source as stated on the source itself. Where the title has multiple parts, such as a subtitle, also include that, using a hyphen to signal where there was a linebreak in the original text.

Source: Author
==============

Attribute name
~~~~~~~~~~~~~~

``::source/author``

Description
~~~~~~~~~~~

The name(s) of the human(s) who authored, or otherwise created, the source.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``Osa Okhomina``, ``Tom Moses``, ``Tony Wilson; Tom Longley``

Guidance on use
~~~~~~~~~~~~~~~

Use this field to record the given name and surnames of the humans who authored or otherwise created the source. Typically, this will be a byline containing one or more persons. Where more than one person is credited as the author/creator, use a semi-colon to separate the names.

If the source is a social media post, and the real name of the author/creator cannot be found, record the social media account identity.

Where the author/creator is an organization (e.g. ``Press Association``, ``Reuters and agencies``) do not enter this in `Source: Author`_ - this information will likely be included in the publication entity linked to the source.

Source: Creation Timestamp
==========================

Attribute name
~~~~~~~~~~~~~~

``::source/created-at``

Description
~~~~~~~~~~~

Date and time that the source was first created.

Attribute type
~~~~~~~~~~~~~~

ISO 8601 timestamp, full or partial, UTC timezone (``YYYY-MM-DDThh:mm:ssZ``)

tatus
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``2019-11-29T10:25:45Z``, ``2019``, ``2010-11-29``

Guidance on use
~~~~~~~~~~~~~~~

Where available, record the date and time that the source was first created, which is a common and precise attribute on social media content. The field accepts full or partial values: at its simplest this is to the year, at its most comprehensive it can be to the second. 

A creation timestamp may not be available for a source - if this is the case, leave this field blank and look for a publication or upload timestamp.

Where the timezone is indicated, convert the timestamp to UTC before entering it in this attribute.

Source: Upload Timestamp
========================

Attribute name
~~~~~~~~~~~~~~

``::source/uploaded-at``

Description
~~~~~~~~~~~
Date and time that the source was uploaded to the online platform or service on which it is hosted.

Attribute type
~~~~~~~~~~~~~~

ISO 8601 timestamp, full or partial, UTC timezone (``YYYY-MM-DDThh:mm:ssZ``)

Status
~~~~~~

This field is optional.

Example of use
~~~~~~~~~~~~~~

``2019-11-29T10:25:45Z``, ``2019``, ``2010-11-29``

Guidance on use
~~~~~~~~~~~~~~~

Where available, record the date and time that the source was uploaded to the online platform or service on which it is hosted. This may different from the date of creation or publication. Upload timestamp information may not be available for source - if this is the case, leave the field blank.

The field accepts full or partial values: at its simplest this is to the year, at its most comprehensive it can be to the second.

Where the timezone is indicated, convert the timestamp to UTC.

Source: URL
===========

Attribute name
~~~~~~~~~~~~~~

``::source/url``

Description
~~~~~~~~~~~

The first and original public online location of the source.

Attribute type
~~~~~~~~~~~~~~

String in URL format

Status
~~~~~~

This field is optional.

Example of use
~~~~~~~~~~~~~~

``https://www.amnesty.org/en/documents/afr44/1657/2015/en/``

Guidance on use
~~~~~~~~~~~~~~~

The URL included here must be for the first and original public online location of the source.

Where possible, if a source is republished through a content sharing or syndication system, attempt to find the original online location.

If you are accessing the source through a restricted or subscription-only gateway (such as LexisNexis or ProQuest), find the original public URL for a source rather than the URL generated by the gateway service.

Source: Publication Timestamp
=============================

Attribute name
~~~~~~~~~~~~~~

``::source/published-at``

Description
~~~~~~~~~~~

Date and time that the source was published on the online platform or service on which it is hosted.

Attribute type
~~~~~~~~~~~~~~

ISO 8601 timestamp, full or partial, UTC timezone (``YYYY-MM-DDThh:mm:ssZ``)

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``2019-11-29T10:25:45Z``, ``2019``, ``2010-11-29``

Guidance on use
~~~~~~~~~~~~~~~

Where available, record the date and time that the source was published to the online platform or service on which it is hosted. This may different from the date of creation or upload. 

Although a timestamp for creation and upload dates and times may not be available, it is very likely that at least a publication date will be available for a source. Where a publication date is not available for a source, the timestamp of the earliest complete snapshot of the source found in the Internet Archive should be recorded here.

The field accepts full or partial values: at its simplest this is to the year, at its most comprehensive it can be to the second.

Where the timezone is indicated, convert the timestamp to UTC.

Source: Accessed Timestamp
==========================

Attribute name
~~~~~~~~~~~~~~

``::source/accessed-at``

Description
~~~~~~~~~~~

Full date on which the Staff Reseacher looked at the source.

Attribute type
~~~~~~~~~~~~~~

Date (YYYY-MM-DD)

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``2019-02-20``

Guidance on use
~~~~~~~~~~~~~~~

When a Staff Researcher accesses a source, they should record the full, exact date in this attribute. This data is a useful part of quality assurance processes, enabling us to re-visit sources at set points in time to assess whether they have been updated.

Source: Publication Unique Identifier
=====================================

Attribute name
~~~~~~~~~~~~~~

``::source/publication-id``

Description
~~~~~~~~~~~

The unique 32 character code assigned of the publication that issued the source.

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

This value is a Universally Unique Indentifier (UUID) generated using a computer program. Entries in this attribute correspond to the existing identifiers stored the :ref:`Publication` records.

Source: Acquisition Search Engine
=================================

.. Warning::

   To do!

Attribute name
~~~~~~~~~~~~~~

``::source/acquired-engine``

Description
~~~~~~~~~~~
Attribute type
~~~~~~~~~~~~~~
Status
~~~~~~
Example of use
~~~~~~~~~~~~~~
Guidance on use
~~~~~~~~~~~~~~~

Source: Acquisition Search Term
===============================

.. Warning::

   To do!

Attribute name
~~~~~~~~~~~~~~

``::source/acquired-term``

Description
~~~~~~~~~~~
Attribute type
~~~~~~~~~~~~~~
Status
~~~~~~
Example of use
~~~~~~~~~~~~~~
Guidance on use
~~~~~~~~~~~~~~~

Source: Acquisition Search Timestamp
====================================

.. Warning::

   To do!

Attribute name
~~~~~~~~~~~~~~
``::source/acquired-timestamp``

Description
~~~~~~~~~~~
Attribute type
~~~~~~~~~~~~~~
Status
~~~~~~
Example of use
~~~~~~~~~~~~~~
Guidance on use
~~~~~~~~~~~~~~~

Source: Research Comments
=========================

Attribute name
~~~~~~~~~~~~~~

``::source/comments``

Description
~~~~~~~~~~~

Observations specific to the process of reviewing data in this sources, including fixes, refinements and other suggestions.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``Source need archiving``, ``How to extract full publication timestamp from post?``, ``Source should not be published because permission has not been given by the resource owner``

Guidance on use
~~~~~~~~~~~~~~~

Staff Researchers use this attribute to pass on feedback about the data about the source. This may include the progress made in extracting information from the source, references to sources that the researcher might look at, and other observations that can improve the quality of the data. Data in this attribute are not intended for publication.

Source: Restricted
==================

.. warning::

   This attribute will be replaced by a more comprehensive approach to access control and data access.

Attribute name
~~~~~~~~~~~~~~

``::source/restricted``

Description
~~~~~~~~~~~

Field indicating that the source should not be published on WhoWasInCommand, or distributed in any public product.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``1``

Guidance on use
~~~~~~~~~~~~~~~

If a source should not be published on WhoWasInCommand, or distributed in any public form, the Staff Analyst can indicate this by placing a ``1`` in the `Source: Restricted`_ field. The reasons for restricted publication of a source should be recorded in `Source: Research Comments`_.