Positioning
###########

The :ref:`positioning` claim describes the geographic footprint of a specific unit. This includes the ``site`` or base of a unit, as well as the areas of operation (``aoo``) of a :ref:`unit`.

Every :ref:`positioning` should be "pushed up" to parent units or the :ref:`relation:related_unit:refs:assertion` units, which have a :ref:`relation` that overlaps any :ref:`positioning` claim for any subordinate :ref:`unit`.

.. admonition:: Example

    The Myanmar Army contains ten light infantry divisions which control battalions. A citation references the ``79 Infantry Battalion`` operating in ``Lashio Township`` on ``2020-04-24``, giving that battalion a :ref:`positioning` for ``Lashio Township`` on ``2020-04-24``. Other citations establish a :ref:`relation` between the ``79 Infantry Battalion`` and the ``99 Light Infantry Division`` before and after the :ref:`positioning` of the battalion to ``Lashio Township``. In this case, a :ref:`positioning` claim for ``99 Light Infantry Division`` operating in ``Lashio Township`` on ``2020-04-24`` should be created. The claim would be evidenced by the original citation for the ``79 Infantry Battalion`` :ref:`positioning` in ``Lashio Township``, along with all of the citations evidencing the :ref:`relation` between the ``79 Infantry Battalion`` and the ``99 Light Infantry Division``. Best practice is to add a :ref:`public_notes:meta <>` to this claim as well to explain the connection for a general audience.

Often citation will evidence a :ref:`positioning` claim for an administrative area that includes smaller administrative areas. In these cases the researcher should enter claims for all possible administrative areas to capture the full claim being made in the citation.

.. admonition:: Example

    Nigeria is divided into 36 states and a Federal Capital Territory. These are further divided into Local Government Areas. If a citation states a :ref:`unit` operates in Lagos State then claims should be entered for positionings of Lagos State as well as every Local Government Area within Lagos State.


Positioning: Summary of claim attributes
****************************************

The table below summarizes the following dimensions of :ref:`positioning` claims:

 - Attribute label: a human readable label for the attribute
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the attribute
 - Key name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-positioning-fields.csv
   :header-rows: 1


Positioning: Details of claim attributes
****************************************

This section contains further information about each attribute, including descriptions, examples of use, and guidance on use.


type:claim
==========

Description
~~~~~~~~~~~

A field that defines what type of claim is being made.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:claim/type``

Example of use
~~~~~~~~~~~~~~

``unit``, ``positioning``, ``relation``, ``person``, ``posting``, ``incident``

Guidance on use
~~~~~~~~~~~~~~~

Entering ``positioning`` defines the claim and defines the relevant fields to be used in further data entry about a ``positioning``. For quality assurance purposes, entering ``positioning`` should create an error if there is any entry for fields tied to other types of claims, such as ``unit`` or ``relation``.


status:meta
===========

Description
~~~~~~~~~~~

A field that classifies the data in the claim.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:claim/statuses``

Example of use
~~~~~~~~~~~~~~

``accepted``, ``conflict``, ``work_needed``, ``issue``

Guidance on use
~~~~~~~~~~~~~~~

Claims are marked ``accepted`` when all of the data can be entered in accordance with the guidance of this handbook. The ``conflict`` flag is used whenever a claim conflicts with another claim (or claims) and a review of citations show it to be the incorrect or false claim. A ``public_notes:meta`` should always accompany any ``conflict`` claim.

.. admonition:: Example

    Citations reference a unit 757 Light Infantry Battalion in 2008 and again in 2019 as part of the Myanmar Army. This conflicts with other citations before and after these dates which list all light infantry battalions of the army and do not include this unit. Further citations establish the general practice for  numbering army units which provides further evidence that no such battalion exists. The ``unit`` and other claims related to the 757 Light Infantry Battalion should still be entered into the dataset, flagged with ``status:meta`` of the ``conflict``, and have the status fully explained in a ``public_notes:meta``.

If the data itself cannot be brought into the SFM standard the flag ``issue`` should be used. Finally, if the current citations cannot establish whether a claim should be flagged as ``accepted`` or ``conflict`` then the flag ``work_needed`` should be used as additional research is needed.


researcher:meta
===============

Description
~~~~~~~~~~~

Field for initials or other identifier of researcher who last entered data for the claim.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:meta/researchers``

Example of use
~~~~~~~~~~~~~~

``TW``, ``Jane_Doe``, ``G1`` 

Guidance on use
~~~~~~~~~~~~~~~

Every researcher should use this field to mark the claims that they have entered. Anytime a researcher modifies any data for an existing claim they should update this field so that any questions can be directed to the right person and the flow of work can be better tracked. 


internal_comments:meta
======================

Description
~~~~~~~~~~~

A field for temporary comments or notes for the researcher or research team working on the claim.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:meta/internal-comments``

Example of use
~~~~~~~~~~~~~~

``Come back to this to determine date for claim``

Guidance on use
~~~~~~~~~~~~~~~

