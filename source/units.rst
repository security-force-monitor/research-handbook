Units
=====

What are units?
---------------

Units are official state or state-sanctioned organizations responsible for the internal or external security for a country. They include police, army, navy, air force and other security forces, as well as those civilian institutions linked to security forces through the chain of command or other linkages. Units refer to any part of the hierarchy of a security force, ranging from a national defense ministry to a police post in a small town. Units can also be groupings of other units, including joint operations, task forces or peacekeeping missions. 

Documented in this section of the handbook are field describing the following dimensions of units:

-  their existence and identity;
-  their position in the hierarchy of a security force;
-  locations of physical infrastructure like posts, bases and camps;
-  their areas of operations; and,
-  memberships in joint operations or international peacekeeping missions.

A spreadsheet containing all the fields used by Security Force Monitor can be found in the section called :ref:`Sample Data Entry Sheets`.

Unit: Unique Identifier
-----------------------

**Description**

A unique 32 character code assigned to each unit in the dataset. 

**Type of field**

Text and numbers

**Example of use**

``a407be6a-28e6-4237-b4e9-307f27b1202e``

**Spreadsheet column name**

``unit:id:admin``

**Shortcode**

``u_id_a``

**Sources**

No

**Confidence**

No

**Guidance on use**

This value is a Universally Unique Indentifier (UUID) generated using a computer program. UUIDs must be created easily using either installable or online tools, for example:

- Linux and OSX users: `uuidgen` command line tool.
- On the web: `UUID Generator <https://www.uuidgenerator.net/version>`_.

The field is administrative, providing a reliable way to differentiate between different units. In earlier versions, Security Force Monitor used ``unit:name`` to do this role but this provided inefficient as the dataset grew.

When a new unit is created directly in WhoWasInCommand, the platform automatically creates a UUID for that unit and stores it in this field. If a new unit is created in a spreadsheet, the Staff Researcher must generate a unique identifying number for that unit and copy it into the field ``unit:id:admin`` for every row associated with that specific unit. This manual, copy-and-paste step is a potential source of error and the Staff Researcher must be careful not to re-use a UUID.

Bulk updates made to WhoWasInCommand.com by spreadsheet import are based on the values in this field. For example, changes made in the row ``a407be6a-28e6-4237-b4e9-307f27b1202e`` in the spreadsheet will be applied to the unit with that UUID in WhoWasInCommand. 

Unit: Research Owner
--------------------

**Description**

Initials of Staff Reseacher who first created the unit.

**Type of field**

Text

**Example of use**

``TL``, ``TW``, ``MM``

**Spreadsheet column name**

``unit:owner:admin``

**Shortcode**

``u_own_a``

**Sources**

No

**Confidence**

No

**Guidance on use**

This field is administrative and only used where data are created using a spreadsheets. It is a simple measure to help researchers keep track of records they have created. These data are not imported into WhoWasInCommand. Instead, WhoWasInCommand keeps a record of the changes (edits, new records, deletions) by the name of the system user who made them.


Unit: Research Status
---------------------

**Description**

The place of a row of data in the research workflow.

**Type of field**

Text and numbers; controlled vocabulary.

**Example of use**

``1``, ``X``

**Spreadsheet column name**

``unit:status:admin``

**Shortcode**

``u_sta_a``

**Sources**

No

**Confidence**

No

**Guidance on use**

This administrative field is only used in spreadsheets. Staff Researchers use this field to indicate where a row of data stands in the research workflow between the first cut of a row of data, review by other researchers, and final readiness for publication. Values in this field are taken from the below controlled list:


- ``X``: Row should be deleted.
- ``0``: First commit. This row of data has just been added and needs review.
- ``1``: Fixes needed. A reviewer has made comments that need to be addressed, which will be recorded in the ``unit:comment:admin`` field.
- ``2``: Fixes made. The owner of this data has addressed the reviewer's comments.
- ``3``: Clean. A final check has been made by a reviewer, and this row of data can be published.

This field is common to all main entities in the SFM data model.

Unit: Research Comments
-----------------------

**Description**

Observations specific to the process of reviewing data in this row, including fixes, refinements and other suggestions.

**Type of field**

Text

**Example of use**

``Parent unit missing``, ``Geography needs attention``, ``Possible duplicate - merge?``

**Spreadsheet column name**

``unit:comments:admin``

**Shortcode**

``u_com_a``

**Sources**

No

**Confidence**

No

**Guidance on use**

This is an adminstrative field specific to data created in spreadsheets. Staff Researchers use it to pass on feedback about the data in the row. This may included changes needs to specific fields, references to sources that the owner of the row might look at, and other observations that can improve the quality of the data. Data in this field are not intended for publication. The comments field is common to all main entities in the SFM data model.


Unit: Name
----------

