Posting
#######

The :ref:`posting` claim type holds information about a person's career. It first defines a relationships between a :ref:`person` and a :ref:`unit`, and can be used to further describe the role the person has in the unit ("Commander", "Chief of Staff", etc.), the rank they hold at the time of the posting, and any title they may hold at the time of a posting. Usually, a :ref:`person` has a single :ref:`posting` at any one time. However, there are cases where one :ref:`person` holds more than one :ref:posting` simultaneously.

In rare instances a :ref:`person` holding multiple postings simultaneously may technically be their own superior (or conversely their own subordinate). This means they hold one :ref:`posting` in a :ref:`unit` which has a :ref:`relation` with a :ref:`relation:related_unit_classes:assertion` of ``command`` to another :ref:`unit` that the :ref:`person` also has a :ref:`posting`. For example a president of a country may also serve as the minister of defense which is subordinate to the president, technically making them their own superior (or subordinate).



Posting: Summary of claim attributes 
************************************

The table below summarizes the following dimensions of Posting claims:

 - Attribute label: a human readable label for the attribute
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the attribute
 - Key name: a standardized name that simplifies attribute use in SFM databases


.. csv-table::
   :file: _static/cluster-postings-fields.csv
   :header-rows: 1

Posting: Details of claim attributes
************************************

This section contains further information about each attribute, including descriptions, examples of use, and Guidance on use.

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

Entering ``posting`` defines the claim and defines the relevant fields to be used in further data entry about a :ref:`posting`. For quality assurance purposes, entering ``posting`` should create an error if there is any entry for fields tied to other claim types, such as :ref:`person`.


.. _posting-status-meta:

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

Claims are marked ``accepted`` when all of the data can be entered in accordance with the guidance of this handbook. The ``conflict`` flag is used whenever a claim conflicts with another claim (or claims) and a review of citations show it to be the incorrect or false claim. A :ref:`public_notes:meta <posting-public-notes>` should always accompany any ``conflict`` claim.

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

Researchers may use this field to make temporary notes or leave temporary comments intended for others in the research team about a claim. These should eventually be addressed and the field cleared by the researcher or research team. If the claim needs an explanatory note or comment to be better understood, then that should be entered in the :ref:`public_notes:meta <posting-public-notes>` field.


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

Every claim must have at least one citation to evidence the data in the claim. When two or more citations are needed to evidence a claim then a corresponding explanatory note should be entered in the :ref:`public_notes:meta <posting-public-notes>` field. This field is for the Universally Unique Identifier (UUID) for each citation, found in the ``ref:source:access_point_id:admin`` field in the Sources sheet. When multiple citations are needed every UUID should be semi-colon separated.


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

Key name
~~~~~~~~

``:claim/about-entity:ref``

Example of use
~~~~~~~~~~~~~~

``a3cb9b5e-316d-4af7-ac2b-87399df067e2``

Guidance on use
~~~~~~~~~~~~~~~

Every claim has a Universally Unique Identifier (UUID) to distinguish it from any other claim. For a ``posting`` this UUID distinguishes them from any other ``posting`` in the dataset. This allows a person to have contiguous or non-contiguous ``posting`` with the same ``unit``.

For each ``person`` their ``posting`` is always treated as contiguous, meaning it has the same UUID, unless citations establish it is non-contiguous. For example, citations establish that on 2010-08-27 Hla Min stopped being commander of the Southern Regional Military Command and became commander of the 3 Bureau of Special Operations. One citation also evidences his being commander of the 3 Bureau of Special Operations on 2011-07-05 and another citation states he retired as commander of the 3 Bureau of Special Operations on 2015-08-10. All three of these claims are treated as evidencing the same ``posting``. In contrast, the 2011-07-05 citation also establishes that Hla Min once again became commander of the Southern Regional Military Command on a temporary basis as its commander was removed from the ``posting``. This ``posting`` as commander of the Southern Regional Military Command is treated as a separate ``posting`` with a different UUID as the previous ``posting`` held on 2010-08-27.

Determining whether one person held multiple postings is based on some match of postings among different citations. For example, if one citation stated "John Alfred Smith" was commander of "Police Station 1" and another citation stated "J. Smith" was commander of "Police Station 3" there would be no match and these should be coded as two separate people each with their own ``about_entity:ref:claim``. If a third citation stated that during the career of "John Smith" he was commander of "Police Station 1", "Police station 15" and "Police Station 3" then all of these would be treated as the same person given the match of at least one ``posting`` across all citations and the similar names of the person in each citation.


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

``Ni Lin Aung Major General Triangle Regional Military Command``

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the ``about_entity:ref:claim`` which combines the various elements of the claim into a single text field. This field can be manually added by a researcher or automatically populated by the system after import.


posting:person:refs:assertion
=============================

Description
~~~~~~~~~~~

The unique 32 character code assigned to a person posted to a unit.

Attribute type
~~~~~~~~~~~~~~

String in UUID format, selected from existing person records

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:assertion/posting:person:refs``

Example of use
~~~~~~~~~~~~~~

