Citation
########

A citation directs us to a particular part of a source evidencing the claim, like a citation in an academic paper. This could be material from a specific page in the source; it could also be a specific archive snapshot of a page, as the content of a webpage can sometimes change over time even though its basic identifying data will not. A single source can be cited in multiple ways, and, once created, a citation can be re-used to evidence any number of claims. 

Citation: Summary of attributes
********************************

The table below summarizes the following dimensions of citations records:

 - Attribute label: a human readable label for the attribute
 - Status: whether the attribute is optional or required in a record
 - Data type: the sort of data that can be entered into the attribute
 - Key name: a standardized name that simplifies attribute use in SFM databases


.. csv-table::
   :file: _static/cluster-source-citations.csv
   :header-rows: 1
   :delim: tab


Citation: Details of attributes
********************************

This section contains further information about each attribute, including descriptions, examples of use, and guidance on use.


source:comments:admin
=====================

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

Key name
~~~~~~~~

``n/a``

Guidance on use
~~~~~~~~~~~~~~~

Staff Researchers use this attribute to pass on feedback about the data about the citation. This may include the progress made in extracting information from the citation, references to sources that the researcher might look at, and other observations that can improve the quality of the data. Data in this attribute are not intended for publication.


source:status:admin
===================

Description
~~~~~~~~~~~

A field that classifies the citation

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is not yet implemented.

Key name
~~~~~~~~

``n/a``

Example of use
~~~~~~~~~~~~~~

Field not yet implemented

Guidance on use
~~~~~~~~~~~~~~~

Field not yet implemented.


source:access_point_id:admin
============================

Description
~~~~~~~~~~~

A unique 32 character code assigned to each citation.

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

``1c03ec21-0fae-4243-9de6-686568afc2b8``

Guidance on use
~~~~~~~~~~~~~~~

This field is for the Universally Unique Identifier (UUID) assigned to the citation. Each citation can only have a single UUID.


source:access_point_type
========================

Description
~~~~~~~~~~~~

The method by which an access point to a source has been created, such as by page or archive snapshot

Attribute type
~~~~~~~~~~~~~~

Text, controlled, single entry

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:citation/type``

Example of use
~~~~~~~~~~~~~~~~

``page``, ``frame``, ``clip``, ``archive``

Guidance on use
~~~~~~~~~~~~~~~

A source has at least one access point, but may have many. For example, if a source is a document we may draw information from a number of different pages (or ranges of pages). For each page or range of pages, we would create a new access point to the source. The field ``Source: Access Point Type`` tells us what method we have used to create the access point - in this case ``page``. The number of the page or page range will be recorded in a related attribute called `source:access_point_trigger`_.

There are eight ways to "trigger" a citation of a specific source, taking in account the source's media type:

- ``archive``: an archive snapshot of the source.
- ``page``: a page or range of page in a document source like a book or report.
- ``line``: a line or range of lines in a line-numbered document like an interview transcript.
- ``clip``: a passage from a video or audio source, comprising a start time and a stop time.
- ``frame``: a single capture point in a video.
- ``paragraph``: where a document is numbered throughout, such as in United Nations Security Council documents, paragraphs can be used as access point triggers.
- ``cell``: the cell reference or range within a table of data

As we seek to include different types of sources in our work, we anticipate updating this list of citation types.


source:access_point_trigger
===========================

Description
~~~~~~~~~~~

A set of different types of values that describe where in a source to find the exact content that comprises the citation.

Type of field
~~~~~~~~~~~~~

Number, number range

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:citation/trigger``

Example of use
~~~~~~~~~~~~~~

