Organizations
=============

Organizations are official state or state-sanctioned organizations responsible for the internal or external security for a country, including police, army, navy, air force and other security forces, as well as those civilian institutions linked to security forces through the chain of command or other linkages. Organizations refer to any part of the hierarchy of a security force, ranging from a national defense ministry to a police post in a small town. We use the term "Unit" interchangeably with "Organization". Organizations can also be groupings of organizations, including joint operations, task forces or peacekeeping missions.Organizations are official state or state-sanctioned organizations responsible for the internal or external security for a country, including police, army, navy, air force and other national security bodies. Organizations refer to any part of the hierarchy of a security force, ranging from a national defense ministry to a police post in a small town. We use the term "Unit" interchangeably with "Organization". Organizations can also be groupings of organizations, including joint operations, task forces or peacekeeping missions.

Documented in this chapter are a range of different pieces of data about organizations, including:

-  their existence and identity;
-  their position in the hierarchy of a security force;
-  locations of physical infrastructure like posts, bases and camps;
-  their areas of operations; and,
-  memberships in joint operations or international peacekeeping missions.

Organization: ID
----------------

**Description**

A unique code assigned to each organization in the dataset.

**Type of field**

Text and numbers

**Example of use**

``a407be6a-28e6-4237-b4e9-307f27b1202e``

**Guidance on use**

This field is created automatically when data is uploaded into the Monitor's online platform.

Organization: Name
------------------

**Description**

Name of the organization.

**Type of field**

Text and numbers

**Example of use**

``3 Armoured Division``, ``3 Compañía de Infantería No Encuadrada``, ``7 Military Operations Command``

**Guidance on use**

As different sources will spell an organization's name in different ways the Security Force Monitor works to create a single canonical version of an organization's name based on sources and standardized to match the overall structure of and reporting about the security forces:

    Example: ``Police Divisions`` are a class of police units in Nigeria. There are over 1000 units of this type nationwide. However, each individual ``Police Division`` may not have a citation for their formal name such as Lagos Police Division, but only have a citation (or numerous citations) for the less formal ``Lagos Division``. The Monitor would list the name of the unit as ``Lagos Police Division`` with a note about the methodology behind that choice. The less formal ``Lagos Division`` name would be entered in the ``Aliases or alternative spellings`` field.

    Example: Army units of a country may follow a naming convention of a number and then name of unit: e.g. ``3 Battalion`` or ``25 Brigade``. There may be a unit of which we only have citations for a variation on that: e.g. ``Fourth Battalion``. In this case, the Monitor would list the name of the unit as ``4 Battalion`` with a note about the methodology behind that choice. The ``Fourth Battalion`` name variant would be entered in the ``Aliases or alternative spellings`` field

Additionally, wherever possible, we will choose the most complete and complex version of an organization’s name that can be evidenced by a source:

    Example: ``3 Armoured Division`` would be the entry, rather than the more informal ``3 Division`` (which may have more citations).

The Monitor does not use ordinal indicators like ``1st`` or ``3rd`` in the name of an Organization. Instead these will be listed in the ``Organization: Aliases`` field (see below).

The Monitor uses the name in the official (local) language of the country where appropriate and/or possible.

    Example: A unit in the Mexican Army would be called by its name in Spanish (``10 Regimiento de Caballería Motorizado``), rather than the English translation ( ``10 Motorized Cavalry Regiment``).

In an effort to standardize names across all countries, the Monitor generally uses Arabic numerals in the ``Organization: Name``\ field. Where warranted by sources the Monitor will use Roman numerals like ``V`` or ``XI`` instead of ``5`` or ``11`` respectively.

In cases where multiple organizations have the same name the Monitor will distinguish them by adding unique identifying text based on the organization's site or parent.

    Example: There are multiple "Central Police Station" formations across Nigeria, some based in the same state. To better distinguish these are separate, distinct units the Monitor added information on where the units were located to the name field for instance ``Central Police Station (Awka, Anambra State).``\ In Myanmar there have been different units through time both the name Central Regional Military Command. To distinguish them the Monitor added information on when the unit came into existence to the name: ``Central Regional Military Command (post 199)``.

Organization: Aliases
---------------------

**Description**

Other names for an organization, including aliases, alternative spellings and abbreviations

**Type of field**

Text and numbers

**Example of use**

If ``3 Armoured Division`` is used as the canonical ``Organization: Name`` of an organization, entries in the ``Organization: Aliases`` field may include ``3 Div`` and ``Three Division``.

**Guidance on use**

Different sources will spell an organization's name in different ways. We choose and record a canonical version of a organization's name in the ``Organization: Name`` field. All other spellings that we have found are treated as aliases and stored in this field.

