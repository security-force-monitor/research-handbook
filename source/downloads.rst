What data can I download from WhoWasInCommand?
==============================================

.. note ::

   May 2022: The WhoWasInCommand.com download feature is experimental and subject to change. Currently, the downloads do not reflect improvements in how the Security Force Monitor data model deals with Locations. 


Data for download
-----------------

Any data published on WhoWasInCommand can be downloaded as a set of Comma Separated Values (.csv) files. These can be easily loaded into a spreadsheet or database tool for analysis. To use WhoWasInCommand's data download feature visit the following link:

https://whowasincommand.com/en/download

The Security Force Monitor data model is a directed graph containing attriutes about units, persons, locations as they change across time. This is quite complicated and does not easily translate into a single file that is straightforward to understand and use without guidance. To get around this and provide a way to provide raw data directly to users, we offer seven different reports drawn from the data on a specific country:

-  **Basic**: a list of all the units in that country
-  **Parentage**: units organized into a hierarchy
-  **Memberships**: units that are part of operations that may fall outside the regular chain of command
-  **Areas of operation**: geographical distribution of units' operational areas
-  **Sites**: specific locations
-  **Personnel**: list of command personnel
-  **Sources**: sources used to evidence the data

A full description of each downloadable slice of data is available in the sections below. It is important to note that none of the download contain the field-level sourcing that is a key part of Security Force Monitor's work (see :ref:`Data integrity measures` for more information). The reason for this is technical (discussed `here <https://github.com/security-force-monitor/sfm-cms/issues/661#issuecomment-635450705>`__ on the code repository for the software that powers WhoWasInCommand.

How to download
---------------

Visit the download page: `https://whowasincommand.com/en/download <https://whowasincommand.com/en/download/>`__

The interface looks like this:

.. figure:: _static/wwic_download_data_1.png
   :alt: 

Use the dropdown menu to select the report that you want to download:

.. figure:: _static/wwic_download_data_2.png
   :alt:

Then, use the next dropdown menu to choose the country about which you want to download data:

.. figure:: _static/wwuc_download_data_3.png
   :alt:

Optionally, tick the checkbox to include Confidence Scores in the downloaded report. Read the page on :ref:`Confidence scores` for more information about this data integrity measure. As mentioned above, downloads do not currently include field-level sourcing.

Finally, click "Download" and a file containing the report will be downloaded to your computer. To help you identify the report, its filename is created using this simple template: ``[report_type]_-[country]_[YYYY-MM-DD].csv"``

Contents of each download
-------------------------

In this section we outline the seven different slices of data that users can download from WhoWasInCommand.com.

Basic
^^^^^

**Description**

The "Basic" download contains a list of distinct units in the dataset, along with force branch, aliases, earliest and latest observation dates for each unit.

**Field**

1   unit:id:admin
2   unit:name
3   unit:country
4   unit:classification
5   unit:other_names
6   unit:first_cited_date
7   unit:last_cited_date
8   unit:first_cited_date_start
9   unit:last_cited_date_open
``

Parentage
^^^^^^^^^

**Description**

The "Parentage" download contains data that describes how units fit into the organizational structure of the security and defence forces of the specified country. Each row contains a child-parent (``unit:name`` - ``unit:related_unit``) relationship inside the orgaizational hierarchy. Each row also contains data on the timescale for each relationship. You can find more information about how relatioships between units work in the :ref:`Unit: Related Unit` section of this handbook.

**Fields**

1   unit:id:admin
2   unit:name
3   unit:country
4   unit:classification
5   unit:other_names
6   unit:first_cited_date
7   unit:last_cited_date
8   unit:first_cited_date_start
9   unit:last_cited_date_open
10  unit:related_unit
11  unit:related_unit:name
12  unit:related_unit:country
13  unit:related_unit_class
14  unit:related_unit_first_cited_date
15  unit:related_unit_first_cited_date_start
16  unit:related_unit_last_cited_date
17  unit:related_unit_open

Memberships
^^^^^^^^^^^

**Description**

The "Memberships" download contains data showing that the unit has been attached to internal/national joint operations, international peacekeeping operations, or other multi-unit efforts. These operational unit groupings exist in parallel to units' positionings in the regular organizational structure as described in the "Parentage" download. You can find more information about how memberships work in the :ref:`Unit: Related Unit` section of this handbook.

**Fields**

