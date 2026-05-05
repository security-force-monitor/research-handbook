Positioning
###########

The ``positioning`` claim describes the geographic footprint of a specific unit. This includes the site or base of a unit, as well as the areas of operation of a unit.

Positioning: Summary of claim attributes
*********************************************

The table below summarises the following dimensions of ``positioning`` claims:

 - Attribute label: a human readable label for the attribute
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the attribute
 - Key name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-positioning-fields.csv
   :header-rows: 1


Positioning: Details of claim attributes
*********************************************

This section contains further information about each attribute, including descriptions, examples of use, and guidance on use.


type:claim
==================================

Description
~~~~~~~~~~~

A field that defines what type of claim is being made.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``positioning``

Guidance on use
~~~~~~~~~~~~~~~

Entering ``positioning`` defines the claim and establishes the fields to be used in further data entry about a positioning.


status:meta
==================================

Description
~~~~~~~~~~~

A field that classifies the data in the claim.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``accepted``, ``conflict``, ``work_needed``

Guidance on use
~~~~~~~~~~~~~~~

Claims are marked ``accepted`` when all of the data can be entered in accordance with the guidance of this handbook. The ``conflict`` flag is used whenever a claim conflicts with another claim (or claims) and a review of citations show it to be the incorrect or false claim. For example, XYZ. Finally, if the data cannot be correctly entered or no citations can establish whether a claim should be flagged as ``accepted`` or ``conflict`` then the flag ``work_needed`` should be used. This allows the researcher to either fix the issue or conduct additional research.


researcher:meta
==================================

Description
~~~~~~~~~~~

Field for initials or other identifer of researcher who last entered data for the claim.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``TW``

Guidance on use
~~~~~~~~~~~~~~~

Every researcher should use this field to mark the claims that they have entered. Anytime a researcher modifies any data for an existing claim they should update this field so that any questions can be directed to the right person and the flow of work can be better tracked. 


internal_comments:meta
==================================

Description
~~~~~~~~~~~

A field for temporary comments or notes for the researcher or research team working on the claim.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``Come back to this to determine date for claim``

Guidance on use
~~~~~~~~~~~~~~~

Researchers may use this field to make temporary notes or leave temporary comments intended for others in the research team about a claim. These should eventually be addressed and the field cleared by the researcher or research team. If the claim needs an explanatory note or comment to be better understood then that should be entered in the ``public_notes:meta`` field.


citation:refs:claim
==================================

Description
~~~~~~~~~~~

Field unique 32 character code assigned to citation(s) evidencing the claim.

Attribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``69dba35b-2b70-47cf-bfda-f80225f652c6``, ``4e99308c-f9c0-49e8-b97b-14c1e7bcb99d;bedf57b2-c20b-41e3-9dcf-b7b065eaa3b7``

Guidance on use
~~~~~~~~~~~~~~~

Every claim must have at least one citation to evidence the data in the claim. When two or more citations are needed to evidence a claim then a corresponding explanatory note should be entered in the ``public_notes:meta`` field. This field is for the Universally Unique Indentifier (UUID) for each citation, found in the ``ref:source:access_point_id:admin`` field in the Sources sheet. When multiple citations are needed every UUID should be semi-colon seperated.


about_entity:ref:claim
==================================

Description
~~~~~~~~~~~

A unique 32 character code assigned to each entity in the dataset.

Attribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``521ebf18-f161-4ac9-8c72-5a246efa0458``

Guidance on use
~~~~~~~~~~~~~~~

Every claim has an Universally Unique Indentifier (UUID) to distinguish it from any other claim. For a ``positioning`` this UUID distinguishes it from any other ``positioning`` in the dataset.

For each ``person`` their ``posting`` is always treated as a contingious, meaning it has the same UUID, unless citations establish it is non-contigious. 