Although we do not use ordinal indicators like ``2nd`` or ``10/o`` in the canonical name we choose for an organization, where a source uses an Ordinal we record it as an alias.

    Example: We find a version of the organization name ``3 Armoured Division`` that has an Ordinal indicator: ``10/o. Regimiento de Caballería Motorizado.`` We would record this in the ``Aliases`` field.

Organization: Country
---------------------

**Description**

ISO 3166 code for the country in which an organization originates

**Type of field**

Two letter country code

**Example of use**

``mx``, ``ug``, ``ng``

**Guidance on use**

The ``Organization: Country`` field identifies the country this organization comes from. All entries in this field are two letter country codes taken from `ISO 3166 which can be searched here <https://www.iso.org/obp/ui/#search>`__.

    For example, an organization based in Nigeria would have the code ``ng`` and an organization based in Brazil would have the code ``br``

Organization: Classification
----------------------------

**Description**

Branch of the security services that the organization a part of or general descriptor for the organization.

**Type of field**

Text and numbers

**Example of use**

``Army``, ``Ejército``, ``Police``, ``Military``, ``Military Police``, ``Joint Operation``

**Guidance on use**

We use classifications to describe the basic nature of a specific organization and to assist investigations of potential linkages between reports of human rights abuses and the Security Force Monitor's dataset. As alleged perpetrators are usually identified in general terms of "soldiers" and "police" this field is important as a first step to understand potential linkages between organizations, persons and incidents. ``Organization: Classification`` values are useful supplements to ``Organization: Parent`` and ``Organization: Membership`` data we use to connect different units together.

The ``Organization: Classification`` field will contain a mix of standard terms and country-specific terms used to describe security force branches. In choosing terms to include in the ``Organization: Classification`` field we try to include terms that are used by country experts as well as those that are commons terms. We also try to be economical and create as few, distinct terms as possible.

    Example: a standard term we would apply to army units is ``Army``. The equivalent in Mexico would be ``Ejécito``. We would capture both terms in the ``Organization: Classification`` field.

Organizations may have more than one classification, usually this will be when an organization can have "generic" and "specific" classifications.

    Example: Organizations which are part of the army of a country may be coded as having a classification of ``Army`` as well as a classification of ``Military``, whereas organizations which are part of the navy of a country would have classifications of of ``Navy`` and ``Military``. For both the army and navy unit their respective classifications are correct, the army and the navy are part of the military. Critically, this enables the Monitor or users of the Monitor's data to properly analyze allegations against "soldiers" and "members of the army" in the country. In the case of "soldiers" this analysis should include every unit with the classification of ``Military`` while if there is greater specificity of "members of the army" would mean excluding any organization with the classification of ``Navy`` and focusing only on those organizations with a classification of ``Army.``

Organization: Date first cited
------------------------------

**Description**

The earliest date that a source shows an organization exists, either through direct reference in the source or by the date of its publication.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Guidance on use**

Along with the fields ``Organization: Start date?``, ``Organization: Date last cited`` and ``Organization: Open-ended?`` the field ``Organization: Date first cited`` provides data about the time period we can evidence an organization has existed.

The ``Organization: Date first cited`` field contains a date that is either:

-  The earliest date found in a source that specifically references an organization; or,
-  The earliest date of publication of sources that make reference to an organization.

    For example, if three sources published on 1 January 2012, 1 February 2012 and 1 March 2012 all refer to 1 Motorized Brigade, we will use 1 January 2012 as the ``Organization: Date first cited``. If the source published on 1 March 2012 refers to activity of 1 Motorized Brigade that occurred on 30 June 2011, we will use 30 June 2011 as the ``Organization: Date first cited``.

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Organization: Date first cited`` .

This field is clarified by the field ``Organization: Start date?`` which indicates whether the date included here is the actual date on which an organization was founded.

Organization: Start date?
-------------------------

**Description**

Is the value in ``Organization: Date first cited`` the actual date on which an organization was founded (Y), or the earliest date a source has referred to an organization (N)?

**Type of field**

Boolean

**Example of use**

``Y``, ``N``

**Guidance on use**

This is a clarifying field for ``Organization: Date first cited``. Where a source references an organization and specifies the date that organization was created we will enter ``Y`` . In all other cases we will enter a value of ``N`` to indicate that the date is not a start date, but the date of first citation.

Organization: Date last cited
-----------------------------

**Description**

The most recent date for sourcing the organization's existence, either through direct reference in the source or by the date of its publication.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2013``, ``2013-12``, ``2013-12-28``

**Guidance on use**

