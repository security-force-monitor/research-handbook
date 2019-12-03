Persons
=======

What are persons?
-----------------

Persons are natural persons who are affiliated with, or hold positions of command over a specific unit at a particular point in time.

The fields in the "Persons" data capture format are used to record basic details about a person's identity, along with their career within a branch of the security force. Using these fields we can capture a persons rank, role and title in one or numerous differe units and see how it has changed over time.

This data capture format is supplemented by the "Persons Extra" format, which enables the capture of other biographical details (like their date of birth, and then they may have died), their social media accounts, and media that provide information about how a person looks and sounds.

Person: Unique Identier
-----------------------

**Description**

A unique 32 character code assigned to each person in the dataset.

**Type of field**

Text and numbers

**Example of use**

``a848de4e-ebeb-49d6-9099-7e68ca3b57fc``

**Spreadsheet column name**

``person:id:admin``

**Shortcode**

``p_id_a``

**Sources**

No

**Confidence**

No

**Guidance on use**

This value is a Universally Unique Indentifier (UUID) generated using a computer program. UUIDs can be created easily using either installable or online tools, for example:

- Linux and OSX users: `uuidgen` command line tool.
- On the web: `UUID Generator<https://www.uuidgenerator.net/version>`_.

The field is administrative, providing a reliable way to differentiate between different persons. In earlier versions, Security Force Monitor used ``person:name`` to do this role but this provided inefficient as the dataset grew.

When a new person is created directly in WhoWasInCommand, the platform automatically creates a UUID for that person and stores it in this field. If a new person is created in a spreadsheet, the Staff Researcher must generate a unique identifying number for that person and copy it into the field ``person:id:admin`` for every row associated with that specific person. This manual, copy-and-paste step is a potential source of error and the Staff Researcher must be careful not to re-use a UUID.

Bulk updates made to WhoWasInCommand.com by spreadsheet import are based on the values in this field. For example, changes made in the row ``a407be6a-28e6-4237-b4e9-307f27b1202e`` in the spreadsheet will be applied to the person with that UUID in WhoWasInCommand. 

Person: Research Owner
----------------------

Initials of Staff Reseacher who first created the person.

**Type of field**

Text

**Example of use**

``TL``, ``TW``, ``MM``

**Spreadsheet column name**

``person:owner:admin``

**Shortcode**

``u_own_a``

**Sources**

No

**Confidence**

No

**Guidance on use**

This field is administrative and only used where data are created using a spreadsheets. It is a simple measure to help researchers keep track of records they have created. These data are not imported into WhoWasInCommand. Instead, WhoWasInCommand keeps a record of the changes (edits, new records, deletions) by the name of the system user who made them.

Person: Research Status
-----------------------

**Description**

The place of a row of data in the research workflow.

**Type of field**

Number range from 0 to 3

**Example of use**

``1``

**Spreadsheet column name**

``person:status:admin``

**Shortcode**

``u_sta_a``

**Sources**

No

**Confidence**

No

**Guidance on use**

This administrative field is only used in spreadsheets. Staff Researchers use this field to indicate where a row of data stands in the research workflow between the first cut of a row of data, review by other researchers, and final readiness for publication. Values in this field are taken from the below controlled list:

- `0`: First commit. This row of data has just been added and needs review.
- `1`: Fixes needed. A reviewer has made comments that need to be addressed, which will be recorded in the ``person:comment:admin`` field.
- `2`: Fixes made. The owner of this data has addressed the reviewer's comments.
- `3`: Clean. A final check has been made by a reviewer, and this row of data can be published.

Data created and managed in WhoWasInCommand does not use this mechanism. At the time of writing, a simple review system is being implemeneted in WhoWasInCommand.

Person: Research Comments
-------------------------

**Description**

Observations specific to the process of reviewing data in this row, including fixes, refinements and other suggestions.

**Type of field**

Text

**Example of use**

``Parent person missing``, ``Possible duplicate - merge?``