**Description**

Name of the unit.

**Type of field**

Text and numbers

**Example of use**

``3 Armoured Division``, ``3 Compañía de Infantería No Encuadrada``, ``7 Military Operations Command``

**Spreadsheet column name**

``unit:name``

**Shortcode**

``u_n``

**Sources**

Yes (``unit:name:source``, ``u_n_s``)

**Confidence**

Yes (``unit:name:confidence``, ``u_n_c``)

**Guidance on use**

As different sources will spell a unit's name in different ways the Security Force Monitor works to create a single canonical version of a unit's name based on sources and standardized to match the overall structure of and reporting about the security forces:

    Example: ``Police Divisions`` are a class of police units in Nigeria. There are over 1000 units of this type nationwide. However, each individual ``Police Division`` may not have a citation for their formal name such as Lagos Police Division, but only have a citation (or numerous citations) for the less formal ``Lagos Division``. The Monitor would list the name of the unit as ``Lagos Police Division`` with a note about the methodology behind that choice. The less formal ``Lagos Division`` name would be entered in the ``Unit: Aliases`` field (documented below).

    Example: Army units of a country may follow a naming convention of a number and then name of unit: e.g. ``3 Battalion`` or ``25 Brigade``. There may be a unit of which we only have citations for a variation on that: e.g. ``Fourth Battalion``. In this case, the Monitor would list the name of the unit as ``4 Battalion`` with a note about the methodology behind that choice. The ``Fourth Battalion`` name variant would be entered in the ``Aliases or alternative spellings`` field

Standardizations don't have specific sources, so we have created a specific source to use in these cases. Where a value in ``Unit: Name`` has been standardized, a source with the following title will be associated with it: "Name standardized in accordance with Security Force Monitor research".

Additionally, wherever possible, we will choose the most complete and complex version of a unit’s name that can be evidenced by a source:

    Example: ``3 Armoured Division`` would be the entry, rather than the more informal ``3 Division`` (which may have more citations).

The Monitor does not use ordinal indicators like ``1st`` or ``3rd`` in the name of an Unit. Instead these will be listed in the ``Unit: Other Names`` field (see below).

The Monitor uses the name in the official (local) language of the country where appropriate and/or possible.

    Example: A unit in the Mexican Army would be called by its name in Spanish (``10 Regimiento de Caballería Motorizado``), rather than the English translation ( ``10 Motorized Cavalry Regiment``).

In an effort to standardize names across all countries, the Monitor generally uses Arabic numerals in the ``Unit: Name`` field. Where warranted by sources the Monitor will use Roman numerals like ``V`` or ``XI`` instead of ``5`` or ``11`` respectively.

In cases where multiple units have the same name the Monitor will distinguish them by adding unique identifying text based on the unit's site or parent.

    Example: There are multiple "Central Police Station" formations across Nigeria, some based in the same state. To better distinguish these are separate, distinct units the Monitor added information on where the units were located to the name field for instance ``Central Police Station (Awka, Anambra State).``\ In Myanmar there have been different units through time both the name Central Regional Military Command. To distinguish them the Monitor added information on when the unit came into existence to the name: ``Central Regional Military Command (post 199)``.

Unit: Other Names
-----------------

**Description**

Other names for a unit, including aliases, alternative spellings and abbreviations.

**Type of field**

Text and numbers

**Example of use**

If ``3 Armoured Division`` is used as the canonical ``Unit: Name`` of a unit, entries in the ``Unit: Other Names`` field may include ``3 Div`` and ``Three Division``.

**Spreadsheet column name**

``unit:other_names``

**Shortcode**

``u_on``

**Sources**

Yes (``unit:other_names:source``, ``u_on_s``)

**Confidence**

Yes (``unit:other_names:confidence``, ``u_on_c``)

**Guidance on use**

Different sources will spell a unit's name in different ways. We choose and record a canonical version of a unit's name in the ``Unit: Name`` field. All other spellings that we have found are treated as aliases and stored in this field.

Although we do not use ordinal indicators like ``2nd`` or ``10/o`` in the canonical name we choose for a unit, where a source uses an Ordinal we record it as an alias.

    Example: We find a version of the unit name ``3 Armoured Division`` that has an Ordinal indicator: ``10/o. Regimiento de Caballería Motorizado.`` We would record this in the ``Unit: Other Names`` field.

Unit: Country
-------------

**Description**

ISO 3166 two letter code for the country in which a unit originates.

**Type of field**

Two letter country code

**Example of use**

``mx``, ``ug``, ``ng``

**Spreadsheet column name**

``unit:country``

**Shortcode**

``u_c``

**Sources**

Yes (``unit:country:sources``, ``u_c_s``)

**Confidence**

Yes (``unit:country:confidence``, ``u_c_c``)