1   unit:id:admin
2   unit:name
3   unit:country
4   unit:classification
5   unit:other_names
6   unit:first_cited_date
7   unit:last_cited_date
8   unit:first_cited_date_start
9   unit:last_cited_date_open
10  unit:membership_id
11  unit:related_unit
12  unit:member_country
13  unit:member_classification
14  unit:related_unit_first_cited_date
15  unit:related_unit_first_cited_date_start
16  unit:related_unit_last_cited_date
17  unit:related_unit_open

Areas of operation
^^^^^^^^^^^^^^^^^^

**Description**

The "Areas of operation" download describes the geographical areas that units have either been assigned to or in which they have been observed operating within. The Research Handbook sections :ref:`Unit: Location Type`, :ref:`Unit: Location` and :ref:`Locations` describe the concept of an area of operation in more detail.

**Fields**

1   unit:id:admin
2   unit:name
3   unit:country
4   unit:classification
5   unit:other_names
6   unit:first_cited_date
7   unit:last_cited_date
8   unit:first_cited_date_start
9   unit:last_cited_date_open
10  unit:area_ops_id
11  unit:area_ops_name
12  unit:area_ops_country
13  unit:area_ops_feature_type
14  unit:area_ops_admin_level
15  unit:area_ops_admin_level_1_id
16  unit:area_ops_admin_level_1_name
17  unit:area_ops_admin_level_2_id
18  unit:area_ops_admin_level_2_name

Sites
^^^^^

**Description**

The "Sites" download describes the specific locations at which specific units have been observed. This download covers locations like infrastructure (such as police stations, barracks, airfields) and specific settlements. The Research Handbook sections :ref:`Unit: Location Type`, :ref:`Unit: Location` and :ref:`Locations` describe the concept of site in more detail.

**Fields**

1   unit:id:admin
2   unit:name
3   unit:country
4   unit:classification
5   unit:other_names
6   unit:first_cited_date
7   unit:last_cited_date
8   unit:first_cited_date_start
9   unit:last_cited_date_open
10  unit:site_exact_location_id_latitude
11  unit:site_exact_location_name_longitude
12  unit:site_country
13  unit:site_feature_type
14  unit:site_admin_level
15  unit:site_nearest_settlement_id
16  unit:site_nearest_settlement_name
17  unit:site_first_admin_area_id
18  unit:site_first_admin_area_name


Personnel
^^^^^^^^^

**Description**

The "Personnel" download provides data on people holding command positions in specific units. The download is organized by the unit to which a person was posted. It contains data on the person's posting (such as their role, rank, and title) in addition to any further biographical information (social media accounts, imagery of them, and so on). More information about how Security Force Monitor records data about persons is in the Research Handbook sections on :ref:`Persons` and :ref:`Persons Extra`.

**Fields**

1   unit:id:admin
2   unit:name
3   unit:country
4   unit:classification
5   unit:other_names
6   unit:first_cited_date
7   unit:last_cited_date
8   unit:first_cited_date_start
9   unit:last_cited_date_open
10  person:admin:id
11  person:name
12  person:other_names
13  person:country
14  person_extra:date_of_birth
15  person_extra:deceased_date
16  person_extra:deceased
17  person_extra:account_type
18  person_extra:account_id
19  person_extra:external_link_description
20  person_extra:media_desc
21  person_extra:notes:admin
22  person:posting_role
23  person:posting_rank
24  person:posting_title
25  person:posting_first_cited_date
26  person:posting_first_cited_date:year
27  person:posting_first_cited_date:month
28  person:posting_first_cited_date:day
29  person:posting_first_cited_date_start
30  person:posting_first_cited_date_start_context
31  person:posting_last_cited_date
32  person:posting_last_cited_date:year
33  person:posting_last_cited_date:month
34  person:posting_last_cited_date:day
35  person:posting_last_cited_date_end
36  person:posting_last_cited_date_end_context

Sources
^^^^^^^

**Description**

The "Sources" download contains a list of all the sources used to evidence data on WhoWasInCommand. Unlike the other downloads, the content of the "Sources" download is not limited to a specific country: it's everything referenced anywhere in WhoWasInCommand. To learn more about how Security Force Monitor uses sources, visit the sections of the Research Handbook about :ref:`Data integrity measures` and :ref:`Sources`.

**Fields**

1   source:id:admin
2   source:title
3   source:type
4   source:author
5   source:publication_name
6   source:publication_country
7   source:published_timestamp
8   source:created_timestamp
9   source:uploaded_timestamp
10  source:url
11  source:access_point_id
12  source:access_point_type
13  source:access_point_trigger
14  source:accessed_timestamp
15  source:archive_url