**Spreadsheet column name**

``person:comments:admin``

**Shortcode**

``u_com_a``

**Sources**

No

**Confidence**

No

**Guidance on use**

This is an adminstrative field specific to data created in spreadsheets. Staff Researchers use it to pass on feedback about the data in the row. This may included changes needs to specific fields, references to sources that the owner of the row might look at, and other observations that can improve the quality of the data. Data in this field are not intended for publication. 

Person: Name
------------

**Description**

Full name of the person, including given, patronym and surnames.

**Type of field**

Text and numbers

**Example of use**

``Magaji Musa Majia'a``

**Spreadsheet column name**

``person:name``

**Shortcode**

``p_n``

**Sources**

Yes (``person:name:source``, ``p_n_s``)

**Confidence**

Yes (``person:name:confidence``, ``p_n_c``)

**Guidance on use**

Different sources will spell the name of a person in different ways, so we choose a name to be a canonical entry for that person. Whenever possible, the canonical entry will contain the most complicated or complete version of a person's name, even if it has the smallest number of citations. For example ``Magaji Musa Majia'a`` will be used instead of ``Magaji Majiaa``. Other names will be placed in the ``Person: Othr Names`` field (documented below). Titles, roles, honorifics and other attributes that are more correctly linked to a person's posting in a unit are recorded in fields like ``Person: Posting Rank``, ``Person: Posting Role`` or ``Person: Posting Title``.

Person: Other Names
-------------------

**Description**

Other names used to identify a person.

**Type of field**

Text and numbers, free entry

**Example of use**

``Virgilio Daniel Méndez Bazan``, ``Virgilio Daniel Mendez Bazán``

**Spreadsheet column name**

``person:other_names``

**Shortcode**

``p_on``

**Sources**

Yes (``person:name:source``, ``p_on_s``)

**Confidence**

Yes (``person:other_names:confidence``, ``p_on_c``)

**Guidance on use**

Different sources will spell a person's name in different ways. We choose and record a canonical version of a person's name in the ``Person: Name`` field. All other spellings that we have found are treated as aliases and stored in this field. This field may contain multiple values, which will be separated by a semi-colon. Titles, roles, honorifics and other attributes that are more correctly linked to a person's posting in a unit are recorded in fields like ``Person: Posting Rank``, ``Person: Posting Role`` or ``Person: Posting Title``.

Person: Country
---------------

**Description**

Country where a unit that a person is a member of is located.

**Type of field**

Text, controlled vocabulary

**Example of use**

``mx``

**Spreadsheet column name**

``person:country``

**Shortcode**

``p_c``

**Sources**

Yes (``person:country:source``, ``p_c_s``), but only in WhoWasInCommand and not spreadsheets.

**Confidence**

Yes (``person:country:confidence``, ``p_c_c``), but only in WhoWasInCommand and not spreadsheets.

**Guidance on use**