Researchers may use this field to make temporary notes or leave temporary comments intended for others in the research team about a claim. These should eventually be addressed and the field cleared by the researcher or research team. If the claim needs an explanatory note or comment to be better understood, then that should be entered in the :ref:`public_notes:meta <positionings-public-notes>` field.


citation:refs:claim
===================

Description
~~~~~~~~~~~

Field unique 32 character code assigned to citation(s) evidencing the claim.

Attribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:claim/citation:refs``

Example of use
~~~~~~~~~~~~~~

``69dba35b-2b70-47cf-bfda-f80225f652c6``, ``4e99308c-f9c0-49e8-b97b-14c1e7bcb99d;bedf57b2-c20b-41e3-9dcf-b7b065eaa3b7``

Guidance on use
~~~~~~~~~~~~~~~

Every claim must have at least one citation to evidence the data in the claim. When two or more citations are needed to evidence a claim then a corresponding explanatory note should be entered in the :ref:`public_notes:meta <positionings-public-notes>` field. This field is for the Universally Unique Identifier (UUID) for each citation, found in the :ref:`ref:source:access_point_id:admin` field in the Sources sheet. When multiple citations are needed every UUID should be semi-colon separated.

.. _positioning-about-entity:

about_entity:ref:claim
======================

Description
~~~~~~~~~~~

A unique 32 character code assigned to each entity in the dataset.

Attribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:claim/about-entity:ref``

Example of use
~~~~~~~~~~~~~~

``521ebf18-f161-4ac9-8c72-5a246efa0458``

Guidance on use
~~~~~~~~~~~~~~~

Every claim has a Universally Unique Identifier (UUID) to distinguish it from any other claim. For a :ref:`positioning` this UUID distinguishes it from any other :ref:`positioning` in the dataset.

Each :ref:`positioning` is always treated as a contiguous, meaning it has the same UUID, unless citations establish it is non-contiguous. 

A :ref:`positioning` should always be given the same UUID if there is an overlap or if the time-ranges of two or more citations fall within 1 day of each other. 

.. admonition:: Example

    Citations establish that the ``502 Light Infantry Battalion`` is part of a mobile formation which is deployed around Myanmar for operations, and because of this :ref:`positioning` claims should not be treated as contiguous. However, there are two different claims that the ``502 Light Infantry Battalion`` has a :ref:`positioning` ``site`` of ``Mantong Township``, one claim on ``2013-04-19`` and the other on ``2013-04-20``. Because these two claims are within a day of each other, they are coded as part of the same :ref:`positioning` giving the ``502 Light Infantry Battalion`` a :ref:`positioning` ``site`` of ``Mantong Township`` from at least ``2013-04-19`` to at least ``2013-04-20``. Another claim giving the ``502 Light Infantry Battalion`` a :ref:`positioning` ``site`` of ``Mantong Township`` on ``2014-04-20`` is coded as a separate, non-contiguous positioning because of the citations stating that the battalion is part of a mobile formation which is deployed around Myanmar for operations.


about_entity:name:qa
====================

Description
~~~~~~~~~~~

Field that provides human readable name for entity.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:claim/about-entity:ref``

Example of use
~~~~~~~~~~~~~~

``510 Light Infantry Battalion in Nansang Township``

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the :ref:`about_entity:ref:claim <positioning-about-entity>`, and combines the various elements of the claim into a single text field. This field can be manually added by a researcher or automatically populated by the system after import.


positioning:unit:refs:assertion
===============================

Description
~~~~~~~~~~~

The unique 32 character code assigned to the unit about which a relationship is described in the claim.

Attribute type
~~~~~~~~~~~~~~

String in UUID format, selected from existing unit records

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:assertion/positioning:unit:refs``

Example of use
~~~~~~~~~~~~~~

``a407be6a-28e6-4237-b4e9-307f27b1202e``

Guidance on use
~~~~~~~~~~~~~~~

The UUID entered into ``positioning:unit:refs:assertion`` must match the :ref:`about_entity:ref:claim <positioning-about-entity>` of a :ref:`unit` that already exists within the dataset.


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

Key name
~~~~~~~~

``:assertion/positioning:unit:refs``

Example of use
~~~~~~~~~~~~~~

``148 Infantry Battalion``

Guidance on use
~~~~~~~~~~~~~~~

This is human readable name for the :ref:`unit` with the :ref:`positioning`. The field can be manually entered or automatically populated by the system. Best practice for this field is to use the ``name:annotation`` for the :ref:`unit`.


positioning:types:assertion
===========================

Description
~~~~~~~~~~~

The type of location of a unit.

Attribute type
~~~~~~~~~~~~~~

String selected from controlled list

Status
~~~~~~

This attribute is optional

Key name
~~~~~~~~

``:assertion/positioning:types``

Example of use
~~~~~~~~~~~~~~

``site``, ``aoo``

Guidance on use
~~~~~~~~~~~~~~~