.. admonition:: Example

    For example, citations establish that on 2010-08-27 Hla Min stopped being commander of the Southern Regional Military Command and became commander of the 3 Bureau of Special Operations. One citation also evidences his being commander of the 3 Bureau of Special Operations on 2011-07-05 and another citation states he retired as commander of the 3 Bureau of Special Operations on 2015-08-10. All three of these claims are treated as evidencing the same ``posting``. In contrast, the 2011-07-05 citation also establishes that Hla Min once again became commander of the Southern Regional Military Command on a temporary basis as its commander was removed from the ``posting``. This ``posting`` as commander of the Southern Regional Military Command is treated as a seperate ``posting`` with a different UUID as the previous ``posting`` held on 2010-08-27.

A ``positioning`` should always be given the same UUID if there is an overlap or if the time-ranges of two or more citations fall within 1 day of each other. 

.. admonition:: Example

    Citations establish that the ``502 Light Infantry Battalion`` is part of a mobile formation which is deployed around Myanmar for operations, and because of this ``positioning`` claims should not be treated as contigious. However, there are two different claims that the ``502 Light Infantry Battalion`` has a ``postioning`` ``site`` of ``Mantong Township``, one claim on ``2013-04-19`` and the other on ``2013-04-20``. Because these two claims are within a day of each other, they are coded as part of the same ``positioning`` giving the ``502 Light Infantry Battalion`` a ``postioning`` ``site`` of ``Mantong Township`` from at least ``2013-04-19`` to at least ``2013-04-20``. Another claim giving the ``502 Light Infantry Battalion`` a ``postioning`` ``site`` of ``Mantong Township`` on ``2014-04-20`` is coded as a seperate, non-contigious positioning because of the citations stating that the battalion is part of a mobile formation which is deployed around Myanmar for operations.


about_entity:name:qa
==================================

Description
~~~~~~~~~~~

Field that provides human readible name for entity.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``510 Light Infantry Battalion in Nansang Township``

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the ``about_entity:ref:claim``, and combines the various elements of the claim into a single text field. This field can be manually added by a researcher or automatically populated by the system after import.


positioning:unit:refs:assertion
=================================

Attribute name
~~~~~~~~~~~~~~

``::positioning:unit:id``

Description
~~~~~~~~~~~

The unique 32 character code assigned to the unit about which a relationship is described in the claim.

Atrribute type
~~~~~~~~~~~~~~

String in UUID format, selected from existing unit records

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``a407be6a-28e6-4237-b4e9-307f27b1202e``

Guidance on use
~~~~~~~~~~~~~~~

The UUID inputted into ``::positioning:unit:id`` must match the ``about_entity:ref:claim`` of a ``unit`` that already exists within the dataset.


positioning:unit:names:qa
=========================

Description
~~~~~~~~~~~

Name of the unit with the positioning.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is optional

Example of use
~~~~~~~~~~~~~~

``148 Infantry Battalion``

Guidance on use
~~~~~~~~~~~~~~~

This is human readible name for the ``unit`` with the ``positioning``. The field can be manually entered or automatically populated by the system. Best practice for this field is to use the ``name:annotation`` for the ``unit``.


positioning:types:assertion
===========================

Attribute name
~~~~~~~~~~~~~~

``::positioning:type``

Description
~~~~~~~~~~~

The type of location of a unit.

Attribute type
~~~~~~~~~~~~~~

String selected from controlled list

Status
~~~~~~

This attribute is optional

Guidance on use
~~~~~~~~~~~~~~~

This field defines the relationship between a unit and a location. The Staff Researcher must choose one of the two options below:

 - ``site``: the Locationdescribes a "site", such as a settlement or specific point, at which the unit has physical infrastructure like a station, camp, base, office or other facility.
 - ``aoo``: the Location in describes an area, such as an administrative area, where the unit is known to have conducted operations or has terratorial jurisdiction.

The type of Location may be different from the way that the Location is described. For example, a small geographic area like a suburb is a *geometric area* but it could be used to describe a "site" for a unit. Locations themselves are a mix of geographical primatives - points, lines and polygons. This is why :ref:`Locations` are defined independently of their relationship to Units and Incidents.