Along with the fields ``Organization: Date first cited``, ``Organization: Start date?``\ and ``Organization: Open-ended?`` the field ``Date last cited`` provides data on the time period we can say an organization has existed.

The ``Organization: Date last cited`` field contains a date that is either:

-  The latest date found in a source that specifically references an organization; or,
-  The latest date of publication of sources that make reference to an organization.

    For example, if three sources published on 1 January 2012, 1 February 2012 and 1 March 2012 all refer to 1 Motorized Brigade, we will use 1 March 2012 as the ``Organization: Date last cited``. If the source published on 1 March 2012 refers to activity of 1 Motorized Brigade that occurred on 15 February 2012, we will use 15 February 2012 as the value in ``Organization: Date last cited``.

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Organization: Date last cited`` .

This field is clarified by ``Organization: Open-ended?``, which indicates whether the date in ``Organization: Date last cited`` is the date an organization was disbanded.

Organization: Open-ended?
-------------------------

**Description**

Is the value in ``Organization: Date last cited`` the actual date on which an organization was disbanded (E), or can we assume this organization continues to exist after this date to the present (Y), or should it not be assumed that the organization continues to exist after ``Organization: Date last cited`` because of poor sourcing or disbandment at an unclear point in time (N)?

**Type of field**

Single choice

**Example of use**

``Y``, ``N``, ``E``

**Guidance on use**

We use this field to clarify the meaning of the date entered in ``Organization: Date last cited``. One of the below values should be chosen:

-  ``E`` indicates the exact date this organization was disbanded, or ceases to exist.
-  ``Y`` indicates that we assume this organization continues to exist.
-  ``N`` indicates we do not assume that this organization continues to exist, but we do not have an exact end date.

Organization: Parent
--------------------

**Description**

The immediate superior organization in the overall hierarchy.

**Type of field**

Text and numbers

**Example of use**

``301 Artillery Regiment``

**Guidance on use**

``Organization: Parent`` describes a hierarchical, time-bound relationship between two organizations that are part of the same branch of a security force. The parent is “above” or distinct and separate from the organization in some way. Over time, an organization may have different parents.

    Example: In Nigeria the ``112 Task Force Battalion`` had the parent of a parent of ``7 Division Garrison`` between 12 November 2015 and 24 March 2016. The ``112 Task Force Battalion`` was then under the ``22 Task Force Brigade`` from 14 March 2017 to 26 October 2017.

Organizations can also have multiple parent relationships at the same time. For example, sources could indicate an organization has a formal legal parent unit while at the same time a new security body established by decree can also directly order the organization to carry out operations, establishing a second parent relationship.

In our data model ``Organization: Parent`` relationships are different from ``Organization: Membership``. Often when there is an "operation" or "joint task force", it may not have have personnel of its own. Rather, personnel from a range of different organizations are assigned to it. Generally, these types of arrangements don’t put the operation “above” the unit in the organizational chart. We outline these types of relationships using the field ``Organization: Membership``, which is documented below.

Parent relationship: Classification
-----------------------------------

**Description**

Type of relationships that exists between two organizations.

**Type of field**

Controlled vocabulary, single choice

**Example of use**

``Command, Administrative, Informal``

**Guidance on use**

Organizations have a ``Command`` relationship when the parent organization can order the organization to perform some operational activity. These cover both *de jure* and *de facto* relationships between organizations.

``Informal`` relationships occur when there is a relationship outside of the legal or formal structure of security forces and where the exact nature of the relationship is unclear.

    Example: Lagos state in Nigeria has a security council which is a meeting of the governor, and the top commanders of police and military units in the state. The security council should be considered its own organization. By law a governor of a state is not in the chain of command for the military or police forces, but the security council membership establishes a relationship between the organizations and meetings often result in new approaches to security being taken, such as different deployments of police. In this case, we could make the determination that an informal relationship exists between the security council and the police and military organizations.

``Administrative`` relationships exist where a formal, non-command relationship exists between organizations, or where an administrative description is more accurate of the relationship between two organizations.

    Example: By law the Ministry of Defence in Nigeria provides administrative support to the Nigerian Army, establishing a relationship we could classify as ``Administrative``. The Standards Department of an Army Headquarters might be under the control of the Army Headquarters, meaning the Army Headquarters could order the Department to take some sort of action. This technically means the Department is under the “command” of the Headquarters, but the Monitor would describe this relationship as ``Administrative`` because the Department is not in the field conducting operations, it's an administrative organ of the Army Headquarters.

Parent relationship: Date first cited
-------------------------------------

**Description**

The earliest date that a source shows a parent organization relationship exists, either through direct reference in the source or by the date of its publication.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Guidance on use**

