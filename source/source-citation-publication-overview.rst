Overview: Sources, Citations and Publications
#############################################

Where does Information Come From?
*********************************

Every data point in the Security Force Monitor's dataset comes from a source. To enable more precise auditing of any data point we have developed a model for structuring information about the sources themselves.

First every source comes from a :ref:`publication` which could be a governmental agency, a media company (like The New York Times), an organization (such as Amnesty International), or an account on social media. These publications produce one or more :ref:`source` which could be a web page, news article, book, report, video, or social media post. These sources are divided into one or more :ref:`citation` which shows the specific part of the :ref:`source` that evidences a ``claim``. Claims are the basic building blocks of our data (see :ref:`Our General Data Model`).

Sources which cannot be easily divided, such as web pages or news articles, only have a single citation for the entire web page or article. Other types of sources which can be easily divided, such as books, reports, or videos, can have multiple citations which can be for a page or grouping of pages, or numbered paragraphs for other types of text sources, or time stamps or time ranges for videos.

To reflect this important difference the data model captures information on these three interlinked, but distinct entities:

- :ref:`Source`: Attributes about the source, such as its title, date of publication, URL.
- :ref:`Citation`: Attribute about the specific part of a source, like the page number, archive version. 
- :ref:`Publication`: Attributes about the organizations or accounts that publish the sources we use, such as their name and country, such as ``British Broadcasting Corporation`` or ``Amnesty International``.

In the remainder of this article, we look at where our sources come from, and provide more detail about the logic of creating citations from sources.


Building the source list
************************

When starting research on a country the Security Force Monitor first builds a small list of sources to deeply explore, extract data from and structure that data into claims. The priorities for this initial source review and extraction are governmental and security forces.

- Government and security force sources, such as the constitution and laws of the country related to security forces; official government media; websites and other media from the relevant ministries of the country (Information, Defense, Interior, and others); websites and other related media published by the security forces;
- Media focused on the country, initially drawn from BBC media profiles for the country or other similar sources;
- Civil society and human rights reporting on the country focused on allegations against security forces;
- Academic and other scholarly research on security forces, which are often found via searches in WorldCat.org

The information contained in these sources are structured into claims as part of the initial research process. Eventually, creating these claims informs the next stage of research.

For the next stage of research, priorities are idenfitied and defined based on gaps in the dataset. Expanded research often relies on keywords from the :ref:`unit:names:assertion` and :ref:`person:names:assertion` fields. This next stage of research will find additional sources and publications for review and extraction, further building the source list. This process can then be repeated as needed to further expand the dataset.


Citing a source
***************

Citations are a flexible device that enables us to reference precisely the material that we have used to support the information in a claim. 

A citation directs us to a particular part of a source as evidence for a information a claim - it's much like a citation in an academic paper. This could be material from a specific page in the source; it could also be a specific archive snapshot of a page, as the content of a webpage can sometimes change over time even though its basic identifying data will not. In this way, a single source can be cited in multiple ways.

There are seven ways to "trigger" a citation of a specific source, taking in account the source's media type:

- ``archive``: an archive snapshot of the source.
- ``page``: a page or range of page in a document source like a book or report.
- ``line``: a line or range of lines in a line-numbered document like an interview transcript.
- ``clip``: a passage from a video or audio source, comprising a start time and a stop time.
- ``frame``: a single capture point in a video.
- ``paragraph``: where a document is numbered throughout, such as in United Nations Security Council documents, paragraphs can be used as access point triggers.
- ``cell``: the cell reference or range within a table of data.

As we seek to include different types of sources in our work, we anticipate updating this list of citation triggers.


Citation examples
*****************

Here are two examples of how citations based on archives and pages work in practice:

.. admonition:: Example 1: Citations based on differences between archive snapshots

   The website of the Bangladesh Police used to publish a page describing the subordinate units of "Dhaka Range". Although this page is no longer live it has been captured in the Internet Archive at various points in time between 2013 and 2018. An assessment of the snapshots shows that though the title, publisher and URL don't change, there are important differences in the content of the webpage. `A 2013 snapshot <https://web.archive.org/web/20180105142913/http://www.police.gov.bd/content.php?id=142>`__ contains details of 18 district police subdivisions that are subordinate to ``Dhaka Range``, but a `2018 one <https://web.archive.org/web/20130904092442/http://www.police.gov.bd:80/content.php?id=142>`__ states there are only 14. This may indicate that some subdivisions of the Dhaka Range were disbanded or placed under a different command structure. In this case, although the details of the source remain the same we have created two citations for it: the first is for the 2013 archive snapshot, the second for the 2018 one.


.. admonition:: Example 2: Citations based on differences between archive snapshots

   In the 2015 report `Stars on their shoulders. Blood on their hands. War crimes committed by the Nigerian military <https://www.amnesty.org/en/documents/afr44/1657/2015/en/>`__ Amnesty International made a large number of allegations against the Nigerian Army. The report is 133 pages long. We have used information from specific pages to evidence specific data points about units, persons and incidents. For example, we use information on page 11 as evidence of the :ref:`person:names:assertion` attribute for claims about "John A. H. Ewansiha"; material from page 24 supplements what we know about the :ref:`unit:names:assertion` attribute claims about "Civilian Joint Task Force." In total, we have created 34 citations for this single source.