**Guidance on use**

The ``Unit: Country`` field identifies the country this unit comes from. All entries in this field are two letter country codes taken from `ISO 3166 <https://www.iso.org/obp/ui/#search>`__.

    For example, a unit based in Nigeria would have the code ``ng`` and a unit based in Brazil would have the code ``br``

Unit: Classification
--------------------

**Description**

Branch of the security services that the unit a part of or general descriptor for the unit.

**Type of field**

Text and numbers

**Example of use**

``Army``, ``Ejército``, ``Police``, ``Military``, ``Military Police``, ``Joint Operation``

**Spreadsheet column name**

``unit:classification``

**Shortcode**

``u_cl``

**Sources**

Yes (``unit:classification:sources``, ``u_cl_s``)

**Confidence**

Yes (``unit:classification:confidence``, ``u_cl_c``)

**Guidance on use**

We use classifications to describe the basic nature of a specific unit and to assist investigations of potential linkages between reports of human rights abuses and the Security Force Monitor's dataset. As alleged perpetrators are usually identified in general terms of "soldiers" and "police" this field is important as a first step to understand potential linkages between units, persons and incidents. ``Unit: Classification`` values are useful supplements to ``Unit: Related Unit`` and ``Unit: Membership`` data we use to connect different units together.

The ``Unit: Classification`` field will contain a mix of standard terms and country-specific terms used to describe security force branches. In choosing terms to include in the ``Unit: Classification`` field we try to include terms that are used by country experts as well as those that are commons terms. We also try to be economical and create as few, distinct terms as possible.

    Example: a standard term we would apply to army units is ``Army``. The equivalent in Mexico would be ``Ejécito``. We would capture both terms in the ``Unit: Classification`` field.

Units may have more than one classification, usually this will be when a unit can have "generic" and "specific" classifications.

    Example: Units which are part of the army of a country may be coded as having a classification of ``Army`` as well as a classification of ``Military``, whereas units which are part of the navy of a country would have classifications of of ``Navy`` and ``Military``. For both the army and navy unit their respective classifications are correct, the army and the navy are part of the military. Critically, this enables the Monitor or users of the Monitor's data to properly analyze allegations against "soldiers" and "members of the army" in the country. In the case of "soldiers" this analysis should include every unit with the classification of ``Military`` while if there is greater specificity of "members of the army" would mean excluding any unit with the classification of ``Navy`` and focusing only on those units with a classification of ``Army.``

Unit: First Cited Date
----------------------

**Description**

The earliest date that a source shows a unit exists, either through direct reference in the source or by the date of its publication.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Spreadsheet column name**

``unit:first_cited_date``

**Shortcode**

``u_fcd``

**Sources**

Yes (``unit:first_cited_date:source``, ``u_fcd_s``)

**Confidence**

Yes (``unit:first_cited_date:confidence``, ``u_fcd_c``)

**Guidance on use**

Along with the fields ``Unit: First Cited Date is also Unit's Start Date``, ``Unit: Last Cited Date`` and ``Unit: Last Cited Date is Open-Ended`` the field ``Unit: First Cited Date`` provides data about the time period we can evidence a unit has existed.

The ``Unit: First Cited Date`` field contains a date that is either:

-  The earliest date found in a source that specifically references a unit; or,
-  The earliest date of publication of sources that make reference to a unit.

    For example, if three sources published on 1 January 2012, 1 February 2012 and 1 March 2012 all refer to 1 Motorized Brigade, we will use 1 January 2012 as the ``Unit: First Cited Date``. If the source published on 1 March 2012 refers to activity of 1 Motorized Brigade that occurred on 30 June 2011, we will use 30 June 2011 as the ``Unit: First Cited Date``.

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Unit: First Cited Date`` .

This field is clarified by the field ``Unit: First Cited Date is also Unit's Start Date`` which indicates whether the date included here is the actual date on which a unit was founded.

Unit: First Cited Date is also Unit's Start Date
------------------------------------------------

**Description**

Indicates whether the value in ``Unit: First Cited Date`` is the actual date a unit was founded.

**Type of field**

Boolean

**Example of use**

``Y``, ``N``

**Spreadsheet column name**

``unit:first_cited_date_start``

**Shortcode**

``u_fcds``

**Sources**

Yes. Inherits from ``Unit: First Cited Date`` (``unit:first_cited_date:source``, ``u_fcd_s``).

**Confidence**

Yes. Inherits from ``Unit:First Cited Date`` (``unit:first_cited_date:confidence``, ``u_fcd_c``).

**Guidance on use**

This is a clarifying field for ``Unit: First Cited Date``:

- ``Y``: used where a source references a unit and specifies the date that unit was created
- ``N``: used in all other cases, indicating that the date is not a start date but the date of first citation.

