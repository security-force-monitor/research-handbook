Persons
=======

Persons are natural persons who are affiliated with, or hold positions of command over a specific organization at a particular point in time.

Person: ID
----------

**Description**

A unique number for each person in the dataset.

**Type of field**

Text and numbers

**Example of use**

``a848de4e-ebeb-49d6-9099-7e68ca3b57fc``

**Guidance on use**

This field contains an automatically-generated unique identifier for each person in the Monitor’s database.

Person: Name
------------

**Description**

Full name of the person, including given, patronym and surnames.

**Type of field**

Text and numbers

**Example of use**

``Magaji Musa Majia'a``

**Guidance on use**

Different sources will spell the name of a person in different ways, so we choose a name to be a canonical entry for that person. Whenever possible, the canonical entry will contain the most complicated or complete version of a person's name, even if it has the smallest number of citations. For example ``Magaji Musa Majia'a`` will be used instead of ``Magaji Majiaa``. Other names will be placed in the ``Person: Aliases`` field (documented below).

Person: Aliases
---------------

**Description**

Other names used to identify a person.

**Type of field**

Text and numbers, free entry

**Example of use**

``Virgilio Daniel Méndez Bazan``, ``Virgilio Daniel Mendez Bazán``

**Guidance on use**

Different sources will spell a person's name in different ways. We choose and record a canonical version of a person's name in the ``Person: Name`` field. All other spellings that we have found are treated as aliases and stored in this field. This field may contain multiple values, which will be separated by a semi-colon.

Person: Country
---------------

**Description**

Country where an organization that a person is a member of is located.

**Type of field**

Text, controlled vocabulary

**Example of use**

``mx``

**Guidance on use**

