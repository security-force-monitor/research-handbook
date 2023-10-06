Citation
########

A citation directs us to a particular part of a source as evidence for a information a claim - it's much like a citation in an academic paper. This could be material from a specific page in the source; it could also be a specific archive snapshot of a page, as the content of a webpage can sometimes change over time even though its basic identifying data will not. A single source can be cited in multiple ways, and - once created - a citation can be re-used to evidence any number of claims. 

Citation: Summary of attributes
********************************

The table below summarises the following dimensions of citations records:

 - Attribute label: a human readable label for the attribute
 - Attribute name: a unique machine-readable name for the attribute, used during data capture
 - Status: whether the attribute is optional or required in the record
 - Data type: the sort of data that can be entered into the attribute
 - Conformed name: a standardized name that simplifies attribute use in SFM databases


.. csv-table::
   :file: _static/cluster-source-citations.csv
   :header-rows: 1
   :delim: tab


Citation: Details of attributes
********************************

This section contains further information about each attribute, including descriptions, examples of use, and guidance on use.


Citation: Unique Identifier
===========================

Attribute name
~~~~~~~~~~~~~~

``::citation/id``

Description
~~~~~~~~~~~

A unique 32 character code assigned to each citation.

Attribute type
~~~~~~~~~~~~~~

String in UUID format.

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``1c03ec21-0fae-4243-9de6-686568afc2b8``

Guidance on use
~~~~~~~~~~~~~~~

This value is a Universally Unique Indentifier (UUID) generated using a computer program. Attributes such as :ref:`Unit Identity: Claim Citation Identifier` draw from the values stored in this attribute. 


Citation: Source Unique Identifier
==================================

Attribute name
~~~~~~~~~~~~~~

``::citation/source:id``

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

This value is a Universally Unique Indentifier (UUID) generated using a computer program. Values in this field correspond to those used in the attribute :ref:`Source: Unique Identifier`.


Citation: Researcher Comments
=============================

Attribute name
~~~~~~~~~~~~~~

``::citation/comments``

Description
~~~~~~~~~~~

Observations specific to the process of reviewing data in this citation, including fixes, refinements and other suggestions.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``Citation page range is not accurate ``

Guidance on use
~~~~~~~~~~~~~~~

Staff Researchers use this attribute to pass on feedback about the data about the citation. This may include the progress made in extracting information from the citation, references to sources that the researcher might look at, and other observations that can improve the quality of the data. Data in this attribute are not intended for publication.


Citation: Type
==============

Attribute name
~~~~~~~~~~~~~~

``::citation/type``

Description
~~~~~~~~~~~~

The method by which an access point to a source has been created, such as by page or archive snapshot

Attribute type
~~~~~~~~~~~~~~

Text, controlled, single entry

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~~~

``page``, ``frame``, ``clip``, ``archive``

Guidance on use
~~~~~~~~~~~~~~~

A source has at least one access point, but may have many. For example, if a source is a document we may draw information from a number of different pages (or ranges of pages). For each page or range of pages, we would create a new access point to the source. The field ``Source: Access Point Type`` tells us what method we have used to create the access point - in this case ``page``. The number of the page or page range will be recorded in a related attribute called `Citation: Trigger`_.

There are eight ways to "trigger" a citation of a specific source, taking in account the source's media type:

- ``archive``: an archive snapshot of the source contains different content from the source, or from other snapshots.
- ``page``: a page or range of page in a document source like a book or report.
- ``line``: a line or range of lines in a line-numbered document like an interview transcript.
- ``clip``: a passage from a video or audio source, comprising a start time and a stop time.
- ``frame``: a single capture point in a video.
- ``still``: an image captured from a video or interactive resource which does not correspond to a specific frame.
- ``paragraph``: where a document is numbered throughout, such as in United Nations Security Council documents, paragraphs can be used as access point triggers.
- ``cell``: the cell reference or range within a table of data

As we seek to include different types of sources in our work, we anticipate updating this list of citation types.

Citation: Trigger
=================

Attribute name
~~~~~~~~~~~~~~

``::citation/trigger``

Description
~~~~~~~~~~~

A set of different types of values that describe where in a source to find the exact content that comprises the citation.

Type of field
~~~~~~~~~~~~~