Unit: Last Cited Date
---------------------

**Description**

The most recent date for sourcing the unit's existence, either through direct reference in the source or by the date of its publication.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2013``, ``2013-12``, ``2013-12-28``

**Spreadsheet column name**

``unit:last_cited_date``

**Shortcode**

``u_lcd``

**Sources**

Yes (``unit:last_cited_date:sources``, ``u_lcd_s``)

**Confidence**

Yes (``unit:last_cited_date:confidence``, ``u_lcd_c``)

**Guidance on use**

Along with the fields ``Unit: First Cited Date``, ``Unit: First Cited Date is also Unit's Start Date`` and ``Unit: Last Cited Date is Open-Ended`` the field ``Unit: Last Cited Date`` provides data on the time period we can say a unit has existed.

The ``Unit: Last Cited Date`` field contains a date that is either:

- The latest date found in a source that specifically references a unit; or,
- The latest date of publication of sources that make reference to a unit.

    For example, if three sources published on 1 January 2012, 1 February 2012 and 1 March 2012 all refer to 1 Motorized Brigade, we will use 1 March 2012 as the ``Unit: Last Cited Date``. If the source published on 1 March 2012 refers to activity of 1 Motorized Brigade that occurred on 15 February 2012, we will use 15 February 2012 as the value in ``Unit: Last Cited Date``.

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Unit: Last Cited Date``.

This field is clarified by ``Unit: Open-ended?``, which indicates whether the date in ``Unit: Date last cited`` is the date a unit was disbanded.

Unit: Last Cited Date is Open-Ended
-----------------------------------

**Description**

Indicates whether the value in ``Unit: Last Cited Date`` the actual date on which a unit was disbanded or not.

**Type of field**

Single choice

**Example of use**

``Y``, ``N``, ``E``

**Spreadsheet column name**

``unit:last_cited_date_open``

**Shortcode**

``u_lcdo``

**Sources**

Yes. Inherits from ``Unit: Last Cited Date`` (``unit:last_cited_date:source``, ``u_lcd_s``)

**Confidence**

Yes. Inherits from ``Unit: Last Cited Date`` (``unit:last_cited_date:confidence``, ``u_lcd_c``)

**Guidance on use**

We use this field to clarify the meaning of the date entered in ``Unit: Last Cited Date``. Depending on information availalbe from sources, one of the below values should be chosen:

- ``E`` indicates the exact date this unit was disbanded, or ceases to exist.
- ``Y`` indicates that we assume this unit continues to exist.
- ``N`` indicates we do not assume that this unit continues to exist, but we do not have an exact end date.

Unit: Type of Relationship
--------------------------

**Description**

The type of relationship that exists between two units.

**Type of field**

Text and numbers; controlled vocabulary.

**Spreadsheet column name**

``unit:relation_type``

**Shortcode**

``u_rut``

**Sources**

Yes. Inherits from ``Unit: Related Unit`` (``unit:related_unit:source``, ``u_ru_s``)

**Confidence**

Yes. Inherits from ``Unit: Related Units`` (``unit:related_unit:confidence``, ``u_ru_c``)

**Guidance on use**

We use this field to define the nature of the relationship between the unit that is the subject of the row (as defined in ``Unit: Name``) and the unit noted in ``Unit: Related Unit``. The Staff Researcher must choose one of the two options below:

 - ``child``: the unit described in the row is immediately subordinate to the unit noted in ``Unit: Related Unit``.
 - ``member``: the unit described in the row is a member of the unit noted in ``Unit: Related Unit``.

The values included in this field are used to build the organizational structure of a branch of the security forces. This is discussed in more detail in the documentation below for the field ``Unit: Related Unit``.

Unit: Related Unit Unique Identifier
------------------------------------

**Description**

The UUID of the related unit.

**Type of field**

Text and numbers

**Spreadsheet column name**

``unit:related_unit_id:admin``

**Shortcode**

``u_ruid_a``

**Sources**

Yes. Inherits from ``Unit: Related Unit`` (``unit:related_unit:source``, ``u_ru_s``)

**Confidence**

Yes. Inherits from ``Unit: Related Units`` (``unit:related_unit:confidence``, ``u_ru_c``)

**Guidance on use**
 
All units referenced as relations in this cluster of "related units" fields must already have an original entry of their own. This value in this field should be the same as the value in ``unit:id:admin`` of the unit noted in ``unit:related_unit``.


Unit: Related Unit
------------------

**Description**

The immediate superior or parent unit of the current unit, or the unit to which the current unit is a member.

**Type of field**

Text and numbers

**Example of use**

``301 Artillery Regiment``

**Spreadsheet column name**

``unit:related_unit``

**Shortcode**

``u_ru``

**Sources**

Yes (``unit:related_unit:source``, ``u_ru_s``)