Along with the fields ``Parent relationship: Start date?``, ``Parent relationship: Sate last cited`` and ``Parent relationship: Open-ended?`` the field ``Parent organization: Date first cited`` provides data on the time period we can say one organization is the parent of another .

The ``Parent organization: Date first cited`` field contains a date that is either:

-  The earliest date found in a source that specifically references a parent relationship; or,
-  The earliest date of publication of sources that make reference to a parent relationship.

    For example, if three sources published on 1 January 2012, 1 February 2012 and 1 March 2012 all say that 3 Armoured Division became the parent of 1 Motorized Brigade, we will enter 1 January 2012 in ``Parent relationship: date first cited``. If the source published on 1 March 2012 says that 3 Armoured Division became the parent of 1 Motorized Brigade on 30 June 2011, we will use 30 June 2011 as the ``Parent relationship: date first cited``.

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included ``Parent relationship: Date first cited`` .

This field is clarified by the field ``Parent relationship: Start date?`` which indicates whether the date included here is the actual date on which an organization became the parent of another.

Parent relationship: start date?
--------------------------------

**Description**

Is the value in ``Parent relationship: Date first cited`` the actual date on which an organization became the parent of another, or the earliest date a source has referred to the relationship?

**Type of field**

Boolean (Yes, No)

**Example of use**

``Y``, ``N``

**Guidance on use**

This is a clarifying field for ``Parent relationship: Date first cited``. Where a source references the parent relationship and specifies the date that the relationship began we will enter ``Y`` . In all other cases we will enter a value of ``N`` to indicate that the date is not a start date, but the date of first citation.

Parent organization: date last cited
------------------------------------

**Description**

The latest date that a source shows a parent organization relationship exists, either through direct reference in the source or by the date of its publication.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Guidance on use**

Along with the fields ``Parent relationship: Date first cited``, ``Parent relationship: Start date?`` and ``Parent relationship: Open-ended?`` the field ``Parent organization: Date last cited`` provides data on the time period we can evidence that one organization is the parent of another.

The ``Parent organization: Date last cited`` field contains a date that is either:

-  The latest date found in a source that specifically references a parent relationship; or,
-  The latest date of publication of sources that make reference to a parent relationship.

    Example: Three sources published on 1 January 2012, 1 February 2012 and 1 March 2012 all state that the 1 Motorized Brigade is under the 3 Armoured Division (which evidences a parent relationship), we will enter 1 March 2012 in ``Parent relationship: Date last cited``.

    Example: A source published on 23 July 2017 describes actions undertaken by the 1 Motorized Brigade is under the 3 Armoured Division during riots in 2009, and another source published on 8 June 2008 states that the 1 Motorized Brigade is under the 3 Armoured Division, we would enter 2009 in ``Parent relationship: Date last cited``.

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included ``Parent relationship: Date last cited`` .

    Example: A source published on 23 July 2017 describes actions undertaken by the 1 Motorized Brigade is under the 3 Armoured Division during riots in 2009, and another source published on 8 June 2008 states that the 1 Motorized Brigade is under the 3 Armoured Division, we would enter 2009 in ``Parent relationship: Date last cited``.

This field is clarified by the field ``Parent relationship: Open-ended?`` which indicates whether the date included here is the actual date on which an organization stopped being the parent of another.

Parent relationship: Open-ended?
--------------------------------

**Description**

Is the value in ``Parent relationship: Date last cited`` the actual date on which the parent relationship ended (E), or can we assume this relationship continues to exist after this date (Y), or can we not assume the relationship continues to exist after this date, but the exact end point is unknown (N)?

**Type of field**

Single choice (Y, N, E)

**Example of use**

``Y``, ``N``, ``E``

**Guidance on use**

We use this field to clarify the meaning of the date entered in ``Parent relationship: Date last cited``. One of the below values should be chosen:

-  ``E`` indicates the exact date one organization stopped being the parent of another.
-  ``Y`` indicates that we assume this parent relationship continues to exist.
-  ``N`` indicates we do not assume that this parent relationship continues to exist, but we do not have an exact end date.

Site: Base
----------

**Description**

A base is a distinctively named building or complex - like a barracks or camp - where the organization is located.

**Type of field**

Text and numbers

**Example of use**

``Leopard Base , Giwa Barracks , Bonny Camp``

**Guidance on use**

The ``Base`` field adds detail about a site. This field is used to record data about organizations that are located in a distinctively-named building or complex.

    For example, ``3 Battalion`` in Nigeria is cited as being based in the ``Lubanga Barracks`` in ``Enugu, Enugu State, Nigeria``.