Values for this field are chosen from the list of ISO 3166-1 alpha-2 codes, which can be found (`on the ISO website <https://www.iso.org/obp/ui/#search/code/>`__ and on `Wikipedia <https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Officially_assigned_code_elements>`__. This field does not denote the citizenship or country of origin of a person. Rather, it denotes where a unit they are a member of is located. For example, if ``1 Batallón de Infantería`` is located in Juarez, Mexico, the unit will be assigned a value of ``mx`` in the field ``Unit: Country``. Any person who is a member of that unit will be assigned a value of ``mx`` in the field ``Person: Country`` as well. A person may have multiple entries for ``Person: Country`` where our research shows they or a unit they are a member of is deployed to different countries.

Person: Posting to Unit
-----------------------

**Description**

The unit that the person is a member of.

**Type of field**

Text and numbers, controlled vocabulary

**Example of use**

``35 Batallón de Infantería``

**Spreadsheet column name**

``person:posting``

**Shortcode**

``p_p``

**Sources**

Yes (``person:posting:source``, ``p_p_s``)

**Confidence**

Yes (``person:posting:confidence``, ``p_p_c``)

**Guidance on use**

Values in this field correspond with names of units that already exist in the dataset (recording in the field ``Unit: Name``. A person can have multiple postings to the same unit. These are triggered when there is a change to their entries for ``Person: Posting Rank``, ``Person: Posting Title`` or ``Person: Posting Role`` with respect to the unit. An example of this is where a person is promoted. Another case where a person can have multiple posting of the same unit is where research indicates there are clear start or end dates to a posting. An example of where this might occur is if a person does multiple "tours" in a particular unit.

Person: Posting Role
--------------------

**Description**

The role a person plays in the unit that is not evident from entries in ``Person: Posting Title`` or ``Person: Posting Rank``.

**Type of field**

Text and numbers, controlled vocabulary

**Example of use**

``Commander``

**Spreadsheet column name**

``person:posting_role``

**Shortcode**

``p_pro``

**Sources**

Yes (``person:posting_role:source``, ``p_pro_s``)

**Confidence**

Yes (``person:posting_role:confidence``, ``p_pro_c``)

**Guidance on use**

The most common value we record in ``Person: Posting Role`` is ``Commander``.

There are a variety of other roles a person can have including ``Second in Command``, ``Chief of Staff`` along with other less common entries. They will vary between countries.

As a special note, heads of academic or other security force institutions will sometimes be referred to as the ``Commandant``. In these cases, ``Commandant`` should be recorded in the ``Title`` field, and their role should be recorded as ``Commander``.

If a person is referred to as “the head”, “chief” or some other variation indicating that they are in charge of a unit, they should be regarded as the ``Commander`` for the purposes of entering a value in ``Person: Posting Role``.

Person: Posting Title
---------------------

**Description**

A title held by a person that is separate from their rank or role.

**Type of field**

Text and numbers, free entry

**Example of use**

``General Officer Commanding``, ``Jefe Del Estado Mayor``

**Spreadsheet column name**

``person:posting_title``

**Shortcode**

``p_pt``

**Sources**

Yes (``person:posting_title:source``, ``p_pt_s``)

**Confidence**

Yes (``person:posting_title:confidence``, ``p_pt_c``)

**Guidance on use**

The range of titles will vary from country to country. For example, commanders of army divisions in Nigeria, who usually hold the rank of ``Major General`` also hold the title of ``General Officer Commanding``.

Person: Posting Rank
--------------------

**Description**

The official position of a person in the hierarchy of a security force.

**Type of field**

Text and numbers, free entry

**Example of use**

``General de División``, ``Teniente Coronel``, ``Air Vice Marshal``

**Spreadsheet column name**

``person:posting_rank``

**Shortcode**

``p_pr``

**Sources**

Yes (``person:posting_rank:source``, ``p_pr_s``)

**Confidence**

Yes (``person:posting_rank:confidence``, ``p_pr_c``)

**Guidance on use**

We remove any dashes that are contained in ``Person: Posting Rank`` values.

    For example, we would enter ``Brigadier General`` rather than ``Brigadier-General``.

Person: Posting First Cited Date
--------------------------------

**Description**

The earliest date a source evidences a relationship between a person and a unit, either through direct reference in the source or by the date of its publication.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Spreadsheet column name**

``person:posting_first_cited_date``

**Shortcode**

``p_pfcd``

**Sources**

Yes (``person:posting_first_cited_date:source``, ``p_pfcd_s``)

**Confidence**

Yes (``person:posting_first_cited_date:confidence``, ``p_pfcd_c``)

**Guidance on use**

Along with the fields ``Person: Posting First Cited Date is Start Date``, ``Person: Posting Last Cited Date`` and ``Person: Posting Last Cited Date is End Date`` this field provides data about the time period over which we can evidence a person's relationships to a unit.

The ``Person: Posting First Cited Date`` field contains a date that is either:

-  The earliest date found in the content of a source that specifically references the relationship between a person and a unit; or,
-  The earliest date of publication of sources that makes reference to the relationship between a person and a unit.

    For example, if three sources published on 1 January 2012, 1 February 2012 and 1 March 2012 all refer to this person as a commander, we will use 1 January 2012 as the value in ``Person: Posting First Cited Date``. If the source published on 1 March 2012 refers to this person as a commander on the date of 30 June 2011, we will use 30 June 2011 as the value in ``Person: Posting First Cited Date``.

The values for ``Person: Posting Title``, ``Person: Posting Role`` and ``Person: Posting Rank`` held by a person are assumed to continue until a source indicates a change in any of those values. If the person's role, title or rank changes a new entry will need to be created to document that change. This new entry will have updated values for ``Person: Posting First Cited Date`` and related date fields.

    For example, if a source indicates that Major General Jack Johnson is the commander of 1 Division as of 2007-08-20 all of the relevant fields would be entered based on that source. If another source states that Jack Johnson retired from the 1 Division on 2008-01-10 the last citation for Jack Johnson's affiliation would be 2008-01-10. However, this would also assume that Jack Johnson continued to have the Role of Commander and the Rank of Major General from 2007-08-20 until 2008-01-10.

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Person: Posting First Cited Date``.

This field is clarified by the field ``Person: Posting First Cited Date is Start Date`` which indicates whether the date included here is the actual date on which the relationship between a person and a unit started.

Person: Posting First Cited Date is Start Date
----------------------------------------------

**Description**

Indicates whether the value in ``Person: Posting First Cited Date`` is the actual date on which a person became a member of this unit, or the earliest date a source has referred to the relationship.

**Type of field**

Boolean

**Example of use**

``Y``, ``N``

**Spreadsheet column name**

``person:posting_first_cited_date_start``

**Shortcode**

``p_pfcds``

**Sources**

Yes. Inherits from ``Person: Posting First Cited Date`` (``person:posting_first_cited_date:source``, ``p_pfcd_s``)

**Confidence**

Yes. Inherits from ``Person: Posting First Cited Date`` (``person:posting_first_cited_date:confidence``, ``p_pfcd_c``)

**Guidance on use**

This is a clarifying field for ``Person: Posting First Cited Date`` and has two options:

- ``Y``: Where the content of the source has indicated the exact date that a relationship between a person and a unit began
- ``N``: In all other cases we will enter a value of ``N`` to indicate that the date is not a start date, but the date of first citation.

Person: Context for Posting Start Date
--------------------------------------

**Description**

Additional information explaining why we are able to be specific about the start date of a person's specific posting to a unit. 

**Type of field**

Text

**Example of use**

``Person was promoted on this date``, ``Person retired from the army on this date``

**Spreadsheet column name**

``person:posting_first_cited_date_start_context``

**Shortcode**

``p_pfcdsc``

**Sources**

Yes (``person:posting_first_cited_date_start_context:source``, ``p_pfcdsc_s``)

**Confidence**

Yes (``person:posting_first_cited_date_start_context:confidence``, ``p_pfcdsc_c``)

**Guidance on use**

This field is not currently in use in spreadsheets or WhoWasInCommand. 

This is a clarifying field for the ``Person: Posting First Cited Date is Start Date``, and enables us to capture the reasons that persons move between units. The data in this field should be a simple statement summarising the reason described in the source.

Person: Posting Last Cited Date
-------------------------------

**Description**

The latest date a source evidences a relationship between a person and a unit, either through direct reference in the source or by the date of its publication.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``,\ ``2012-11``, ``2012-11-23``

**Spreadsheet column name**

``person:posting_last_cited_date``

**Shortcode**

``p_plcd``

**Sources**

Yes (``person:posting_last_cited_date:source``, ``p_plcd_s``)

**Confidence**

Yes (``person:posting_last_cited_date:confidence``, ``p_plcd_c``)

**Guidance on use**

Along with the fields ``Person: Posting First Cited Date``, ``Person: First Cited Date is Start Date``, and ``Person: Posting Last Cited Date is End Date`` the field ``Person: Posting Last Cited Date`` provides data about the time period over which we can evidence a person's relationships to a unit.

The ``Person: Posting Last Cited Date`` field contains a date that is either:

-  The latest date found in the content of a source that specifically references the relationship between a person and a unit; or,
-  The latest date of publication of sources that makes reference to the relationship between a person and a unit.

    For example, if three sources published on 1 January 2012, 1 February 2012 and 1 March 2012 all refer to this person as a commander, we will use 1 March 2012 as the value in ``Person: Posting Last Cited Date``. If the source published on 1 March 2012 refers to this person as a commander on the date of 14 February 2011, we will use 14 February 2011 as the value in ``Person: Posting Last Cited Date``.

The values for ``Person: Posting Title``, ``Person: Posting Role`` and ``Person: Posting Rank`` held by a person are assumed to continue until a source indicates a change in any of those values. If the person's role, title or rank changes a new entry will need to be created to document that change. This new entry will have updated values for ``Person: Posting Last Cited Date`` and related date fields.

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included ``Person: Posting Last Cited Date`` .

This field is clarified by the field ``Person: Posting Last Cited Date is End Date`` which indicates whether the date included here is the actual date on which the relationship between a person and a unit ended.

Person: Posting Last Cited Date is End Date
-------------------------------------------

**Description**

This field indicates whether the value in ``Person : Posting Last Cited Date`` is the actual end date on which the person ceased to be a member of this unit or if it is only the date last cited for that relationship.

**Type of field**

Boolean

**Example of use**

``Y``, ``N``

**Spreadsheet column name**

``person:posting_last_cited_date_end``

**Shortcode**

``p_plcde``

**Sources**

Yes. Inherits from ``Person: Posting Last Cited Date`` (``person:posting_last_cited_date:source``, ``p_plcd_s``)

**Confidence**

Yes. Inherits from ``Person: Posting Last Cited Date`` (``person:posting_last_cited_date:confidence``, ``p_plcd_c``)

**Guidance on use**

This is a clarifying field for ``Person : Posting Last Cited Date``. One of the below values should be chosen:

-  ``Y`` indicates that the content of the source is the exact date that a relationship between a person and a unit ended.
-  ``N`` indicates that the date is not an exact end date, but the date of last citation.

Person: Context for Posting End Date
------------------------------------

**Description**

Additional information explaining why we are able to be specific about the end date of a person's specific posting to a unit. 

**Type of field**

Text

**Example of use**

``Person was promoted on this date``, ``Person retired from the army on this date``

**Spreadsheet column name**

``person:posting_first_cited_date_end_context``

**Shortcode**

``p_pfcdec``

**Sources**

Yes (``person:posting_first_cited_date_end_context:source``, ``p_pfcdec_s``)

**Confidence**

Yes (``person:posting_first_cited_date_end_context:confidence``, ``p_pfcdec_c``)

**Guidance on use**

This field is not currently in use in spreadsheets or WhoWasInCommand. 

This is a clarifying field for the ``Person: Posting Last Cited Date is Date``, and enables us to capture the reasons that persons move between units. The data in this field should be a simple statement summarising the reason described in the source.

Person: Notes
-------------

**Description**

Analysis, commentary and notes about the person that do not fit into the data structure.

**Type of field**

Text and numbers

**Example of use**

``Trained in logisitics at Fort Lackland, Texas and the air force base of Wright Patterson, Ohio.``

**Spreadsheet column name**

``person:notes:admin``

**Shortcode**

``p_n_a``

**Sources**

No

**Confidence**

No

**Guidance on use**

We use this field to record information about the person that is likely to provide useful context, additional information that does not fit into the data structure, and notes about how decisions were made about which data to include. Any sources used should be included directly inside the field.