**Confidence**

Yes (``unit:related_unit:confidence``, ``u_ru_c``)

**Guidance on use**

``Unit: Related Unit`` and the accompanying cluster of fields is used to describe the relationships that exist between units. The SFM data model includes two types of relationship between units: "Hierarchic", and "membership".

"Hierarchic" relationships are time-bound parent-child relationships between two units that are part of the same branch of a security force. When the relationship is defined in this way,``Unit: Related Unit`` is a synonym for  "parent unit" in that it describes a unit that is “above” and distinct and separate from the present unit in some way. It also exercises authority over the "child" unit. The aggregated upwards relationships  between units form organizational structured and command chains. 

Over time, a unit may have different parents. 

    Example: In Nigeria the ``112 Task Force Battalion`` had the parent of ``7 Division Garrison`` between 12 November 2015 and 24 March 2016. The ``112 Task Force Battalion`` was then under the ``22 Task Force Brigade`` from 14 March 2017 to 26 October 2017.

Units can also have multiple parent relationships at the same time. For example, sources could indicate a unit has a formal legal parent unit while at the same time a new security body established by decree can also directly order the unit to carry out operations, establishing a second parent relationship.

"Membership" relationships indicate that a unit is member of or attached to internal/national joint operations, international peacekeeping operations, or other multi-unit efforts. Often when there is an "operation" or "joint task force", it may not have have personnel of its own. Rather, personnel from a range of different units are assigned to it. Generally, these types of arrangements don’t put the operation “above” the unit in the organizational chart. There are two circumstances in which it is appropriate to define a relationship as a "Membership". First, where multiple units operate as part of an “operation” focused on a specific mission. Second, where multiple units “lend” or otherwise deploy personnel who operate under the command of a force composition like a "Joint Task Force" or "Operation", which usually has a commander of its own.

    Example: soldiers from ``1 Division`` are deployed to the northeast of Nigeria to operate under ``Operation BOYANA``. ``1 Division`` has a commander, but the soldiers as part of ``Operation BOYANA`` likely report to and take orders from the commander of ``Operation BOYANA``. When the soldiers are done with their rotation, after several months, they return to their “home unit” ``1 Division``. So while ``Operation BOYANA`` commands some soldiers who are part of ``1 Division`` it doesn’t technically command all of the soldiers of ``1 Division`` (otherwise it would be the parent unit).

The type of relationship between units is determined by setting the value in ``unit:relation_type``, which offers two options:

 - ``child`` to define a hierarchic relationship. The unit specified in ``unit:related_unit`` is the parent of the unit in the present row.
 - ``members`` to define a membership relationship. The unit specified in the present row is a member of the unit noted in ``unit:related_unit``.


Unit: Related Unit Classification
---------------------------------

**Description**

Type of relationships that exists between two units.

**Type of field**

Controlled vocabulary, single choice

**Example of use**

``Command``, ``Administrative``, ``Informal``

**Spreadsheet column name**

``unit:related_unit_class``

**Shortcode**

``u_ruc``

**Sources**

Yes (``unit:related_unit_class:source``, ``u_ruc_s``)

**Confidence**

Yes (``unit:related_unit_class:confidence``, ``u_ruc_c``)

**Guidance on use**

Units have a ``Command`` relationship when the related parent unit can order the unit to perform some operational activity. These cover both *de jure* and *de facto* relationships between units.

``Informal`` relationships occur when there is a relationship outside of the legal or formal structure of security forces and where the exact nature of the relationship is unclear.

    Example: Lagos state in Nigeria has a security council which is a meeting of the governor, and the top commanders of police and military units in the state. The security council should be considered its own unit. By law a governor of a state is not in the chain of command for the military or police forces, but the security council membership establishes a relationship between the units and meetings often result in new approaches to security being taken, such as different deployments of police. In this case, we could make the determination that an informal relationship exists between the security council and the police and military units.

``Administrative`` relationships exist where a formal, non-command relationship exists between units, or where an administrative description is more accurate of the relationship between two units.

    Example: By law the Ministry of Defence in Nigeria provides administrative support to the Nigerian Army, establishing a relationship we could classify as ``Administrative``. The Standards Department of an Army Headquarters might be under the control of the Army Headquarters, meaning the Army Headquarters could order the Department to take some sort of action. This technically means the Department is under the “command” of the Headquarters, but the Monitor would describe this relationship as ``Administrative`` because the Department is not in the field conducting operations, it's an administrative organ of the Army Headquarters.

Unit: Related Unit First Cited Date
-----------------------------------

**Description**

The earliest date that a source evidences a relationship between units, either through direct reference in the source or by the date of its publication.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Spreadsheet column heading**

``unit:related_unit_first_cited_date``

**Shortcode**

``u_rufcd``