This field should not be used for anything that matches the name or alias of a organization. For example, ``North Sector Police Station`` should not be put in this field if the name of the organization is ``North Sector Police Station``.

Site: Exact Location (Longitude or OSM object Name)
---------------------------------------------------

**Description**

The longitude or OSM object name of the most precise location of a site associated with this organization.

**Type of field**

First value of a latitude/longitude pair (using `EPSG:3857 <http://spatialreference.org/ref/epsg/wgs-84/>`__), or an OSM object Name.

**Example of use**

| If used to record an OSM Node Name: ``Masr Al-Gedida``
| If used to record a latitude: ``31.3280332``

**Guidance on use**

We identify ``sites`` with a number of different levels of geographical precision.

``Site: Exact Location (Longitude or OSM Object Name)`` is the first of a pair of values with ``Site: Exact Location (Latitude or OSM Object ID)``. It is used to record the most precise location of a site associated with an organization, whether this is an object (node, way or relation) on OpenStreetMap or a pair of geographical coordinates.

-  Where an object for the exact site is present on OpenStreetMap we will enter its name in this field.
-  Where no OSM object exists for the exact site a pair of coordinates will be used, the latitude value recorded in this field.

Site: Exact Location (Latitude or OSM object ID)
------------------------------------------------

**Description**

The latitude or OSM object ID number of the most precise location of a site associated with this organization.

**Type of field**

Second value of a longitude/latitude pair (using `EPSG:3857 <http://spatialreference.org/ref/epsg/wgs-84/>`__), or an OSM object ID number.

**Example of use**

| If used to record an OSM object ID number: ``452377264``
| If used to record a Longitude: ``30.09716``

**Guidance on use**

We identify ``sites`` with a number of different levels of geographical precision.

``Site: Exact Location (Latitude or OSM Object ID)`` is the second of a pair of values with ``Site: Exact Location (Longitude or OSM Object Name)``. It is used to record the most precise location of a site associated with an organization, whether this is an object (node, way or relation) on OpenStreetMap or a pair of geographical coordinates.

-  Where an object for the exact site is present on OpenStreetMap we will enter its ID number in this field.
-  Where no OSM object exists for the exact site a pair of coordinates will be used, the latitude value recorded in this field.

Site: Settlement (OSM object Name)
----------------------------------

**Description**

The city, town or village in which an organization site is based.

**Type of field**

Text, OSM object name, first in a pair of values

**Example of use**

``Tampico``, ``Francisco Escarcega``, ``Abu al Matamir``

**Guidance on use**

We identify ``sites`` with a number of different levels of geographical precision. In ``Site: Settlement (OSM Object Name)`` we record the name of the OSM object (node, way or relation) that identifies a settlement in which there is an organization site. It could be a city, town or village or other OSM object that denotes a settlement.

Site: Settlement (OSM object ID)
--------------------------------

**Description**

The city, town or village in which an organization site is based.

**Type of field**

Number, OSM object ID number, second in a pair of values

**Example of use**

``273584290``,\ ``286989920``,\ ``769127625``

**Guidance on use**

We identify ``sites`` with a number of different levels of geographical precision. In ``Site: Settlement (OSM Object ID)`` field we record the name of the OSM object (node, way or relation) ID number that identifies a settlement in which there is an organization site. It could be a city, town or village or other OSM object that denotes a settlement.

Site: Top Administrative Area (OSM object Name)
-----------------------------------------------

**Description**

The OSM name of the largest, generally used administrative area of a country (usually admin level 4).

**Type of field**

Text, OSM object name, first in a pair of values

**Example of use**

``Michoacán, Borno``

**Guidance on use**

We identify ``sites`` with a number of different levels of geographical precision. In ``Site: Top Administrative Area (OSM Object Name)`` we record the text name of highest level subnational boundary for the country in which the site is located, `as found in in OpenStreetMap <http://wiki.openstreetmap.org/wiki/Tag:boundary%3Dadministrative#Super-national_administrations>`__. Generally, these are `relations <https://wiki.openstreetmap.org/wiki/Relation>`__ in the OSM dataset tagged as administrative level 4.

    Example: Mexico has both *municipios* (administrative level 6 in OSM) and states (administrative level 4). For a ``site`` based in Mexico, we would record in ``Site: Top Administrative Area (OSM Name)`` the name of the administrative level 4 object or the state.

Site: Top Administrative Area (OSM object ID number)
----------------------------------------------------

**Description**

The OSM ID of the largest, generally used administrative area of a country (usually admin level 4).

**Type of field**

Number, OSM relation ID number, second in a pair of values

**Example of use**

``2340636``

**Guidance on use**

