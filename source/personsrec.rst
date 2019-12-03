Person records on WhoWasInCommand
=================================

This page contains an overview of the data that visitors to WhoWasInCommand will find in a person record.

This includes the different sections of the person record, the data fields that are used to create it and links to more information about each field.

Person record: title area
------------------------

.. figure:: _static/person_record_anatomy_title_area.png
   :alt: Image showing the title area of a person record on WhoWasInCommand.com

   Image showing the title area of a person record on WhoWasInCommand.com

This section contains key information about the identity of the person. It also contains links to download and print actions for the displayed record. Hover your mouse or tap any value in the title area and a little coloured circle will appear: click this to display the sources and confidence rating that we have assigned to that datapoint.

**Fields used in the person record title area**

-  :ref:`Person: Name`
-  :ref:`Person: Other Names`
-  :ref:`Person: Country`

Person record: content sidebar
-----------------------------

.. figure:: _static/person_record_anatomy_content_sidebar.png
   :alt: Image showing the content sidebar of a person record on WhoWasInCommand.com

   Image showing the content sidebar of a person record on WhoWasInCommand.com

The content sidebar is a navigation aid. It provides quick links to different sections of the person record. The items inside the content sidebar indicate what sort of data is available about this person. If a particular section is not listed in the content sidebar - for example, "Subordinates" - then there is no data available about the subordinates of this person.

Person "Last Seen As"
---------------------

.. figure:: _static/person_record_anatomy_last_seen_as.png
   :alt: Image showing the Last Seen As section of a person record on WhoWasInCommand.com

   Image showing the Last Seen As section of a person record on WhoWasInCommand.com

This section summarises the most recently-available data about a person's rank, role and membership of a unit. Hover over any value in this section and a little coloured circle will appear. Click on this to view the sources and confidence rating for that value.

**Fields used in the Person "Last Seen As" section**

The following fields are used in the Last Seen As section:

-  :ref:`Person: Posting Rank`
-  :ref:`Person: Posting to Unit`
-  :ref:`Person: Posting Role`
-  :ref:`Unit: Classification`
-  :ref:`Person: Posting Last Cited Date`
-  :ref:`Person: Posting Last Cited Date is End Date`

Person memberships
------------------

.. figure:: _static/person_record_anatomy_memberships.png
   :alt: Image showing the memberships table on a person record on WhoWasInCommand.com

   Image showing the memberships table on a person record on WhoWasInCommand.com

This section contains a table that describes the positions a person has held in different units. In this table, WhoWasInCommand will display a new membership row is displayed for each time a person changes unit, rank, role or title. This means that in some records a person may have multiple memberships in the same organization, but in different roles or at a different rank.

As with all tables in person, unit and incident records on WhoWasInCommand, hovering over or tapping any value in the table will cause a little coloured circle to appear. Clicking or tapping again on this will show the sources and confidence ratings we have assigned to that value.

**Fields used in the person memberships section**

The following fields are used in the memberships section:


-  :ref:`Person: Posting to Unit`
-  :ref:`Person: Posting Rank`
-  :ref:`Person: Posting Role`
-  :ref:`Person: Posting Title`
-  :ref:`Person: Posting First Cited Date`
-  :ref:`Person: Posting First Cited Date is Start Date`
-  :ref:`Person: Posting Last Cited Date`
-  :ref:`Person: Posting Last Cited Date is End Date`

Person record: Chain of command
-----------------------

.. figure:: _static/person_record_anatomy_chain_of_command.png
   :alt: Image showing the Chain of Command interactive chart that appear on person records on WhoWasInCommand.com

   Image showing the Chain of Command interactive chart that appear on person records on WhoWasInCommand.com

The chain of command section displays interactive charts. These show the links between all the units commanded by a person and all those superior to them, along with their commanders. The chart will display up to the highest-level unit in the unital structure, creating a "line of sight" from the current unit to the top.

The charts are drawn using parent relationships between units that are classified as ``command`` (rather than ``informal`` or ``administrative``). You can learn more about this in the documentation for :ref:`Unit: Related Unit Classification`.

The charts are drawn at the last cited or end date of the parent relationship. This date is displayed at the bottom of the chart. Where a unit has different parents at different times, a chart is drawn for each relationship: swiping left or right, or using the arrows at each side, displays these.

**Fields used in the person chain of command section**

The following fields are used in the chain of command section:

-  :ref:`Unit: Name`
-  :ref:`Unit: Related Unit`
-  :ref:`Unit: Related Unit Classification`
-  :ref:`Unit: Related Unit First Cited Date`
-  :ref:`Unit: Unit Relationship Start Date`
-  :ref:`Unit: Related Unit Last Cited Date`
-  :ref:`Unit: Related Unit is Open-Ended`
-  :ref:`Person: Name`

Person record: Superiors
------------------------

.. figure:: _static/person_record_anatomy_superiors.png
   :alt: Image showing the table of commanders of superior units that appears on a person record on WhoWasInCommand.com

   Image showing the table of commanders of superior units that appears on a person record on WhoWasInCommand.com

This section displays a table of commanders of units that were superior to any units commanded by this person, along with the duration of overlap in service that sources are able to evidence. As with all tables in person, unit and incident records, hovering over or tapping any value in the table will cause a little coloured circle to appear. Click or tap again on this to view the sources and confidence ratings we have assigned to that value.

**Fields used in the person superiors section**

The following fields are used in the superiors section:

-  :ref:`Unit: Name`
-  :ref:`Unit: Related Unit`
-  :ref:`Unit: Related Unit Classification`
-  :ref:`Unit: Related Unit First Cited Date`
-  :ref:`Unit: Unit Relationship Start Date`
-  :ref:`Unit: Related Unit Last Cited Date`
-  :ref:`Unit: Related Unit is Open-Ended`
-  :ref:`Person: Name`

The below fields are calculated from the date values in the above fields:

-  *Start of overlap*: the earliest date that the present person and a commander of an immediately superior unit served at the same time.
-  *End of overlap*: the last date that the present person and a command of an immediately superior unit served at the same time.
-  *Duration of overlap*: the number of days the present person and an immediate superior served at the same time.

Person record: Subordinates
---------------------------

.. figure:: _static/person_record_anatomy_subordinates.png
   :alt: Image showing the table of subordinate personnel that appears on person records on WhoWasInCommand.com

   Image showing the table of subordinate personnel that appears on person records on WhoWasInCommand.com

This section displays a table of commanders of units that were subordinate to any units commanded by this person. As with all tables in person, unit and incident records on WhoWasInCommand, hovering over or tapping any value in the table will cause a little coloured circle to appear. Click or tap again on this to view the sources and confidence ratings we have assigned to that value.

**Fields used in the person subordinates section**

The following fields are used in the superiors section:

-  :ref:`Unit: Name`
-  :ref:`Unit: Related Unit`
-  :ref:`Unit: Related Unit Classification`
-  :ref:`Unit: Related Unit First Cited Date`
-  :ref:`Unit: Unit Relationship Start Date`
-  :ref:`Unit: Related Unit Last Cited Date`
-  :ref:`Unit: Related Unit is Open-Ended`
-  :ref:`Person: Name`

The following fields are calculated from date values in the above fields:

-  *Start of overlap*: the earliest date that the present person and a commander of an immediately subordinate unit served at the same time.
-  *End of overlap*: the last date that the present person and a command of an immediately subordinate unit served at the same time.
-  *Duration of overlap*: the number of days the present person and an immediate superior served at the same time.