**Sources**

Yes (``unit:related_unit_first_cited_date:source``, ``u_rufcd_s``)

**Confidence**

Yes (``unit:related_unit_first_cited_date:confidence``, ``u_rufcd_c``)

**Guidance on use**

Along with the fields ``Unit: Unit Relationship Start Date``, ``Unit: Related Unit Last Cited Date`` and ``Unit: Related Unit is Open-Ended`` the field ``Unit: Related Unit First Cited Date`` provides data on the time period for which sources provide evidence that one unit is related to another as part of a hierarchy or as a membership.

The ``Unit: Related Unit First Cited Date`` field contains a date that is either:

-  The earliest date found in a source that specifically references a relationship; or,
-  The earliest date of publication of sources that make reference to a relationship.

    For example, if three sources published on 1 January 2012, 1 February 2012 and 1 March 2012 all say that 3 Armoured Division became the parent of 1 Motorized Brigade, we will enter 1 January 2012 in ``Unit: Related Unit First Cited Date``. If the source published on 1 March 2012 says that 3 Armoured Division became the parent of 1 Motorized Brigade on 30 June 2011, we will use 30 June 2011 as the ``Unit: Related Unit First Cited Date``.

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, such partial dates can be included in ``Unit: Related Unit First Cited Date``.

This field is clarified by the field ``Unit: Unit Relationship Start Date`` (documented below) which indicates whether the date included here is the actual date on which a unit became related to another.

Unit: Unit Relationship Start Date
----------------------------------

**Description**

Indicates whether the value in ``Unit: Related Unit First Cited Date`` is the actual date on which a unit became related to another, or the earliest date a source has referred to the relationship

**Type of field**

Boolean (Yes, No)

**Example of use**

``Y``, ``N``

**Spreadsheet column name**

``unit:related_unit_first_cited_date_start``

**Shortcode**

``u_rufcds``

**Sources**

Yes. Inherits from ``Unit: Related Unit First Cited Date`` (``unit:related_unit_first_cited_date:source``, ``u_rufcd_s``)

**Confidence**

Yes. Inherits from ``Unit: Related Unit First Cited Date`` (``unit:related_unit_first_cited_date:confidence``, ``u_rufcd_c``)

**Guidance on use**

This is a clarifying field for ``Unit: Related Unit First Cited Date``. Where a source references the hierarchic or membership relationship and specifies the date that the relationship began we will enter ``Y`` . In all other cases we will enter a value of ``N`` to indicate that the date is not a start date, but the date of first citation.

Unit: Related Unit Last Cited Date
----------------------------------

**Description**

The latest date that a source evidences a heirarchic or membership relationship, either through direct reference in the source or by the date of its publication.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Spreadheet column name**

``unit:related_unit_last_cited_date``

**Shortcode**

``u_rulcd``

**Sources**

Yes (``unit:related_unit_last_cited_date:source``, ``u_rulcd_s``)

**Confidence**

Yes (``unit:related_unit_last_cited_date:confidence``, ``u_rulcd_c``)

**Guidance on use**

Along with the fields ``Unit: Related Unit First Cited Date``, ``Unit: Unit Relationship Start Date`` and ``Unit: Related Unit is Open-Ended`` the field ``Unit: Related Unit Last Cited Date`` provides data on the time period we can evidence that one unit is related to another.

The ``Unit: Related Unit Last Cited Date`` field contains a date that is either:

-  The latest date found in a source that specifically references a relationship; or,
-  The latest date of publication of sources that make reference to a relationship.

    Example: Three sources published on 1 January 2012, 1 February 2012 and 1 March 2012 all state that the 1 Motorized Brigade is under the 3 Armoured Division (which evidences a parent relationship), we will enter 1 March 2012 in ``Unit: Related Unit Last Cited Date``.

    Example: A source published on 23 July 2017 describes actions undertaken by the 1 Motorized Brigade is under the 3 Armoured Division during riots in 2009, and another source published on 8 June 2008 states that the 1 Motorized Brigade is under the 3 Armoured Division, we would enter 2009 in ``Unit: Related Unit Last Cited Date``.

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Unit: Related Unit Last Cited Date``

    Example: A source published on 23 July 2017 describes actions undertaken by the 1 Motorized Brigade is under the 3 Armoured Division during riots in 2009, and another source published on 8 June 2008 states that the 1 Motorized Brigade is under the 3 Armoured Division, we would enter 2009 in ``Unit: Related Unit Last Cited Date``.

This field is clarified by the field ``Unit: Related Unit is Open-Ended``, which indicates whether the date included here is the actual date on which a unit stopped being related to another.

Unit: Related Unit is Open-Ended
--------------------------------

**Description**

Indicates whether or not the value in ``Unit: Related Unit Last Cited Date`` is the actual date on which the hierarchic or membership relationship ended.