positioning:base_names:assertion
================================

Attribute name
~~~~~~~~~~~~~~

``::positioning:base_name``

Description
~~~~~~~~~~~

A base is a distinctively named building or complex - like a barracks or camp - where the unit is located.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional

Example of use
~~~~~~~~~~~~~~

``Leopard Base``,  ``Bonny Camp``

Guidance on use
~~~~~~~~~~~~~~~

The `Unit Positioning: Base Name`_ attribute adds unit-specific context about a Location. This field is used to record data about units that are located in a distinctively-named building or complex which is not found in the fazeteer, or otherwise cannot be represented as a geographic datapoint.

    For example, ``3 Battalion`` in Nigeria is cited as being based in the ``Lubanga Barracks`` in ``Enugu, Enugu State, Nigeria``.

This field should not be used for anything that matches the name or alias of a unit. For example, ``North Sector Police Station`` should not be put in this field if the name of the unit is ``North Sector Police Station``.


positioning:location:refs:assertion
===================================

Attribute name
~~~~~~~~~~~~~~

``::positioning:location:id``

Description
~~~~~~~~~~~

Unique 32 character identifier  of a Location where the unit has a "site" or "area of operations".

Attribute type
~~~~~~~~~~~~~~

String in UUID format, selected from ``::location:id``

Status
~~~~~~

This attribute is optional

Example of use
~~~~~~~~~~~~~~

``93dcc4a8-8335-4a21-8372-a151c4972c54`` (which is the raw ID for ``Ikorodu (osm, point) 93dcc4a8-8335-4a21-8372-a151c4972c54``)

Guidance on use
~~~~~~~~~~~~~~~

This attribute is used to store a reference to a location at which the unit has infrastructure, or has operated. The value included in this attributemust be selected from ``::location:id``. For further guidance on the creation, management and use of Locations visit the :ref:`Locations` documentation.


positioning:location:names:qa
=============================

Description
~~~~~~~~~~~

Name of the location.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is optional

Example of use
~~~~~~~~~~~~~~

``Hpruso Township (osm, poly) fd51e411-0a21-439c-ba3b-b6aa787541d1``

Guidance on use
~~~~~~~~~~~~~~~

The best practice for this field is to use the ``location:humane_id:qa`` of the ``incident:location:refs:assertion``.


first_precise:range
======================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


last_precise:range
====================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


first_imprecise:range
========================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


last_imprecise:range
======================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


starting:range
===========================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


ending:range
==========================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


starting_context:range
==========================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


ending_context:range
==========================================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


public_notes:meta
============================

Description
~~~~~~~~~~~

Additional context or details about the claim for a public audience.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.


Example of use
~~~~~~~~~~~~~~

``Citation @3c981094-fb7b-4b78-b8f6-b525a03f72b5, published on 15 July 2019, states that numerous military appointments occurred "last week". This is understood to mean the week starting the previous Sunday 7 July 2019 through Saturday 13 July 2019.``

Guidance on use
~~~~~~~~~~~~~~~

This field should be used whenever any claim requires additional explanation because for a general reader the claim is not clearly and directly stated in the citation. For the example of use above a citation published on 15 July 2019 refers to something happening "last week" and as a result a researcher has determined the previous Sunday 7 July 2019 through Saturday 13 July 2019 should be entered into the appropriate fields of ``first_imprecise:range`` and ``last_imprecise:range``. That range would not be immediately clear to a public auidence since neither date is directly referenced in the text of the citation. As a result the researcher should explain how that date range was evidenced by the citation.


type:entity
====================================

Description
~~~~~~~~~~~

Specifies the type of entity.

Attribute type
~~~~~~~~~~~~~~

Text, controlled vocabulary

Status
~~~~~~

This field is required.

Example of use
~~~~~~~~~~~~~~

``claim``

Guidance on use
~~~~~~~~~~~~~~~

For a ``positioning`` the only allowed entry for this field is ``claim``.