We identify ``sites`` with a number of different levels of geographical precision. In ``Site: Top Administrative Area (OSM Object ID number)`` we record OSM object ID number of the highest level subnational boundary for the country in which the site is located, `as found in in OpenStreetMap <http://wiki.openstreetmap.org/wiki/Tag:boundary%3Dadministrative#Super-national_administrations>`__. Generally, these are `relations <https://wiki.openstreetmap.org/wiki/Relation>`__ in the OSM dataset tagged as administrative e level 4.

    Example: Mexico has both *municipios* (administrative level 6 in OSM) and states (administrative level 4). For a ``site`` based in Mexico, we would record in ``Site: Top Administrative Area (OSM Name)`` the name of the administrative level 4 object or the state.

Site: Country
-------------

**Description**

ISO 3166 code for the country in which the organization's site is located.

**Type of field**

Two letter country code

**Example of use**

``mx``, ``ug``, ``ng``

**Guidance on use**

We identify ``sites`` with a number of different levels of geographical precision.The ``Site: Country`` field identifies the country in which an organization site is located. All entries in this field are two letter country codes taken from `ISO 3166 which can be searched here <https://www.iso.org/obp/ui/#search>`__.

    For example, an organization site located in Nigeria would have the code ``ng`` and an organization site located in Brazil would have the code ``br``.

Site: Date of first citation
----------------------------

**Description**

This field is for the earliest citation for the location of a site, either through direct reference in the source or by the date of its publication.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Guidance on use**

Along with the fields ``Site: Founding date?``, ``Site: Date last cited`` and ``Site: Open-ended?`` the field ``Site: Date first cited`` provides data on the time period for a site's location.

The ``Site: Date first cited`` field contains a date that is either:

-  The earliest date found in any source that references the values contained in the pairs of fields that record ``Site: Settlement``, or failing that, ``Site: Top Administrative area``.
-  The earliest date of publication of any source that references the values contained in the pairs of fields that record ``Site: Settlement``, or failing that, ``Site: Top Administrative area``.

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Site: Date first cited``.

This field is clarified by the field ``Site: Founding date?`` which indicates whether the date included here is the actual date on which an organization site was founded.

Site: Founding date?
--------------------

**Description**

Is the value in ``Site: Date first cited`` the actual date on which an organization site was founded (Y), or the earliest date a source has referred to an organization site (N)?

**Type of field**

Boolean (Yes, No)

**Example of use**

``Y``, ``N``

**Guidance on use**

This is a clarifying field for ``Site: Date first cited``. Where a source references an organization site and specifies the date that organization site was founded we will enter ``Y`` . In all other cases we will enter a value of ``N`` to indicate that the date is not a start date, but the date of first citation.

Site: Date last cited
---------------------

**Description**

This field is for the latest citation for the location of a site, either through direct reference in the source or by the date of its publication.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Guidance on use**

Along with the fields ``Site: Date first cited``, ``Site: Founding date?`` and ``Site is Open-ended?`` the field ``Site: Date last cited`` provides data on the time period for a site's location.

The ``Site: Date last cited`` field contains a date that is either:

-  The latest date found in any source that references the values contained in the pairs of fields that record ``Site: Settlement``, or failing that, ``Site: Top Administrative area``.
-  The latest date of publication of any source that references the values contained in the pairs of fields that record ``Site: Settlement``, or failing that, ``Site: Top Administrative area``.

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Site: Date last cited``.

This field is clarified by the field ``Site: Open-ended?`` which indicates whether the date included here is the actual date on which an organization was no longer located at this site.

Site: Open-ended?
-----------------

**Description**

Indicates whether the value in ``Site: Date last cited`` is the actual date on which an organization site was disbanded, the latest date a source has referred to an organization site, and whether can we assume this organization site continues to exist.

**Type of field**

Single choice (Y, N, E)

**Example of use**

``Y``, ``N``, ``E``

**Guidance on use**

We use this field to clarify the meaning of the date entered in ``Date last cited``. In entering a value for this field we use a variety of factors including: the history of basing for the unit, the overall structure and nature of the security forces, and the frequency of movement of similar units.

The values that can be entered in this field are restricted to the below:

-  ``E`` indicates the exact date this organization site was disbanded, or ceases to exist.
-  ``Y`` indicates that we assume this organization site continues to exist.
-  ``N`` indicates we do not assume that this organization site continues to exist, but we do not have an exact end date.

Area of Operations: OSM object name
-----------------------------------

**Description**

A geographical area in which an organization exercises jurisdiction or has operated in any manner

**Type of field**

Text and numbers, OSM object name, first in a pair of fields

**Example of use**

``Baja California Sur``, ``Kafr el-Sheikh Governorate``