Number, number range

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``11``, ``11-12``, ``11,13``, ``11,13,14-19``, ``1:31-1:40``, ``3(1)(c)``, ``1.1.1-2.4.1```


Guidance on use
~~~~~~~~~~~~~~~

This field is used to specify the exact content within a source that defines the citation. For example, if we want to create an citation of page 4 of a source then we would set the value in `Citation: Type`_ to ``page`` and enter ``4`` in this attribute. As noted in the documention for `Citation: Type`_ there are eight ways to trigger a citation. These are listed below, along with the data type and format rquired to specify the exact content of the citation:

- ``archive``: Leave empty. The value in `Citation: Archive URL`_ serves as the trigger for this citation type.
- ``page``: Single page (``1``), single range of pages (``1-2``), combination of page and page ranges (``1,2-3,4,5-8``)
- ``line``: Single line (``200``), single range of lines (``200-230``), combination of line and line ranges (``200-230,236,240-250``)
- ``clip``: Single range containing start and end time in the format ``hh:mm:ss`` (``00:01:20-00:01:24``)
- ``frame``: A single capture point from a video in ``hh:mm:ss`` format (``00:01:20``)
- ``still``: A direct link to SFM's hosting library to an image captured from a video or interactive resource for which we do no have a specific time frame. For example, a ``still`` would be the appropriate type of citation to create to enable us to use as evidence multiple views of an online database that didn't provide permalinks for queries.
- ``paragraph``: if a document has numbered paragraphs in any format (e.g. ``3(1)(a)``), they can be captured here.
- ``cell``: the grid reference (``C123``) of the cell, or cell range (``C123-C129``), containing the data used to evidence the claim.

The range of access point triggers may extend as different media forms become available. 

Citation: Accessed Timestamp
==========================

Attribute name
~~~~~~~~~~~~~~

``::citation/accessed-at``

Description
~~~~~~~~~~~

Full date on which the Staff Reseacher created this citation from the source.

Attribute type
~~~~~~~~~~~~~~

Date formatted as``YYYY-MM-DD``

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``2022-02-20``

Guidance on use
~~~~~~~~~~~~~~~

When a Staff Researcher accesses a source in order to create a citation, they should record the full, exact date in this attribute. This data is a useful part of quality assurance processes, enabling us to re-visit sources at set points in time to assess whether they have been updated. Recording an access date at the level of the citation also reflects that we may work on some sources for extended periods of time, or work on the same source at different points in time during our research. 

Citation: Archive URL
=====================

Attribute name
~~~~~~~~~~~~~~

``::citation/archive-url``

Description
~~~~~~~~~~~

URL of a snapshot of the source captured by the Internet Archive and hosted on its Wayback Machine.

Attribute type
~~~~~~~~~~~~~~

String formatted as URL

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``https://web.archive.org/web/20150703120013/http://www.amnesty.org/en/documents/AFR44/043/2012/en/``

Guidance on use
~~~~~~~~~~~~~~~

A source becomes usable by Staff Researchers when it has an citation. After entering the source's basic details (like :ref:`Source: Title`), the researcher can create a first citation by specifying an Internet Archive snapshot to use. If the source is not already archived in the Internet Archive, the researcher should attempt to create a new snapshot to use as the citation. Where snapshots for the source already exist in the Internet Archive, the Staff Researcher should find the snapshot that is earliest in time.

In the majority of cases, this will suffice. However, in some cases, we may need to specify more than one Internet Archive snapshot for the same source - each different snapshot creates a distinct citation. The common reason for this is that the source content changes, but the basic details of the source do not. A good example of this is this (dead) URL published by the *Secretaría de la Defensa Nacional* in Mexico: ``http://www.sedena.gob.mx:80/ejercito/comandancias/gur_mil.htm``. It lists the commanders of Mexico's miltary garrisons, and we have included reference to this in our data about the Mexican army. The title, initial publication date, publication and basic URL did not change: however, over time the content did. In each of 24 different snapshots made by the Internet Archive, the list of commanders is different. In this case, we have a single source with 24 citations: each citations refers to a specific version of that source containing the exact information that we relied upon to create various claims.

The example above also illustrates an important point: sometimes a source is only available in an archived form, because its original source URL is no longer online. There are many reasons a link many no longer be live, and this problem is known as "linkrot". In these cases, the Staff Researcher can fill in :ref:`Source: URL` with a portion of the Internet Archive URL printed after the timestamp. For example:

- Archive URL: ``https://web.archive.org/web/20040208204841/http://www.sedena.gob.mx:80/ejercito/comandancias/gur_mil.htm``
- Original URL extracted from the Archive URL: ``http://www.sedena.gob.mx:80/ejercito/comandancias/gur_mil.htm```


Citation: Archive Timestamp
===========================

Attribute name
~~~~~~~~~~~~~~

``::citation/archive-timestamp``

Description
~~~~~~~~~~~

Timestamp of the Internet Archive snapshot that has been used to create a citation.

Attribute type
~~~~~~~~~~~~~~

Date (YYYY-MM-DDTHH:MM:SSZ)

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``2004-02-08T20:48:41Z``

Guidance on use
~~~~~~~~~~~~~~~

Every snapshot made by the Internet Archive contains a timestamp of the time (GMT/UTC) when that snapshot was created. The timestamp is contained in the URL and looks like this: ``20040208204841``

We extract this part of the URL and reformat it to something more human readable (an ISO 8601 format): ``2004-02-08T20:48:41Z``

The timestamp provides useful quality assurance data.

Citation: External Archive Content Hash
=======================================

Attribute name
~~~~~~~~~~~~~~

``::citation/external-archive:sha-content``

Description
~~~~~~~~~~~

First of a pair of fields recording where a copy of the source can be found in external archives

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``0E94AE36DA6FF03992A57FDDBDF4728B609D0D7FE6EB019FA9F1B9B5B540D835``

Guidance on use
~~~~~~~~~~~~~~~

This is a dynamic field designed to enable interlinking between sources recorded in the format used by Security Force Monitor, and those in use in other collections. This particular field contains an SHA hash of the specific content of a source captured through a scraping process.


Citation: External Archive Metadata Hash
========================================

Attribute name
~~~~~~~~~~~~~~

``::citation/external-archive:sha-meta``

Description
~~~~~~~~~~~

Second of a pair of fields recording where a copy of the source can be found in external archives

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``0E94AE36DA6FF03992A57FDDBDF4728B609D0D7FE6EB019FA9F1B9B5B540D835``

Guidance on use
~~~~~~~~~~~~~~~

This is a dynamic field designed to enable interlinking between sources recorded in the format used by Security Force Monitor, and those in use in other collections. This particular field contains an SHA hash of the specific content of the metadata of a source captured through a scraping process.