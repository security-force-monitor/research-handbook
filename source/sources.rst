Sources
=======

What are sources?
-----------------

Security Force Monitor collects data about the persons and units that comprise security forces, along with allegations of human rights abuses made against security forces. This data is carefully collected from a variety of sources, generally online. These include:

- Laws of the country;
- Official government media;
- Press releases from the relevant ministries of the country (Information, Defense, Interior, and others);
- Security force newsletters;
- Social media pages for security services or government agencies;
- Other social media and messaging services;
- Statistics and data agencies;
- Local government websites;
- Human rights commissions;
- Third country government publications and other documents;
- United Nations publications and other documents;
- Local news reportage;
- Civil society and human rights reporting;
- Academic research; and,
- Other country-specific sources.

We also identify non-digital resources such as monographs, scholarly literature, biographies and other materials about security services. The existence and availability of these type of sources vary widely from country to country.

Sources can also be published in a range of different media forms, not only text. Other media forms may include maps, images, audio recordings, video, social media posts, messages send through messaging services. We have designed the data capture format for sources to be flexible enough to accomodate a wide range of different media.

Sources and Access Points
-------------------------

When we choose to use a source as evidence for a data point, we create a spreadsheet or database entry for it. This entry includes the data required to identify the source: title, publication date, URL, name of publication and so on.

However, a source can have multiple "access points". An access point directs us to a particular part of a source as evidence for a data point - it's much like a citation in an academic paper. This could be material from a specific page in the source; it could also be a specific archive snapshot of a page, as the content of a webpage can sometimes change over time even though its basic identifying data will not. In this way, a single source can have multiple access points.

There are six ways that an access point can be "carved out" of a specific source, taking in account the source's media type:

- ``archive``: an archive snapshot of the source contains different content from the source, or from other snapshots.
- ``page``: a page or range of page in a document source like a book or report.
- ``line``: a line or range of lines in a line-numbered document like an interview transcript.
- ``clip``: a passage from a video or audio source, comprising a start time and a stop time.
- ``frame``: a single capture point from a video.
- ``still``: an image captured from a video or interactive resource which does not correspond to a specific frame.

Here are some examples of how access points based on archives and pages work in practice:

- *Access points based on differences between archive snapshots*: The website of the Bangladesh Police used to publish a page describing the subordinate units of "Dhaka Range". Although this page is no longer live it has been captured in the Internet Archive at various points in time between 2013 and 2018. An assessment of the snapshots shows that though the title, publisher and URL don't change, there are important differences in the content of the webpage. `A 2013 snapshot <https://web.archive.org/web/20180105142913/http://www.police.gov.bd/content.php?id=142>`__ contains details of 18 district police subdivisions that are subordinate to Dhaka Range, but a `2018 one <https://web.archive.org/web/20130904092442/http://www.police.gov.bd:80/content.php?id=142>`__ states there are only 14. This may indicate that some subdivisions of the Dhaka Range were disbanded or placed under a different command structure. In this case, although the details of the source remain the same we have created two access points for it: the first is for the 2013 archive snapshot, the second for the 2018 one.

- *Access points based on page number*: in the 2015 report `Stars on their shoulders. Blood on their hands. War crimes committed by the Nigerian military <https://www.amnesty.org/en/documents/afr44/1657/2015/en/>`__ Human Rights Watch made a large number of allegations against the Nigerian Army. The report is 133 pages long. We have used information from specific pages to evidence specific data points about units, persons and incidents. For example, we use information on page 11 as evidence of the ``Person: Name`` field for "John A. H. Ewansiha"; material from page 24 supplements what we know about the ``Unit: Name`` for "Civilian Joint Task Force". In total, we have created 13 access points for this single source.

Access points are a flexible concept that enable us to specify precisely the material that we have used to evidence data point.

Source: Research Comments
-------------------------

**Description**

Observations specific to the process of reviewing data in this row, including fixes, refinements and other suggestions.

**Type of field**

Text and numbers

**Example of use**

``Source need archiving``, ``How to extract full publication timestamp from post?``, ``Source should not be published because permission has not been given by the resource owner``