**Guidance on use**

The ``Area of Operations`` fields document multiple and concurrent areas of operation of an organization. The value entered in this field is the OpenStreetMap name for the lowest-level formal geographical area that best describes where an organization has operated in some manner.

Area of Operations: OSM object ID number
----------------------------------------

**Description**

A geographical area in which an organization exercises jurisdiction or has operated in any manner

**Type of field**

Numbers, OSM object ID number, second in a pair of fields

**Example of use**

``2589611``, ``4103405``

**Guidance on use**

The ``Area of Operations`` fields document multiple and concurrent areas of operation of an organization. The value entered in this field is the OpenStreetMap object ID number for the lowest-level formal geographical area that best describes where an organization has operated in some manner.

Area of Operations: Country
---------------------------

**Description**

The country in which an Area of Operation is located.

**Type of field**

Two letter country code

**Example of use**

``mx``, ``ug``, ``ng``

**Guidance on use**

We identify ``Area of Operations`` with two different levels of geographical precision.The ``Area of Operations: Country`` field identifies the country in which an organization has operated in some manner. All entries in this field are two letter country codes taken from `ISO 3166, which can be searched here <https://www.iso.org/obp/ui/#search>`__.

Area of Operations: Date first cited
------------------------------------

**Description**

This field is for the earliest citation for an organization's ``Area of Operations``, either through direct reference in the source or by the date of its publication.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Guidance on use**

Along with the fields ``Area of Operations: Founding date?``, ``Area of Operations: Date last cited`` and ``Area of Operations: Open-ended?`` the field ``Area of Operations: Date first cited`` provides data on the time period for which can specify an organization's Area of operations.

The ``Area of Operations: Date first cited`` field contains a date that is either:

-  The earliest date found in any source that references the values contained in the pairs of fields that record ``Area of Operations``.
-  The earliest date of publication for any source that references the values contained in the pairs of fields that record ``Area of Operations``.

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Area of Operations: Date first cited``.

This field is clarified by the field ``Area of Operations: start date?`` which indicates whether the date included here is the actual date on which an Area of Operations started.

Area of Operations: Start date?
-------------------------------

**Description**

Is the value in ``Area of Operations: Date first cited`` the actual date on which an organization's Area of Operations started, or the earliest date a source has referred to an organization's Area of Operations?

**Type of field**

Boolean (Yes, No)

**Example of use**

``Y``,\ ``N``

**Guidance on use**

This is a clarifying field for ``Area of Operations: Date first cited``. Where a source references an organization site and specifies the date that organization Area of Operations was started we will enter ``Y`` . In all other cases we will enter a value of ``N`` to indicate that the date is not a start date, but the date of first citation.

Area of Operations: Date last cited
-----------------------------------

**Description**

This field is for the latest citation for an Area of Operations, either through direct reference in the source or by the date of its publication.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Guidance on use**

Along with the fields ``Area of Operations: Date first cited``, ``Area of Operations: start date?`` and ``Area of Operations: Open-ended?`` the field ``Site: Date last cited`` provides data on the time period for which can specify an Area of Operations location.

The ``Area of Operations: Date last cited`` field contains a date that is either:

-  The latest date found in any source that references the values contained in the pairs of fields that record ``Area of Operations``.
-  The latest date of publication for any source that references the values contained in the pairs of fields that record ``Area of Operations``. . In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Site: Date last cited``.

This field is clarified by the field ``Site: Open-ended?`` which indicates whether the date included here is the actual date on which an organization site was ended, or whether we have reason to assume its continued existence beyond that date.

Area of Operations: Open-ended?
-------------------------------

**Description**

Indicates whether the value in ``Area of Operations: Date last cited`` is the actual date on which an organization ended operations in the specified area, the latest date a source has referred to this Area of Operations, and whether can we assume an organization will continue to operate in an area beyond the date of last citation.

**Type of field**

Single choice from selection

**Example of use**

``Y``,\ ``N``,\ ``E``

**Guidance on use**

We use this field to clarify the meaning of the date entered in ``Area of Operations: Date last cited``. In entering a value for this field we use a variety of factors to assess whether an organization continues to operation in any manner in this area beyond the date of the last citation. These include: the history of operations of the organization, the overall structure and nature of the security forces, and the frequency of movement of similar units.

    For Example, the ``New York State police`` would likely maintain an AOO over all of ``New York State`` even if the last citation available to us was from 2015.

The values that can be entered in this field are restricted to the below:

-  ``E`` indicates the exact date an organization stops operating in the specified area.
-  ``Y`` indicates that we assume this organization continues to operation in the specified area.
-  ``N`` indicates we do not assume that this organization will continue to operate in the specified area, but we do not have an exact end date for this.

