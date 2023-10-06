Overview: Sources and citations
###############################

What are sources?
*****************

Sources contain information about security and defence forces. Security Force Monitor turns sources into claims, which are the basic units of our research data (see :ref:`What is a claim?`). A claim is an assertion of information evidenced by a source. Every claim that we create contains a piece of information (like the name of a unit). Alongside this is a "citation" telling us the from which we got the information, and - where necessary - the specific part of that source (such as the page number or range, or paragraph number). The same source can be cited many times at different citation points. 

To reflect this important difference the data model treats sources and citations as distinct entities comprised of three different attribute sets:

- :ref:`Source`: Attributes about the source, such as its title, date of publication, URL
- :ref:`Citation`: Attribute about the specific part of a source, like the page number, archive version, and research comments about that citation. 
- :ref:`Publication: Attributes about the organizations that publish the sources we use, such as their name and country, such as ``British Broadcasting Corporation`` or ``Amnesty International``.

In the remainder of this article, we look at where our sources come from, and provide more detail about the logic of creating citations from sources.


The sources for sources
***********************

The sources we use are carefully collected from a variety of public sources, generally online. These include:

- Laws of the country;
- Official government media;
- Press releases from the relevant ministries of the country (Information, Defense, Interior, and others);
- Security and defence force newsletters;
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

Many sources are identified through our use of search engines. In these cases we may keep a record of the search engine, the specific search term used, and the date the source was entered into our datasets in any form.

We also identify non-digital resources such as monographs, scholarly literature, biographies and other materials about security services. The existence and availability of these type of sources vary widely from country to country.

Our data capture format for sources and citations is flexible enough to accomodate a wide range of different media. Sources can also be published in a range of different media forms, not only text. Other media forms may include maps, datasets, images, audio recordings, video, social media posts, messages sent through messaging services. 

We may process some types of source further to make the informaiton in them more accessible and useful to our research. For example, we digitised the Karen Human Rights Group's `maps of Karen state in Myanmar <https://khrg.org/maps>`_ to create a useable geospatial dataset of Karen-specific placenames to help us accurately interpret locations mentioned in Karenni sources. 

Citing a source
***************

Citations are a flexible device that enables us to reference precisely the material that we have used to support the information in a claim. 

A citation directs us to a particular part of a source as evidence for a information a claim - it's much like a citation in an academic paper. This could be material from a specific page in the source; it could also be a specific archive snapshot of a page, as the content of a webpage can sometimes change over time even though its basic identifying data will not. In this way, a single source can be cited in multiple ways.

There are eight ways to "trigger" a citation of a specific source, taking in account the source's media type:

- ``archive``: an archive snapshot of the source contains different content from the source, or from other snapshots.
- ``page``: a page or range of page in a document source like a book or report.
- ``line``: a line or range of lines in a line-numbered document like an interview transcript.
- ``clip``: a passage from a video or audio source, comprising a start time and a stop time.
- ``frame``: a single capture point in a video.
- ``still``: an image captured from a video or interactive resource which does not correspond to a specific frame.
- ``paragraph``: where a document is numbered throughout, such as in United Nations Security Council documents, paragraphs can be used as access point triggers.
- ``cell``: the cell reference or range within a table of data

As we seek to include different types of sources in our work, we anticipate updating this list of citation triggers.

We never directly reference a source as evidence for a claim. Rather, we always create a a citation from a source to use inside a claim, which creates a little extra work for us. In many cases, there really is only one way to cite a source: for example, if the source is a short article, or a tweet, then there is't much possiblity for the sort of subdivision that citations allow. However, we start with the open-minded view that source will need to be cited in different ways, and adopt a data structure that enables this to happen.


Citation examples
*****************

Here are two examples of how citations based on archives and pages work in practice:

.. admonition:: Example 1: Citations based on differences between archive snapshots

   The website of the Bangladesh Police used to publish a page describing the subordinate units of "Dhaka Range". Although this page is no longer live it has been captured in the Internet Archive at various points in time between 2013 and 2018. An assessment of the snapshots shows that though the title, publisher and URL don't change, there are important differences in the content of the webpage. `A 2013 snapshot <https://web.archive.org/web/20180105142913/http://www.police.gov.bd/content.php?id=142>`__ contains details of 18 district police subdivisions that are subordinate to ``Dhaka Range``, but a `2018 one <https://web.archive.org/web/20130904092442/http://www.police.gov.bd:80/content.php?id=142>`__ states there are only 14. This may indicate that some subdivisions of the Dhaka Range were disbanded or placed under a different command structure. In this case, although the details of the source remain the same we have created two citations for it: the first is for the 2013 archive snapshot, the second for the 2018 one.


.. admonition:: Example 2: Citations based on differences between archive snapshots

   In the 2015 report `Stars on their shoulders. Blood on their hands. War crimes committed by the Nigerian military <https://www.amnesty.org/en/documents/afr44/1657/2015/en/>`__ Human Rights Watch made a large number of allegations against the Nigerian Army. The report is 133 pages long. We have used information from specific pages to evidence specific data points about units, persons and incidents. For example, we use information on page 11 as evidence of the :ref:`Person Identity: Name` attribute for claims about "John A. H. Ewansiha"; material from page 24 supplements what we know about the :ref:`Unit Identity: Name` attribute claims about "Civilian Joint Task Force". In total, we have created 13 citations for this single source.