**Spreadsheet column name**

``source:comments:admin``

**Shortcode**

``s_c_a``

**Sources**

No

**Confidence**

No

**Guidance on use**

This is an adminstrative field specific to data created in spreadsheets. Staff Researchers use it to pass on feedback about the data in the row. This may included changes needs to specific fields, references to sources that the owner of the row might look at, and other observations that can improve the quality of the data. Data in this field are not intended for publication.

Source: Restricted
------------------

**Description**

Field indicating that the source should not be published on WhoWasInCommand, or distributed in any public product.

**Type of field**

Number, single entry

**Example of use**

``1``

**Spreadsheet column name**

``source:restricted:admin``

**Shortcode**

``s_r_a``

**Guidance on use**

If a source should not be published on WhoWasInCommand, or distributed in any public form, the Staff Analyst can indicate this by placing a ``1`` in the ``Source: Restricted`` field. The reasons for restricted publication of a source should be recorded in ``Source: Research Comments``.

Source: External Archive
------------------------

**Description**

A set of fields recording where a copy of the source can be found in external archives

**Type of field**

Test and numbers

**Example of use**

``0E94AE36DA6FF03992A57FDDBDF4728B609D0D7FE6EB019FA9F1B9B5B540D835``

**Spreadsheet column name**

Presently, the two available field refer to an archive that provides a separate SHA256 hash of both the source's content and its metadata. These are laballed:

``source:external_archive_sha_content:admin`` and ``source:external_archive_sha_meta:admin``

**Shortcode**

``s_eac_a`` and ``s_eam_a``

**Guidance on use**

This is a dynamic field designed to enable interlinking between sources recorded in the format used by Security Force Monitor, and those in use in other collections.

Source: Access Point Unique Identifier
--------------------------------------

**Description**

A unique 32 character code assigned to each access point.

**Type of field**

Text and numbers

**Example of use**

``1c03ec21-0fae-4243-9de6-686568afc2b8``

**Spreadsheet column name**

``source:access_point_id:admin``

**Shortcode**

``s_id_a``

**Guidance on use**

This value is a Universally Unique Indentifier (UUID) generated using a computer program. UUIDs can be created easily using either installable or online tools, for example:

- Linux and OSX users: ``uuidgen`` command line tool.
- On the web: `UUID Generator<https://www.uuidgenerator.net/version>`__.

The field is administrative, providing a reliable way to differentiate between different access points.

When a new access point is created directly in WhoWasInCommand, the platform automatically creates a UUID for that access point and stores it in this field. If a new accesspoint is created in a spreadsheet, the Staff Researcher must generate a unique identifying number for that person and copy it into the field ``source:access_point_id:admin`` for that specific access point. This manual, copy-and-paste step is a potential source of error and the Staff Researcher must be careful not to re-use a UUID.

Bulk updates made to WhoWasInCommand.com by spreadsheet import are based on the values in this field. For example, changes made in the row ``a407be6a-28e6-4237-b4e9-307f27b1202e`` in the spreadsheet will be applied to the access point with that UUID in WhoWasInCommand.

Source: Type
------------

**Description**

Description of the media type of the source, such as "document", "video" or "image".

**Type of field**

Text and numbers, controlled, single entry

**Example of use**

``document``, ``video``, ``message``, ``tweet``, ``post``

**Spreadsheet column name**

``source:type``

**Shortcode**

``s_ty``

**Guidance on use**

Use this field to capture data about the source's basic media type. The choice of values is defined in a controlled vocabulary.

Source: Title
-------------

**Description**

The name of the source, as stated on the source.

**Type of field**

Text and numbers

**Example of use**

``Stars on their shoulders. Blood on their hands. War crimes committed by the Nigerian military``

**Spreadsheet column name**

``source:title``

**Shortcode**

``s_t``

**Guidance on use**

Copy the exact title of the source as stated on the source itself. Where the title has multiple parts, such as a subtitle, also include that.

Source: Author
--------------

**Description**

The name(s) of the person(s) who authored, or otherwise created, the source.

**Type of field**