**Type of field**

Single choice (Y, N, E)

**Example of use**

``Y``, ``N``, ``E``

**Spreadsheet column name**

``unit:related_unit_open``

**Shortcode**

``u_ruo``

**Sources**

Yes. Inherits from ``Unit: Related Unit Last Cited Date`` (``unit:related_unit_last_cited_date:source``, ``u_rulcd_s``)

**Confidence**

Yes. Inherits from ``Unit: Related Unit Last Cited Date`` (``unit:related_unit_last_cited_date:confidence``, ``u_rulcd_c``)

**Guidance on use**

We use this field to clarify the meaning of the date entered in ``Unit: Related Unit Last Cited Date`` One of the below values should be chosen:

-  ``E`` indicates the exact date one unit stopped being related to another.
-  ``Y`` indicates that we assume this relationship continues to exist.
-  ``N`` indicates we do not assume that this relationship continues to exist, but we do not have an exact end date.

Unit: Location Type
-------------------

**Description**

The type of Location of a unit.

**Type of field**

Text and numbers; controlled vocabulary.

**Spreadsheet column name**

``unit:location_type``

**Shortcode**

``u_loct``

**Sources**

Yes. Inherits from ``Unit: Location`` (``unit:location:source``, ``u_loc_s``)

**Confidence**

Yes. Inherits from ``Unit: Location`` (``unit:location:confidence``, ``u_loc_c``)

**Guidance on use**

This field defines the relationship between a unit and a Location. The Staff Researcher must choose one of the two options below:

 - ``site``: the Location in ``unit:location`` describes a "site", such as a settlement or specific point, at which the unit has physical infrastructure like a station, camp, base, office or other facility.
 - ``aoo``: the Location in ``unit:location`` describes an area, such as an administrative area, where the unit is known to have conducted operations or has terratorial jurisdiction.

The type of Location may be different from the way that the Location is described. For example, a small geographic area like a suburb is a *geometric area* but it could be used to describe a "site" for a unit. This is why :ref:`Locations` are defined independently of their relationship to Units and Incidents.

Unit: Base Name
---------------

**Description**

A base is a distinctively named building or complex - like a barracks or camp - where the unit is located.

**Type of field**

Text and numbers

**Example of use**

``Leopard Base``, ``Giwa Barracks``, ``Bonny Camp``

**Spreadsheet column name**

