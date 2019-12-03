Unit Records on WhoWasInCommand
===============================

This page gives an overview of the data that visitors to WhoWasInCommand will find in a unit record.

This includes descriptions of different sections of the unit page, the data fields that are used to create it and links to more information about each field.

Unit record title area
----------------------

.. figure:: _static/org_record_anatomy_titlearea.png
   :alt: Image showing the title area of an organization record on WhoWasInCommand

   Image showing the title area of an organization record on WhoWasInCommand

This section contains key information about the identity of the unit. It also contains links to download and print actions for the displayed record. Hover over any value in the unit title area to display a little coloured circle; clicking on this will display the sources and confidence rating for each value.

**Fields used in the unit record title area**

The following fields are used in the title area:

-  :ref:`Organization: Name`
-  :ref:`Organization: Aliases`
-  :ref:`Organization: Classification`
-  :ref:`Organization: Country`

When a field is empty, it will not be displayed in the Title area.

Unit record content sidebar
---------------------------

.. figure:: _static/org_record_anatomy_content_sidebar.png
   :alt: Image showing the content sidebar of an organization record on WhoWasInCommand

   Image showing the content sidebar of an organization record on WhoWasInCommand

The content sidebar is a navigation aid. It provides quick links to different parts of the page. The items inside the content sidebar indicate what sort of data is available about this unit. For example if "Incidents" is not listed in the content sidebar, then there is no data available about incidents involving this unit.

Unit record Areas of Operation
------------------------------

.. figure:: _static/org_record_anatomy_areas_of_operation.png
   :alt: Image showing the Area of Operation map and table of a organization record on WhoWasInCommand.com

   Image showing the Area of Operation map and table of a organization record on WhoWasInCommand.com

The areas of operation section contains a map and table that describe where an organization has operated in some manner. Click on the highlighted areas of the map to display the name of an area of operation. Grab the map to drag/pan it around. Swipe or use the ``+`` and ``-`` controls on the map to zoom in or zoom out. Hover over any value in the table and a little coloured circle will appear. Click on this to view the sources and confidence rating we have assigned to that value.

**Fields used in the unit record areas of operations section**

The following fields are used in the areas of operation section:

-  :ref:`Area of Operations: OSM object name`
-  :ref:`Area of Operations: OSM object ID number`
-  :ref:`Area of Operations: Date first cited`
-  :ref:`Area of Operations: Start date?`
-  :ref:`Area of Operations: Date last cited`
-  :ref:`Area of Operations: Open-ended?`

The Areas of Operation section will display where there is a valid Area of Operations record that contains values for ``Area of Operations: OSM object name`` and ``Area of Operations: OSM object ID number``. Otherwise, the section will not display.

Unit Sites
----------

.. figure:: _static/org_record_anatomy_sites.png
   :alt: Image showing a map and table of sites - or bases - as part of an organization record on WhoWasInCommand.com

   Image showing a map and table of sites - or bases - as part of an organization record on WhoWasInCommand.com

This section contains a map and a table that describe sites associated with the organization. Clicking on the pins plotted on the map will display the name of the site. Grab the map to drag/pan it around. Swipe or use the ``+`` and ``-`` controls on the map to zoom in or zoom out. Hover over any value in the table and a little coloured circle will appear. Click on this to view the sources and confidence rating for that value.

**Fields used in the unit Sites section**

The following fields are used in the Site section:

-  :ref:`Site: Exact Location (Longitude or OSM object Name)`
-  :ref:`Site: Exact Location (Latitude or OSM object ID)`
-  :ref:`Site: Settlement (OSM object Name)`
-  :ref:`Site: Settlement (OSM object ID)`
-  :ref:`Site: Top Administrative Area (OSM object Name)`
-  :ref:`Site: Top Administrative Area (OSM object ID number)`
-  :ref:`Site: Date of first citation`
-  :ref:`Site: Founding date?`
-  :ref:`Site: Date last cited`
-  :ref:`Site: open-ended?`

The Sites section will display where there is a valid Site record. Otherwise, the section will not display on the unit record.

Unit memberships
----------------

.. figure:: _static/org_record_anatomy_memberships.png
   :alt: Image showing a membership table of a organization record on WhoWasInCommand.com

   Image showing a membership table of a organization record on WhoWasInCommand.com

This section contains a table indicating whether the organization has been a member of internal/national joint operations, international peacekeeping missions, or other multi-unit deployments. Hover over any value in the table and a little coloured circle will appear. Click on this to view the sources and confidence rating for that value.

**Fields used in the unit memberships section**

The following fields are used in the memberships section:

-  :ref:`Organization Membership`
-  :ref:`Membership: Date first cited`
-  :ref:`Membership: Start date?`
-  :ref:`Membership: Date of last citation`
-  :ref:`Membership: End date?`

Where a unit has no memberships attached to it, the memberships section will not display on the unit record.

Member units
------------

.. figure:: _static/org_record_anatomy_member_units.png
   :alt: 

This section contains a table listing the units that comprise the present unit. For example, it will list units that have taken part in a joint operation, international peacekeeping missing or other multi-unit organization. However over any value in the table, and a little coloured circle will appear. Click on this to view the sources and confidnce rating for that value.