Text and numbers

**Example of use**

``Osa Okhomina``, ``Tom Moses``, ``Tony Wilson; Tom Longley``

**Spreadsheet column name**

``source:author``

**Shortcode**

``s_a``

**Guidance on use**

Use this field to record the given name and surnames of the persons who authored or otherwise created the source. Typically, this will be a byline containing one or more persons. Where more than one person is credited as the author/creator, use a semi-colon to separate the names.

If the source is a social media post, and the real name of the author/creator cannot be found, record the social media account identity.

Where the author/creator is an organization (e.g. ``Press Association``, ``Reuters and agencies``) do not enter this in ``Source: Author`` - this information will likely be included in ``Source: Publication Name``.

Source: Source URL
------------------

**Description**

The first and original public online location of the source.

**Type of field**

URL

**Example of use**

``https://www.amnesty.org/en/documents/afr44/1657/2015/en/``

**Spreadsheet column name**

``source:url``

**Shortcode**

``s_u``

**Guidance on use**

The URL included here must be for the first and original public online location of the source.

Where possible, if a source is republished through a content sharing or syndication system, attempt to find the original location.

If you are accessing the source through a restricted or subscription-only gateway (such as LexisNexis or ProQuest), attempt to find the original public URL for a source rather than the URL generated by the gateway service.

Source: Creation Date and Time
------------------------------

**Description**

Date and time that the source was created.

**Type of field**

ISO 8601 timestamp, full or partial, UTC timezone (``YYYY-MM-DDThh:mm:ssZ``)

**Example of use**

``2019-11-29T10:25:45Z``, ``2019``, ``2010-11-29``

**Spreadsheet column name**

``source:created_timestamp``

**Shortcode**

``s_ct``

**Guidance on use**

Where available, record the date and time that the source was created. The field accepts full or partial values: at its simplest this is to the year, at its most comprehensive it can be to the second. A creation timestamp may not be available for a source - if this is the case, leave this field blank.

Where the timezone is indicated, convert the timestamp to UTC.

Source: Upload Date and Time
----------------------------

**Description**

Date and time that the source was uploaded to the online platform or service on which it is hosted.

**Type of field**

ISO 8601 timestamp, full or partial, UTC timezone (``YYYY-MM-DDThh:mm:ssZ``)

**Example of use**

``2019-11-29T10:25:45Z``, ``2019``, ``2010-11-29``

**Spreadsheet column name**

``source:uploaded_timestamp``

**Shortcode**

``s_ut``

**Guidance on use**

Where available, record the date and time that the source was uploaded to the online platform or service on which it is hosted. This may different from the date of creation or publication. Upload timestamp information may not be available for source - if this is the case, leave the field blank.

The field accepts full or partial values: at its simplest this is to the year, at its most comprehensive it can be to the second.

Where the timezone is indicated, convert the timestamp to UTC.

Source: Publication Date and Time
---------------------------------

**Description**

Date and time that the source was published on the online platform or service on which it is hosted.

**Type of field**

ISO 8601 timestamp, full or partial, UTC timezone (``YYYY-MM-DDThh:mm:ssZ``)

**Example of use**

``2019-11-29T10:25:45Z``, ``2019``, ``2010-11-29``

**Spreadsheet column name**

``source:published_timestamp``

**Shortcode**

``s_pt``

**Guidance on use**

Where available, record the date and time that the source was published to the online platform or service on which it is hosted. This may different from the date of creation or upload. Although a timestamp for creation and upload dates and times may not be available, it is very likely that at least a publication date will be available for a source. Where a publication date is not available for a source, the timestamp of the earliest snapshot of the source in the Internet Archive should be recorded here.

The field accepts full or partial values: at its simplest this is to the year, at its most comprehensive it can be to the second.

Where the timezone is indicated, convert the timestamp to UTC.

Source: Access Date and Time
----------------------------

**Description**

Full date on which the Staff Reseacher looked at the source or its access points.

**Type of field**

Date (YYYY-MM-DD)

**Example of use**

``2019-02-20``

**Spreadsheet column name**

``source:access_point_access_date``