This field defines the relationship between a unit and a location. The Staff Researcher must choose one of the two options below:

 - ``site``: the Location describes a "site", such as a settlement or specific point, at which the unit is based.
 - ``aoo``: the Location in describes an area, such as an administrative area, where the unit is known to have conducted operations or has territorial jurisdiction.

The type of Location may be different from the way that the Location is described. For example, a small geographic area like a suburb is a *geometric area* but it could be used to describe a "site" for a unit. Locations themselves are a mix of geographical primatives - points, lines and polygons. This is why :ref:`Locations` are defined independently of their relationship to Units and Incidents.


positioning:base_names:assertion
================================

Description
~~~~~~~~~~~

A base is a distinctively named building or complex - like a barracks or camp - where the unit is located.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional

Key name
~~~~~~~~

``:assertion/positioning:base-names``

Example of use
~~~~~~~~~~~~~~

``Leopard Base``,  ``Bonny Camp``

Guidance on use
~~~~~~~~~~~~~~~

The ``positioning:base_names:assertion`` attribute adds unit-specific context about a Location. This field is used to record data about units that are located in a distinctively-named building or complex which is not found in the gazeteer, or otherwise cannot be represented as a geographic datapoint.


.. admonition:: Example

    The ``3 Battalion`` in Nigeria is cited as being based in the ``Lubanga Barracks`` in ``Enugu, Enugu State, Nigeria``.

This field should not be used for anything that matches the name or alias of a unit. For example, ``North Sector Police Station`` should not be put in this field if the name of the unit is ``North Sector Police Station``.


positioning:location:refs:assertion
===================================

Description
~~~~~~~~~~~

Unique 32 character identifier of a Location where the unit has a "site" or "area of operations".

Attribute type
~~~~~~~~~~~~~~

String in UUID format, selected from ``id:entity`` in locations sheet.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:assertion/positioning:location:refs``

Example of use
~~~~~~~~~~~~~~

``93dcc4a8-8335-4a21-8372-a151c4972c54`` (which is the raw ID for ``Ikorodu (osm, point) 93dcc4a8-8335-4a21-8372-a151c4972c54``)

Guidance on use
~~~~~~~~~~~~~~~

This attribute is used to store a reference to a location at which the unit is based, or has operated. The value included in this attribute must be selected from ``id:entity`` in the Locations sheet. For further guidance on the creation, management and use of Locations visit the :ref:`Locations` documentation.

The ``:assertion/positioning:location:refs`` should always be the location covering the largest possible area. 

.. admonition:: Example

    In Myanmar there is a region of Magway, which contains Magway District. The district contains Magway Township, and the township contains the city of Magway. If a unit is described as being based in "Magway" the ``site`` used in data entry should be Magway Region.


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

Key name
~~~~~~~~

``:assertion/positioning:location:refs``

Example of use
~~~~~~~~~~~~~~

``Hpruso Township (osm, poly) fd51e411-0a21-439c-ba3b-b6aa787541d1``

Guidance on use
~~~~~~~~~~~~~~~

The best practice for this field is to use the ``location:humane_id:qa`` of the ``positioning:location:refs:assertion``.


first_precise:range
===================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`How Dates Work`.


last_precise:range
==================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`How Dates Work`.


first_imprecise:range
=====================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`How Dates Work`.


last_imprecise:range
====================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`How Dates Work`.


starting:range
==============

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`How Dates Work`.


ending:range
============

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`How Dates Work`.


starting_context:range
======================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`How Dates Work`.


ending_context:range
====================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`How Dates Work`.

.. _positionings-public-notes:

public_notes:meta
=================

Description
~~~~~~~~~~~

Additional context or details about the claim for a public audience.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:meta/public-notes``

Example of use
~~~~~~~~~~~~~~

``Citation @3c981094-fb7b-4b78-b8f6-b525a03f72b5, published on 15 July 2019, states that numerous military appointments occurred "last week". This is understood to mean the week starting the previous Sunday 7 July 2019 through Saturday 13 July 2019.``

Guidance on use
~~~~~~~~~~~~~~~

This field should be used whenever any claim requires additional explanation because for a general reader the claim is not clearly and directly stated in the citation. In the "Example of Use" above a citation published on 15 July 2019 refers to something happening "last week" and as a result a researcher has determined the previous Sunday 7 July 2019 through Saturday 13 July 2019 should be entered into the appropriate fields of ``first_imprecise:range`` and ``last_imprecise:range``. That range would not be immediately clear to a public audience since neither date is directly referenced in the text of the citation. As a result, the researcher should explain how that date range was evidenced by the citation.


type:entity
===========

Description
~~~~~~~~~~~

Specifies the type of entity.

Attribute type
~~~~~~~~~~~~~~

Text, controlled vocabulary.

Status
~~~~~~

This field is required.

Key name
~~~~~~~~

``:entity/type``

Example of use
~~~~~~~~~~~~~~

``claim``

Guidance on use
~~~~~~~~~~~~~~~

For a :ref:`positioning` the only entry allowed for this field is ``claim``.
