Source
######

Sources are the raw material of Security Force Monitor's research. They are publicly available, mostly digital, documents and other media that contain information that makes claims about security forces. Specific parts of a source, like page or paragraph numbers, are cited as a required part of every claim type.

This document provides an overview of what information we store in source records. We discuss the difference in how we find sources, and the differences between sources, citations and publications in :ref:`Overview: Sources, Citations and Publications`.  You can find more about how sources and citations relate to claims and the other entities in our data model in :ref:`What is a claim?`

Source: Summary of attributes
*****************************

The table below summarizes the following dimensions of source records:

 - Attribute label: a human readable label for the attribute
 - Status: whether the attribute is optional or required in a record
 - Data type: the sort of data that can be entered into the attribute
 - Key name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-source-sources.csv
   :header-rows: 1
   :delim: tab


Source: Details of attributes
*****************************

This section contains further information about each attribute, including descriptions, examples of use, and guidance on use.

source:type
===========

Description
~~~~~~~~~~~

Description of the media type of the source, such as "document", "video" or "image".

Attribute type
~~~~~~~~~~~~~~

Single string value selected from contolled list.

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:source/type``

Example of use
~~~~~~~~~~~~~~

``audio``, ``dataset``, ``document``, ``image``, ``map``, ``post``, ``video``

Guidance on use
~~~~~~~~~~~~~~~

Use this field to capture data about the source's basic media type. The choice of values for this attribute is defined in a controlled vocabulary.


source:source_id:admin
======================

Description
~~~~~~~~~~~

Field unique 32 character code assigned to the source.

Attribute type
~~~~~~~~~~~~~~

String in UUID format.

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:entity/id``

Example of use
~~~~~~~~~~~~~~

``eaa8d097-fa15-4fe4-8860-936acb4f73f9``

Guidance on use
~~~~~~~~~~~~~~~

This field is for the Universally Unique Identifier (UUID) assigned to the source. Each source can only have a single UUID.


source:title
============

Description
~~~~~~~~~~~

The name of the source, as stated on the source.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:source/title``

Example of use
~~~~~~~~~~~~~~

``Stars on their shoulders. Blood on their hands. War crimes committed by the Nigerian military``

Guidance on use
~~~~~~~~~~~~~~~

Copy the exact title of the source as stated on the source itself. Where the title has multiple parts, such as a subtitle, also include that, using a hyphen to signal where there was a linebreak in the original text.


source:author
=============

Description
~~~~~~~~~~~

The name(s) of the human(s) who authored, or otherwise created, the source (if provided).

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:source/author``

Example of use
~~~~~~~~~~~~~~

``David Hook, Tin Maung Than and Kim N. B. Ninh``, ``AZ AIB``, ``Maung Aung Myoe``, ``Andrew Selth``

Guidance on use
~~~~~~~~~~~~~~~

Use this field to record the given name and surnames of the humans who authored or otherwise created the source. Typically, this will be a byline containing one or more persons. Where more than one person is credited as the author/creator, use a comma to separate the names.


source:url
==========

Description
~~~~~~~~~~~

The original public online location of the source.

Attribute type
~~~~~~~~~~~~~~

String in URL format

Status
~~~~~~

This field is optional.

Key name
~~~~~~~~

``:source/url``

Example of use
~~~~~~~~~~~~~~

``https://www.amnesty.org/en/documents/afr44/1657/2015/en/``

Guidance on use
~~~~~~~~~~~~~~~

The URL included here should be for the original public online location of the source. If a source is republished through a content sharing or syndication system, attempt to find the original online location.


source:created_timestamp
========================

Description
~~~~~~~~~~~

Date and time that the source was first created.

Attribute type
~~~~~~~~~~~~~~

ISO 8601 timestamp, full or partial, UTC timezone (``YYYY-MM-DDThh:mm:ssZ``)

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:source/created-at``

Example of use
~~~~~~~~~~~~~~

``2019-11-29T10:25:45Z``, ``2010-11-29``

Guidance on use
~~~~~~~~~~~~~~~

Where available, record the date and time that the source was first created, which is a common and precise attribute on web and social media content. A creation timestamp may not be available for a source - if this is the case, leave this field blank and look for a publication or upload timestamp.

Where the timezone is indicated, convert the timestamp to UTC before entering it in this attribute.


source:uploaded_timestamp
=========================

Description
~~~~~~~~~~~
Date and time that the source was uploaded to the online platform or service on which it is hosted.

Attribute type
~~~~~~~~~~~~~~

ISO 8601 timestamp, full or partial, UTC timezone (``YYYY-MM-DDThh:mm:ssZ``)

Status
~~~~~~

This field is optional.

Key name
~~~~~~~~

``:source/uploaded-at``

Example of use
~~~~~~~~~~~~~~

``2019-11-29T10:25:45Z``, ``2019``, ``2010-11-29``

Guidance on use
~~~~~~~~~~~~~~~

Where available, record the date and time that the source was uploaded to the online platform or service on which it is hosted. This may different from the date of creation or publication. Upload timestamp information may not be available for source - if this is the case, leave the field blank.

If a publication date is not available for a source, the timestamp of the snapshot of the source found in the Internet Archive should be used in this field (and the ``source:published_timestamp`` would be left blank).

Where the timezone is indicated, convert the timestamp to UTC.


source:published_timestamp
==========================

Description
~~~~~~~~~~~

Date and time that the source was published.

Attribute type
~~~~~~~~~~~~~~

ISO 8601 timestamp, full or partial, UTC timezone (``YYYY-MM-DDThh:mm:ssZ``)

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:source/published-at``

Example of use
~~~~~~~~~~~~~~

``2019-11-29T10:25:45Z``, ``2019``, ``2010-11-29``

Guidance on use
~~~~~~~~~~~~~~~

Where available, record the date and time that the source was published. This may different from the date of creation or upload. 

Although a timestamp for creation and upload dates and times may not be available, it is very likely that at least a publication date will be available for a source. If a publication date is not available for a source, the timestamp of the snapshot of the source found in the Internet Archive should be used in the ``source:uploaded_timestamp`` and this field should be left blank.

Where the timezone is indicated, convert the timestamp to UTC.


source:publication_id:admin
===========================

Description
~~~~~~~~~~~

The unique 32 character code assigned of the publication that issued the source.

Attribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:source/publication:ref``

Example of use
~~~~~~~~~~~~~~

``3e1aded8-4629-4837-a1b3-78d29ad4abf1``

Guidance on use
~~~~~~~~~~~~~~~

This field is for the Universally Unique Identifier (UUID) assigned to the ``publication`` which published the source. This could be an organization like The New York Times, or an account id on a social media site. Each publication can only have a single UUID.