**Shortcode**

``s_apad``

**Guidance on use**

When a Staff Researcher accesses an access point, they should record the full, exact date in this field. This data is a useful part of quality assurance processes, enabling us to re-visit sources at set points in time to assess whether they have been updated.

Source: Access Point Type
-------------------------

**Description**

The method by which an access point to a source has been created, such as by page or archive snapshot

**Type of field**

Text, controlled, single entry

**Example of use**

``pages``, ``frame``, ``clip``, ``archive``

**Spreadsheet column name**

``source:access_point_trigger``

**Shortcode**

``s_apt``

**Guidance on use**

A source has at least one access point, but may have many. For example, if a source is a document we may draw information from a number of different pages (or ranges of pages). For each page or range of pages, we would create a new access point to the source. The field ``Source: Access Point Type`` tells us what method we have used to create the access point - in this case ``page``. The number of the page or page range will be recorded in the field ``Source: Access Point Trigger``.

Currently, there are six methods for creating an access point:

- ``archive``: an archive snapshot of the source contains different content from the source, or from other snapshots.
- ``page``: a page or range of page in a document source like a book or report.
- ``line``: a line or range of lines in a line-numbered document like an interview transcript.
- ``clip``: a passage from a video or audio source, comprising a start time and a stop time.
- ``frame``: a single capture point from a video.
- ``still``: an image captured from a video or interactive resource which does not correspond to a specific frame.

The range of access point types may extend as different media forms become available.

Source: Access Point Trigger
----------------------------

**Description**

Number or number range describing where in a source to find the exact content that comprises the access point.

**Type of field**

Number, number range

**Example of use**

``11``, ``11-12``, ``11,13``, ``11,13,14-19``, ``1:31-1:40``

**Spreadsheet column name**

``source:access_point_trigger``

**Shortcode**

``s_aptr``

**Guidance on use**

This field is used to specify the exact content within a source that defines the access point. For example, if we want to create an access point at page 4 of a source then we would set the value in ``Source: Access Point Type`` to ``page`` and enter ``4`` in ``Source: Access Point Trigger``. As noted in the documention for ``Source: Access Point Type`` there are six ways to create an access point. These are listed below, along with the data type and format rquired to specify the exact content of the access point:

- ``archive``: duplicate the value in ``Source: Access Point Archive URL``
- ``page``: Single page (``1``), single range of pages (``1-2``), combination of page and page ranges (``1,2-3,4,5-8``)
- ``line``: Single line (``200``), single range of lines (``200-230``), combination of line and line ranges (``200-230,236,240-250``)
- ``clip``: Single range containing start and end time in the format ``hh:mm:ss`` (``00:01:20-00:01:24``)
- ``frame``: a single capture point from a video in ``hh:mm:ss`` format (``00:01:20``)
- ``still``: a direct link to SFM's hosting library to an image captured from a video or interactive resource for which we do no have a specific time frame. For example, a ``still`` would be the appropriate type of access point to create to enable us to use as evidence multiple views of an online database that didn't provide permalinks for queries.

The range of access point triggers may extend as different media forms become available.


Source: Access Point Archive URL
--------------------------------

**Description**

URL of a snapshot of the source captured by the Internet Archive and hosted on its Wayback Machine.

**Type of field**

URL

**Example of use**

``https://web.archive.org/web/20150703120013/http://www.amnesty.org/en/documents/AFR44/043/2012/en/``

**Spreadsheet column name**

``source:archive_url``

**Shortcode**

``s_au``

**Guidance on use**

A source becomes usable by Staff Researchers when it has an access point. After entering the source's basic details (like ``Source: Title``), the researcher then creates the first access point by specifying an Internet Archive snapshot to use for that source. If the source is not already archived in the Internet Archive, the research must create a new snapshot to use as the access point. Where snapshots for the source already exist in the Internet Archive, the Staff Researcher should find the snapshot that is earliest in time.