Values for this field are chosen from the list of ISO 3166-1 alpha-2 codes, which can be found (`on the ISO website <https://www.iso.org/obp/ui/#search/code/>`__ and on `Wikipedia <https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Officially_assigned_code_elements>`__. This field does not denote the citizenship or country of origin of a person. Rather, it denotes where a unit they are a member of is located. For example, if ``1 Batallón de Infantería`` is located in Juarez, Mexico, the organization will be assigned a value of ``mx`` in the field ``Organization: Country``. Any person who is a member of that organization will be assigned a value of ``mx`` in the field ``Person: Country`` as well. A person may have multiple entries for ``Person: Country`` where our research shows they or an organization they are a member of is deployed to different countries.

Person: Gender
--------------

To do

**Description**

To do

**Type of field**

To do

**Example of use**

To do

**Guidance on use**

To do

Person: Date of Birth
---------------------

To do

**Description**

To do

**Type of field**

To do

**Example of use**

To do

**Guidance on use**

To do

Person: Date of Death
---------------------

To do

**Description**

To do

**Type of field**

To do

**Example of use**

To do

**Guidance on use**

To do

Person: Deceased
----------------

To do

**Description**

To do

**Type of field**

To do

**Example of use**

To do

**Guidance on use**

To do

Person: Biography
-----------------

To do

**Description**

To do

**Type of field**

To do

**Example of use**

To do

**Guidance on use**

To do

Person: External Link
---------------------

To do

**Description**

To do

**Type of field**

To do

**Example of use**

To do

**Guidance on use**

To do

Person: Organization
--------------------

**Description**

The organization that the person is a member of.

**Type of field**

Text and numbers, controlled vocabulary

**Example of use**

``35 Batallón de Infantería``

**Guidance on use**

Values in this field correspond with names of organizations that already exist in the dataset (recording in the field ``Organization: Name``. A person can have multiple memberships of the same organization if there is a change to their entries for ``Person: Rank``, ``Person: Title`` or ``Person: Role`` with respect to the organization. An example of this is where a person is promoted. Another case where a person can have multiple membership of the same organization is where research indicates there are clear start or end dates to a membership. An example of where this might occur is if a person does multiples "tours" in a particular organization.

Person: Role
------------

**Description**

The role a person plays in the organization that is not evident from entries in ``Person: Title`` or ``Person: Rank``.

**Type of field**

Text and numbers, controlled vocabulary

**Example of use**

``Commander``

**Guidance on use**

The most common value we record in ``Person: Role`` is ``Commander``.

There are a variety of other roles a person can have including ``Second in Command``, ``Chief of Staff`` along with other less common entries. They will vary between countries.

As a special note, heads of academic or other security force institutions will sometimes be referred to as the ``Commandant``. In these cases, ``Commandant`` should be recorded in the ``Title`` field, and their role should be recorded as ``Commander``.

If a person is referred to as “the head”, “chief” or some other variation indicating that they are in charge of a unit, they should be regarded as the ``Commander``.

Person: Title
-------------

**Description**

A title held by a person that is separate from their rank or role.

**Type of field**

Text and numbers, free entry

**Example of use**

``General Officer Commanding``, ``Jefe Del Estado Mayor``

**Guidance on use**

The range of titles will vary from country to country. For example, commanders of army divisions in Nigeria, who usually hold the rank of ``Major General`` also hold the title of ``General Officer Commanding``.

Person: Rank
------------

**Description**

The official position of a person in the hierarchy of a security force.

**Type of field**

Text and numbers, free entry

**Example of use**

``General de División``, ``Teniente Coronel``, ``Air Vice Marshal``

**Guidance on use**

We remove any dashes that are contained in ``Person: Rank`` values.

    For example, we would enter ``Brigadier General`` rather than ``Brigadier-General``.

Person Membership: Date first cited
-----------------------------------

**Description**

The earliest date a source evidences a relationship between a person and an organization, either through direct reference in the source or by the date of its publication.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Guidance on use**

Along with the fields ``Person membership: Start date?``, ``Person Membership: Date last cited`` and ``Person Membership: Open-ended?`` the field ``Person Memberships: Date first cited`` provides data about the time period over which we can evidence a person's relationships to an organization

The ``Person Membership: Date first cited`` field contains a date that is either:

-  The earliest date found in the content of a source that specifically references the relationship between a person and an organization; or,
-  The earliest date of publication of sources that makes reference to the relationship between a person and an organization.

    For example, if three sources published on 1 January 2012, 1 February 2012 and 1 March 2012 all refer to this person as a commander, we will use 1 January 2012 as the value in ``Person Membership: Date first cited``. If the source published on 1 March 2012 refers to this person as a commander on the date of 30 June 2011, we will use 30 June 2011 as the value in ``Person Membership: Date first cited``.

The values for ``Person: Title``, ``Person: Role`` and ``Person: Rank`` held by a person are assumed to continue until a source indicates a change in any of those values. If the person's role, title or rank changes a new entry will need to be created to document that change. This new entry will have updated values for ``Person Membership: Date first cited`` and related date fields.

    For example, if a source indicates that Major General Jack Johnson is the commander of 1 Division as of 2007-08-20 all of the relevant fields would be entered based on that source. If another source states that Jack Johnson retired from the 1 Division on 2008-01-10 the last citation for Jack Johnson's affiliation would be 2008-01-10. However, this would also assume that Jack Johnson continued to have the Role of Commander and the Rank of Major General from 2007-08-20 until 2008-01-10.

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Person Membership: Date first cited``.

This field is clarified by the field ``Person Membership: Start date?`` which indicates whether the date included here is the actual date on which the relationship between a person and an organization started.

Person Membership: Start date
-----------------------------

**Description**

Indicates whether the value in ``Person Membership: Date first cited`` is the actual date on which a person became a member of this organization, or the earliest date a source has referred to the relationship.

**Type of field**

Boolean, Y/N

**Example of use**

``Y``, ``N``

**Guidance on use**

This is a clarifying field for ``Person Membership: Date first cited``.

Where the content of the source has indicated the exact date that a relationship between a person and an organization began we will enter ``Y`` . In all other cases we will enter a value of ``N`` to indicate that the date is not a start date, but the date of first citation.

Person Membership: Context Start Date
-------------------------------------

**Description**

**Type of field**

**Example of use**

**Guidance on use**

Person Membership: Date last cited
----------------------------------

**Description**

The latest date a source evidences a relationship between a person and an organization, either through direct reference in the source or by the date of its publication.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``,\ ``2012-11``, ``2012-11-23``

**Guidance on use**

Along with the fields ``Person Membership: Date first cited``, ``Person Membership: Start date?`` and ``Person Membership: Open-ended?`` the field ``Person Memberships: Date last cited`` provides data about the time period over which we can evidence a person's relationships to an organization

The ``Person Membership: Date last cited`` field contains a date that is either:

-  The latest date found in the content of a source that specifically references the relationship between a person and an organization; or,
-  The latest date of publication of sources that makes reference to the relationship between a person and an organization.

    For example, if three sources published on 1 January 2012, 1 February 2012 and 1 March 2012 all refer to this person as a commander, we will use 1 March 2012 as the value in ``Person Membership: Date last cited``. If the source published on 1 March 2012 refers to this person as a commander on the date of 14 February 2011, we will use 14 February 2011 as the value in ``Person Membership: Date last cited``.

The values for ``Person: Title``, ``Person: Role`` and ``Person: Rank`` held by a person are assumed to continue until a source indicates a change in any of those values. If the person's role, title or rank changes a new entry will need to be created to document that change. This new entry will have updated values for ``Person Membership: Date last cited`` and related date fields.

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included ``Person Membership: Date last cited`` .

This field is clarified by the field ``Person Membership: Open-ended?`` which indicates whether the date included here is the actual date on which the relationship between a person and an organization ended.

Person Membership: End date?
----------------------------

**Description**

This field indicates whether the value in ``Person Membership: Date last cited`` is the actual end date on which the person ceased to be a member of this organization or if it is only the date last cited for that relationship.

**Type of field**

Single choice, (Y, N)

**Example of use**

``Y``,\ ``N``

**Guidance on use**

This is a clarifying field for ``Person Membership: Date last cited``. One of the below values should be chosen:

-  ``Y`` indicates that the content of the source is the exact date that a relationship between a person and an organization ended.
-  ``N`` indicates that the date is not an exact end date, but the date of last citation.

Person Membership: Context End Date
-----------------------------------

**Description**

**Type of field**

**Example of use**

**Guidance on use**

Person: Notes
-------------

**Description**

Analysis, commentary and notes about the person that do not fit into the data structure.

**Type of field**

Text and numbers

**Example of use**

``Trained in logisitics at Fort Lackland, Texas and the air force base of Wright Patterson, Ohio.``

**Guidance on use**

We use this field to record information about the organization that is likely to provide useful context, additional information that does not fit into the data structure, and notes about how decisions were made about which data to include. Any sources used should be included inside the field.