``a848de4e-ebeb-49d6-9099-7e68ca3b57fc``

Guidance on use
~~~~~~~~~~~~~~~

This is the Universally Unique Identifier (UUID) of the ``person`` who is being posted to a ``unit``. A record for the ``person`` must already exist in the dataset. 


posting:person:names:qa
========================================

Description
~~~~~~~~~~~

Name of person posted to a unit.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is optional

Key name
~~~~~~~~

``:assertion/posting:person:refs``

Example of use
~~~~~~~~~~~~~~

``Hla Min``

Guidance on use
~~~~~~~~~~~~~~~

This is a human readable name for the ``person`` with the ``posting`` to the ``unit``. The field can be manually entered or automatically populated by the system. Best practice for this field is to use the ``name:annotation`` for the ``person``.


posting:unit:refs:assertion
======================================

Description
~~~~~~~~~~~

The unique 32 character code assigned to a unit to which the person is posted.

Attribute type
~~~~~~~~~~~~~~

String in UUID format, selected from existing unit records

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:assertion/posting:unit:refs``

Example of use
~~~~~~~~~~~~~~

``a848de4e-ebeb-49d6-9099-7e68ca3b57fc``

Guidance on use
~~~~~~~~~~~~~~~

This is the Universally Unique Identifier (UUID) of the ``unit`` to which the ``person`` is posted. A record for the ``unit`` must already exist in the dataset. 


posting:unit:names:qa
======================================

Description
~~~~~~~~~~~

Name of unit which has the posted person.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:assertion/posting:unit:refs``

Example of use
~~~~~~~~~~~~~~

``Moriones Tondo Police Station 2``, ``Northeastern Regional Military Command``

Guidance on use
~~~~~~~~~~~~~~~

This is a human readable name for the ``unit`` where the ``person`` has a ``posting``. The field can be manually entered or automatically populated by the system. Best practice for this field is to use the ``name:annotation`` for the ``unit``.


posting:roles:assertion
====================

Description
~~~~~~~~~~~

The role a person plays in the unit.

Attribute type
~~~~~~~~~~~~~~

Text string.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:assertion/posting:roles``

Example of use
~~~~~~~~~~~~~~

``Commander``, ``Chief of Staff``, ``Second in Command``

Guidance on use
~~~~~~~~~~~~~~~

The most common value we record in this attribute is ``Commander``.

There are a variety of other roles a person can have including ``Second in Command``, ``Chief of Staff`` along with other less common entries. They will vary between countries.

In nearly all cases, the value entered in this field is taken verbatim from the source. ``Commander`` is coded as the person who is ultimately in charge of the unit. If a person is referred to as “the head”, “chief” or some other variation indicating that they are in charge of a unit, they should be regarded as the ``Commander`` for the purposes of entering a value in this attribute. Similarly, the head of government or head of state of a country should have their role recorded as ``Commander`` for their ``posting``.

.. admonition:: Example

    The ``Président de la transition`` of Burkina Faso is the head of state, along with the commander-in-chief of the security forces. In our data any person who has been the ``Président de la transition`` would have a posting to that ``unit`` with a ``posting:roles:assertion`` of ``Commander`` and a ``posting:titles:assertion`` of ``Président de la transition``.

Similarly, heads of academic or other security force institutions will sometimes be referred to as the ``Commandant``. In these cases, ``Commandant`` should be recorded in the ``posting:titles:assertion`` attribute, and their ``posting:roles:assertion`` should be recorded here as ``Commander``.


posting:titles:assertion
========================

Description
~~~~~~~~~~~

A title held by a person that is separate from their rank.

Attribute type
~~~~~~~~~~~~~~

Text string.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:assertion/posting:titles``

Example of use
~~~~~~~~~~~~~~

``General Officer Commanding``, ``Jefe Del Estado Mayor``, ``Vice Chairman``

Guidance on use
~~~~~~~~~~~~~~~

The range of titles will vary from country to country. For example, commanders of army divisions in Nigeria, who usually hold the rank of ``Major General`` also hold the title of ``General Officer Commanding``. The value placed in this attribute is taken verbatim from the source and not edited or standardized.


posting:ranks:assertion
=======================

Description
~~~~~~~~~~~

The official rank of a person.

Attribute type
~~~~~~~~~~~~~~

Text string.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:assertion/posting:ranks``

Example of use
~~~~~~~~~~~~~~

``General de División``, ``Teniente Coronel``, ``Air Vice Marshal``, ``Lieutenant Colonel``

Guidance on use
~~~~~~~~~~~~~~~

Ranks for security forces are usually established in law or policy or listed on websites of security forces themselves. Best practice is to find this citation first and then use this contextual citation for any other citation referencing a rank with an abbreviation, such as "Lt. Col." for Lieutenant Colonel. In some countries ranks are refenced with a dash "-" rather than a space between words. Generally, SFM aims to avoid entering dashes or other additional punctuation into data and thus would enter ``Brigadier General`` rather than ``Brigadier-General``.


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

.. _posting-public-notes:

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

For a ``posting`` the only entry allowed for this field is ``claim``.