In the majority of cases, this will suffice. However, in some cases, we may need to specify more than one Internet Archive snapshot for the same source. The common reason for this is that the source content changes, but the basic details of the source do not. A good example of this is this (dead) URL published by the *Secretaría de la Defensa Nacional* in Mexico: ``http://www.sedena.gob.mx:80/ejercito/comandancias/gur_mil.htm``. It lists the commanders of Mexico's miltary garrisons, and we have included reference to this in our data. The title, initial publication date, publication and basic URL did not change: however, the content did. In each of 24 different captures made by the Internet Archive, the list of commanders is different. In this case, we have a single source with 24 access points: each access point refers to a specific version of that source containing the exact information that we relied upon to create the data.

The example above also illustrates an important point: sometimes a source is only available in an archived form, because its original source URL is no longer online. There are many reasons a link many no longer be live, and this problem is known as "linkrot". In these cases, the Staff Researcher can fill in ``Source: URL`` with a portion of the Internet Archive URL printed after the timestamp:

``https://web.archive.org/web/20040208204841/http://www.sedena.gob.mx:80/ejercito/comandancias/gur_mil.htm``

Source: Access Point Archive Timestamp
--------------------------------------

**Description**

Timestamp of the Internet Archive snapshot used to create an access point.

**Type of field**

Date (YYYY-MM-DDTHH:MM:SS)

**Example of use**

``2004-02-08T20:48:41``

**Spreadsheet column name**

``source:access_point_archive_timestamp``

**Shortcode**

``s_apat``

**Guidance on use**

Every snapshot made by the Internet Archive contains a timestamp of the time (GMT/UTC) when that snapshot was created. The timestamp is contained in the URL and looks like this:

``20040208204841``

We extract this part of the URL and reformat it to something more human readable (an ISO 8601 format):

``2004-02-08T20:48:41``

The timestamp is a useful quality assurance filter, and is used in the WhoWasInCommand data entry tools as a visual aid to differentiate between access points.

Source: Publication Country
---------------------------

**Description**

County in which the publication or publishing organization of the source is based.

**Type of field**

Text, controlled vocabulary

**Example of use**

``United States``, ``Nigeria``

**Spreadsheet column name**

``source:publication_country``

**Shortcode**

``s_c``

**Guidance on use**

Values for this field are the English language full names of countries contained in the list of ISO 3166-1 alpha-2 codes, which can be found (`on the ISO website <https://www.iso.org/obp/ui/#search/code/>`__ and on `Wikipedia <https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Officially_assigned_code_elements>`__).

Source: Publication Name
------------------------

**Description**

The name of the publication, or publishing organization, of the source.

**Type of field**

Text

**Example of use**

``Amnesty International``, ``Secretaría de la Defensa Nacional``, ``Daily Independent``, ``The Irrawady``

**Spreadsheet column name**

``source:publication_title``

**Shortcode**

``s_pt``

**Guidance on use**

This field can cover two sorts of publication:

- The publication in which the source appears, which could be a newspaper, journal or a book.
- Absent a specific publication, include the name of the publishing organization, such as the government organization responsible for a web-page.

Source: Publication Unique Identifier
-------------------------------------

**Description**

A unique 32 chracter code assigned to each publication from which sources are drawn.

**Type of field**

Text and numbers

**Example of use**

``2190a9b4-8163-47a6-8461-3157f68c3ba3``

**Spreadsheet column name**

``source:publication_id:admin``

**Shortcode**

``s_pid_a``

**Guidance on use**

This value is a Universally Unique Indentifier (UUID) generated using a computer program. UUIDs can be created easily using either installable or online tools, for example:

- Linux and OSX users: `uuidgen` command line tool.
- On the web: `UUID Generator<https://www.uuidgenerator.net/version>`__.

The field is administrative, providing a reliable way to differentiate between different publications (which in some cases may have the same name).

When a new publication is created directly in WhoWasInCommand, the platform automatically creates a UUID for that source and stores it in this field. If a new publication is created in a spreadsheet, the Staff Researcher must generate a unique identifying number for that publication and copy it into the field ``publication:id:admin`` for every row associated with that specific publication. This manual, copy-and-paste step is a potential source of error and the Staff Researcher must be careful not to re-use a UUID.