``unit:base_name```

**Shortcode**

``u_bn``

**Sources**

Yes (``unit:base_name:source``, ``u_bn_s``)

**Confidence**

Yes (``unit:base_name:confidence``, ``u_bn_c``)

**Guidance on use**

The ``Unit: Base Name`` field adds unit-specific context about a Location. This field is used to record data about units that are located in a distinctively-named building or complex.

    For example, ``3 Battalion`` in Nigeria is cited as being based in the ``Lubanga Barracks`` in ``Enugu, Enugu State, Nigeria``.

This field should not be used for anything that matches the name or alias of a unit. For example, ``North Sector Police Station`` should not be put in this field if the name of the unit is ``North Sector Police Station``.

Unit: Location
--------------

**Description**

Name of a Location where the unit has a "site" or "area of operations".

**Type of field**

Text and numbers; linked to ``location:humane_id:admin``

**Example of use**

``Ikorodu (osm, point) 93dcc4a8-8335-4a21-8372-a151c4972c54``

**Spreadsheet column name**

``unit:location``

**Shortcode**

``u_loc``

**Sources**

Yes (``unit:location:source``, ``u_loc_s``)

**Confidence**

Yes (``unit:location:confidence``, ``u_loc_c``)

**Guidance on use**

This field is used to store information about a :ref:`Location` at which the unit has infrastructure, or as operated. The value included in this field must be taken from ``location:humane_id_admin``. For further guidance on the creation, management and use of Locations visit the :ref:`Locations` documentation.


Unit: Location First Cited Date
-------------------------------

**Description**

This field captures the earliest citation date for the location of a site or area of operations, either through direct reference in the source or by the date of its publication.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Spreadsheet column name**

``unit:location_first_cited_date``

**Shortcode**

``u_sfcd``

**Sources**

Yes (``unit:location_first_cited_date:source``, ``u_locfcd_s``)

**Confidence**

Yes (``unit:location_first_cited_date:confidence``, ``u_locfcd_c``)

**Guidance on use**

Along with the fields ``Unit: Location was founded on First Cited Date``, ``Unit: Location Last Cited Date`` and ``Unit: Location Last Cited Date is Open-Ended`` the field ``Unit: Location First Cited Date`` provides data on the time period at which a unit was sited or operated in a Location.

The ``Unit: Location First Cited Date`` field contains a date that is either:

-  The earliest date found in any source that references the value contained ``Unit: Location``; or,
-  The earliest date of publication of any source that references the value contained in ``Unit: Location``.

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Unit: Location First Cited Date``.

This field is clarified by the field ``Unit: Location was Founded on First Cited Date`` which indicates whether the date included here is the actual date on which a unit site was founded.

Unit: Location was Founded on First Cited Date
----------------------------------------------

**Description**

Indicates whether or not the value in ``Unit: Location First Cited Date`` the actual date on which a unit site or area of operations was founded.

**Type of field**

Boolean (Yes, No)

**Example of use**

``Y``, ``N``

**Spreadsheet column name**

``unit:location_first_cited_date_founding``

**Shortcode**

``u_sfcdf``

**Sources**

Yes. Inherits from ``Unit: Location First Cited Date`` (``unit:location_first_cited_date:source``, ``u_locfcd_s``)

**Confidence**

Yes. Inherits from ``Unit: Location First Cited Date`` (``unit:location_first_cited_date:confidence``, ``u_locfcd_c``)

**Guidance on use**

This is a clarifying field for ``Unit: Location First Cited Date``. There are two options for use in this field:

- ``Y``: Where a source references a unit site and specifies the date that unit site was founded.
- ``N``: In all other cases, indicate that the date is not a start date, but the date of first citation.

Unit: Location Last Cited Date
------------------------------

**Description**

This field is for the latest citation for the location of a unit site or area of operations, either through direct reference in the source or by the date of its publication.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Spreadsheet column name**

``unit:location_last_cited_date``

**Shortcode**

``u_loclcd``

**Sources**

Yes (``unit:location_last_cited_date:source``, ``u_loclcd_s``)

**Confidence**

Yes (``unit:location_last_cited_date:confidence``, ``u_loclcd_c``)

**Guidance on use**

Along with the fields ``Unit: Location First Cited Date``, ``Unit: Location was founded on First Cited Date`` and ``Unit: Location Last Cited Date is Open-Ended`` the field ``Unit: Location Last Cited Date`` provides data on the time period that a unit was sited or operated at a Location.

The ``Unit: Location Last Cited Date`` field contains a date that is either:

-  The latest date found in any source that references the value contained in ``Unit: Location``; or,
-  The latest date of publication of any source that references the value contained in ``Unit: Location``.

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Unit: Location Last Cited Date``.

This field is clarified by the field ``Unit: Location Last Cited Date is Open-Ended`` which indicates whether the date included here is the actual date on which a unit was no longer sited or operating in the Location.

Unit: Location Last Cited Date is Open-Ended
--------------------------------------------

**Description**

Indicates whether the value in ``Unit: Location Last Cited Date`` is the actual date on which a unit site was disbanded, the latest date a source has referred to a unit site, and whether can we assume this unit site continues to exist.

**Type of field**

Single choice (Y, N, E)

**Example of use**

``Y``, ``N``, ``E``

**Spreadsheet column name**

``unit:location_open``

**Shortcode**

``u_loclcd_o``

**Sources**

Yes. Inherits from ``Unit: Location Last Cited Date`` (``unit:location_last_cited_date:source``, ``u_loclcd_s``)

**Confidence**

Yes. Inherits from ``Unit: Location Last Cited Date`` (``unit:location_last_cited_date:confidence``, ``u_loclcd_c``)

**Guidance on use**

We use this field to clarify the meaning of the date entered in ``Unit: Location Last Cited Date``. In entering a value for this field we use a variety of factors including: the history of basing and operations for the unit, the overall structure and nature of the security forces, and the frequency of movement of similar units.

The values that can be entered in this field are restricted to the below:

-  ``E``: indicates the exact date this unit ceased to be sited or operate in this Location.
-  ``Y``: indicates that we assume this unit  continues to be sited or operate in this Location,
-  ``N``: indicates we do not assume that this unit continues to be sited or operate in this Location, but we do not have an exact end date.

Unit: Notes
-----------

**Description**

Analysis, commentary and notes about the unit that do not fit into the data structure.

**Type of field**

Text and numbers

**Example of use**

  In March 1990 the previous Central Regional Military Command based in Taungoo was renamed Southern Regional Military Command, the previous Northwestern Regional Military Command based in Mandalay was renamed as the Central Regional Military Command and a new Northwestern Regional Military Command was created in Monywa.

**Spreadsheet column name**

``unit:notes:admin``

**Shortcode**

``u_n_a``

**Sources**

No

**Confidence**

No

**Guidance on use**

We use this field to record information about the unit that is likely to provide useful context, additional information that does not fit into the data structure, and notes about how decisions were made about which data to include. Any sources used in the note should be created as :ref:`Sources` and its access point UUID included (from ``source:access_point_id:admin``) included directly in the field.