**Fields used in the Member Units section**

The following fields are used in the member units section:

-  :ref:`Organization: Name`
-  :ref:`Organization: Aliases`
-  :ref:`Organization: Classification`
-  :ref:`Organization Membership`
-  :ref:`Membership: Date first cited`
-  :ref:`Membership: Start date?`
-  :ref:`Membership: Date of last citation`
-  :ref:`Membership: End Date?`

Parent Units
------------

.. figure:: _static/org_record_anatomy_parents.png
   :alt: Image showing a table of parent units for an organization on WhoWasInCommand.com

   Image showing a table of parent units for an organization on WhoWasInCommand.com

The parent units section displays an interactive chart. This shows the links between all units known to be above the present one in the overall organizational hierarchy of that security force, right up to the Commander in Chief or equivalent. The chart is drawn using parent relationships that are classified as ``command`` (rather than ``informal`` or ``administrative``). They are drawn at the last cited or end date of the parent relationship. This date is displayed at the bottom of the chart. Where a unit has different parents at different times, a chart is drawn for each relationship: swiping left or right, or using the arrows at each side, displays these.

**Fields used in the Parent Units section**

The following fields are used in the parent units sections:

-  :ref:`Organization: Name`
-  :ref:`Organization: Parent`
-  :ref:`Parent relationship: Classification`
-  :ref:`Parent relationship: Date first cited`
-  :ref:`Parent relationship: start date?`
-  :ref:`Parent organization: date last cited`
-  :ref:`Parent relationship: Open-ended?`

Where a unit does not have a parent relationship, this section will not be displayed in the unit record.

Unit subsidiaries
-----------------

.. figure:: _static/org_record_anatomy_subsidiaries.png
   :alt: Image showing a table of subsidiaries on an organization record on WhoWasInCommand.com

   Image showing a table of subsidiaries on an organization record on WhoWasInCommand.com

The subsidiaries section contains a table describing all units known to have been immediately below the current unit in the overall organizational hierarchy of that security force. Hover over any value in tables to display a little coloured circle; clicking on this will display the sources and confidence rating for each value.

**Fields used in the Unit subsidiaries section**

The following fields are used in the subsidiaries section:

-  :ref:`Organization: Name`
-  :ref:`Organization: Aliases`
-  :ref:`Organization: Classification`
-  :ref:`Organization: Parent`
-  :ref:`Parent relationship: Classification`
-  :ref:`Parent relationship: Date first cited`
-  :ref:`Parent relationship: start date?`
-  :ref:`Parent organization: date last cited`
-  :ref:`Parent relationship: Open-ended?`

Where a unit has no subsidaires, this section will not be displayed in the unit record.

Unit personnel
--------------

.. figure:: _static/org_record_anatomy_personnel.png
   :alt: Image of a table showing a list of personnel on an organzation record on WhoWasInCommand.com

   Image of a table showing a list of personnel on an organzation record on WhoWasInCommand.com

The personnel section displays a table showing all persons affiliated to this unit at any time in command, administrative and other roles. Hover over any value in the table to display a little coloured circle; clicking on this will display the sources and confidence rating for each value.

**Fields used in the unit personnel section**

The following fields are used in the personnel section:

-  :ref:`Person: Name`
-  :ref:`Person: Organization`
-  :ref:`Person: Role`
-  :ref:`Person: Title`
-  :ref:`Person: Rank`
-  :ref:`Person Membership: Date first cited`
-  :ref:`Person Membership: Start date`
-  :ref:`Person Membership: Context Start Date`
-  :ref:`Person Membership: Date last cited`
-  :ref:`Person Membership: End date?`

Where no persons in the dataset are members of a unit, this section will not be displayed in the unit record.

Unit incidents
--------------

.. figure:: _static/org_record_anatomy_incidents.png
   :alt: Image showing a list of incidents on an organization record on WhoWasInCommand.com

   Image showing a list of incidents on an organization record on WhoWasInCommand.com

The incidents section displays a list of incidents of alleged human rights violations that sources allege the unit has committed. Hover over either the date or the incident description to display a little coloured circle that when clicked will show the sources and confidence rating we have assigned to this data.

**Fields used in the unit incidents section**

The following fields are used in the incidents section:

-  :ref:`Event: Start date`
-  :ref:`Event: End date`
-  :ref:`Event: Description`
-  :ref:`Event: Perpetrator organization`

If a source has not made an allegation against a unit, this section will not be displayed in the unit record.

Unit record changelog
---------------------

.. figure:: _static/org_record_anatomy_changelog.png
   :alt: Image showing the changelog section that appears on organization records on WhoWasInCommand.com

   Image showing the changelog section that appears on organization records on WhoWasInCommand.com

The data displayed in any record on WhoWasInCommand is always the most up to date version. The changelog section shows when the data included in this record were first added and subsequently updated. This data is generated by the software that powers WhoWasInCommand whenever a new data import is run. Clicking on the name of the field will open a box showing all the changes that were made to a datapoint, including the time the change was made and the source used to evidence the change.