``11``, ``11-12``, ``11,13``, ``11,13,14-19``, ``1:31-1:40``, ``3(1)(c)``, ``1.1.1-2.4.1```


Guidance on use
~~~~~~~~~~~~~~~

This field is used to specify the exact content within a source that defines the citation. For example, if we want to create a citation of page 4 of a source then we would set the value in `source:access_point_type`_ to ``page`` and enter ``4`` in this attribute. As noted in the documentation for `source:access_point_type`_ there are seven ways to trigger a citation. These are listed below, along with the data type and format required to specify the exact content of the citation:

- ``archive``: Leave empty. The value in `source:archive_url`_ serves as the trigger for this citation type.
- ``page``: Single page (``1``), single range of pages (``1-2``), combination of page and page ranges (``1,2-3,4,5-8``)
- ``line``: Single line (``200``), single range of lines (``200-230``), combination of line and line ranges (``200-230,236,240-250``)
- ``clip``: Single range containing start and end time in the format ``hh:mm:ss`` (``00:01:20-00:01:24``)
- ``frame``: A single capture point from a video in ``hh:mm:ss`` format (``00:01:20``)
- ``paragraph``: if a document has numbered paragraphs in any format (e.g. ``3(1)(a)``), they can be captured here.
- ``cell``: the grid reference (``C123``) of the cell, or cell range (``C123-C129``), containing the data used to evidence the claim.

The range of access point triggers may extend as different media forms become available. 


source:accessed_timestamp
=========================

Description
~~~~~~~~~~~

Full date on which the researcher created this citation from the source.

Attribute type
~~~~~~~~~~~~~~

Date formatted as``YYYY-MM-DD``

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:citation/accessed-at``

Example of use
~~~~~~~~~~~~~~

``2022-02-20``

Guidance on use
~~~~~~~~~~~~~~~

When a Staff Researcher accesses a source in order to create a citation, they should record the full, exact date in this attribute. This data is a useful part of quality assurance processes, enabling us to re-visit sources at set points in time to assess whether they have been updated. Recording an access date at the level of the citation also reflects that we may work on some sources for extended periods of time, or work on the same source at different points in time during our research. 


source:archive_url
==================

Description
~~~~~~~~~~~

URL of a snapshot of the source captured by the Internet Archive and hosted on its Wayback Machine.

Attribute type
~~~~~~~~~~~~~~

String formatted as URL

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:citation/archive-url``

Example of use
~~~~~~~~~~~~~~

``https://web.archive.org/web/20150703120013/http://www.amnesty.org/en/documents/AFR44/043/2012/en/``

Guidance on use
~~~~~~~~~~~~~~~

A source becomes usable by Staff Researchers when it has a citation. After entering the source's basic details (like :ref:`Source: Title`), the researcher can create a first citation by specifying an Internet Archive snapshot to use. If the source is not already archived in the Internet Archive, the researcher should attempt to create a new snapshot to use as the citation. Where snapshots for the source already exist in the Internet Archive, the Staff Researcher should find the snapshot that is earliest in time.

In the majority of cases, this will suffice. However, in some cases, we may need to specify more than one Internet Archive snapshot for the same source - each different snapshot creates a distinct citation. The common reason for this is that the source content changes, but the basic source level details such as the title or url of the source do not. A good example of this is this (dead) URL published by the *Secretaría de la Defensa Nacional* in Mexico: ``http://www.sedena.gob.mx:80/ejercito/comandancias/gur_mil.htm``. It lists the commanders of Mexico's military garrisons, and we have included reference to this in our data about the Mexican army. The title, initial publication date, publication and basic URL did not change: however, over time the content did. In each of 24 different snapshots made by the Internet Archive, the list of commanders is different. In this case, we have a single source with 24 citations: each citation refers to a specific version of that source containing the exact information that we relied upon to create various claims.

The example above also illustrates an important point: sometimes a source is only available in an archived form, because its original source URL is no longer online. There are many reasons a link many no longer be live, and this problem is known as "linkrot". In these cases, the researcher can fill in :ref:`source:url` with a portion of the Internet Archive URL printed after the timestamp. For example:

- Archive URL: ``https://web.archive.org/web/20040208204841/http://www.sedena.gob.mx:80/ejercito/comandancias/gur_mil.htm``
- Original URL extracted from the Archive URL: ``http://www.sedena.gob.mx:80/ejercito/comandancias/gur_mil.htm```


source:archive_timestamp
========================

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