Organization Membership
-----------------------

**Description**

Internal/national joint operations, international peacekeeping operations, or other multi-unit efforts that this organization is a part of

**Type of field**

Text and numbers,.

**Example of use**

``Operación Conjunta Chihuahua``, ``Operation BOYONA``

**Guidance on use**

This field indicates whether an organization has had any memberships or attachments to internal/national joint operations, international peacekeeping operations, or other multi-unit efforts. Generally this means one of two things:

| 1) Multiple units operate as part of an “operation” focused on a specific mission.
| 2) Multiple units “lend” or otherwise deploy personnel who operate under the command of a force composition like a "Joint Task Force" or "Operation", which usually has a commander of its own.

    Example: soldiers from ``1 Division`` are deployed to the northeast of Nigeria to operate under ``Operation BOYANA``. ``1 Division`` has a commander, but the soldiers as part of ``Operation BOYANA`` likely report to and take orders from the commander of ``Operation BOYANA``. When the soldiers are done with their rotation, after several months, they return to their “home unit” ``1 Division``. So while ``Operation BOYANA`` commands some soldiers who are part of ``1 Division`` it doesn’t technically command all of the soldiers of ``1 Division`` (otherwise it would be the parent unit).

We treat task forces, operations, peacekeeping missions and anything else represented in this field as distinct organizations which must have their own record in the system.

Membership: Date first cited
----------------------------

**Description**

This field is for the earliest citation for the location of a membership, either through direct reference in the source or by the date of its publication.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Guidance on use**

Along with the fields ``Membership: Start date?``, ``Membership: Date last cited`` and ``Membership: Open-ended?`` the field ``Membership: Date first cited`` provides data on the duration of one organization's membership in another.

The ``Membership: Date first cited`` field contains a date that is either:

-  The earliest date found in any source that references the values contained in the pairs of fields that record ``Membership``
-  The earliest date of publication of any source that references the values contained in the pairs of fields that record ``Membership``. . In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Membership: Date first cited``.

This field is clarified by the field ``Membership: Founding date?`` which indicates whether the date included here is the actual date on which an organization membership was founded.

Membership: Start date?
-----------------------

**Description**

Is the value in ``Membership: Date first cited`` the actual date on which a membership was started, or the earliest date a source has referred to an organization Membership?

**Type of field**

Boolean (Yes, No)

**Example of use**

``Y``, ``N``

**Guidance on use**

This is a clarifying field for ``Membership: Date first cited``. Where a source references a membership and specifies the exact date the relationship was established we will enter ``Y`` . In all other cases we will enter a value of ``N`` to indicate that the date is not a start date, but the date of first citation.

Membership: Date of last citation
---------------------------------

**Description**

This field is for the latest citation of a membership, either through direct reference in the source or by the date of its publication.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Guidance on use**

Along with the fields ``Membership: Date first cited``, ``Membership: Start date?`` and ``Membership: End-date?`` the field ``Membership: Date last cited`` provides data on duration of a membership.

The ``Membership: Date last cited`` field contains a date that is either:

-  The latest date found in any source that references the values contained in the pairs of fields that record ``Membership``; or,
-  The latest date of publication of any source that references the values contained in the pairs of fields that record ``Membership``. . In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Membership: Date last cited``.

This field is clarified by the field ``Membership: Open-ended?`` which indicates whether the date included here is the actual date on which an organization Membership was terminated.

Membership: End Date?
---------------------

**Description**

Is the value in ``Membership: Date last cited`` the actual date on which the membership ended (Y), or the latest date a source has referred to an organizational Membership (N)?

**Type of field**

Boolean

**Example of use**

``Y``, ``N``

**Guidance on use**

We use this field to clarify the meaning of the date entered in ``Membership: Date last cited``.

The values that can be entered in this field are restricted to the below:

-  ``Y`` indicates that the membership ended on that date.
-  ``N`` indicates that the date is the date of last citation for the membership.

Organization: Notes
-------------------

**Description**

Analysis, commentary and notes about the organization that do not fit into the data structure.

**Type of field**

Text and numbers

**Example of use**

``In March 1990 the previous Central Regional Military Command based in Taungoo was renamed Southern Regional Military Command, the previous Northwestern Regional Military Command based in Mandalay was renamed as the Central Regional Military Command and a new Northwestern Regional Military Command was created in Monywa.``

**Guidance on use**

We use this field to record information about the organization that is likely to provide useful context, additional information that does not fit into the data structure, and notes about how decisions were made about which data to include. Any sources used should be referenced in the field.
