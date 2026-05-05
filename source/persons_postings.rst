Posting
##############

The ``posting`` claim type holds information about a person's career. It first defines a relationships between a ``person`` and a ``unit``, and can be used to further describe the role the person has in the unit ("Commander", "Chief of Staff", etc), the rank they hold at the time of the posting, and any title they may hold at the time of a posting. A person usually has a single posting at any one time, but can have multiple overlapping postings. 

Posting: Summary of claim attributes 
********************************************

The table below summarises the following dimensions of Posting claims:

 - Attribute label: a human readable label for the attribute
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the attribute
 - Key name: a standardized name that simplifies attribute use in SFM databases


.. csv-table::
   :file: _static/cluster-postings-fields.csv
   :header-rows: 1

Posting: Details of claim attributes
********************************************

This section contains further information about each attribute, including descriptions, examples of use, and Guidance on use.

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

``posting``

Guidance on use
~~~~~~~~~~~~~~~

Entering `posting`` defines the claim and establishes the fields to be used in further data entry about a posting.


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

``a3cb9b5e-316d-4af7-ac2b-87399df067e2``

Guidance on use
~~~~~~~~~~~~~~~

Every claim has an Universally Unique Indentifier (UUID) to distinguish it from any other claim. For a ``posting`` this UUID distinguishes them from any other ``posting`` in the dataset. This allows a person to have contigious or non-contigous ``posting`` with the same ``unit``.

For each ``person`` their ``posting`` is always treated as a contingious, meaning it has the same UUID, unless citations establish it is non-contigious. For example, citations establish that on 2010-08-27 Hla Min stopped being commander of the Southern Regional Military Command and became commander of the 3 Bureau of Special Operations. One citation also evidences his being commander of the 3 Bureau of Special Operations on 2011-07-05 and another citation states he retired as commander of the 3 Bureau of Special Operations on 2015-08-10. All three of these claims are treated as evidencing the same ``posting``. In contrast, the 2011-07-05 citation also establishes that Hla Min once again became commander of the Southern Regional Military Command on a temporary basis as its commander was removed from the ``posting``. This ``posting`` as commander of the Southern Regional Military Command is treated as a seperate ``posting`` with a different UUID as the previous ``posting`` held on 2010-08-27.

Determining whether one person held multiple postings is based on some match of postings among different citations. For example, if one citation stated "John Alfred Smith" was commander of "Police Station 1" and another citation stated "J. Smith" was commander of "Police Station 3" there would be no match and these should be coded as two seperate people each with their own ``about_entity:ref:claim``. If then a third citation stated that during the career of "John Smith" he was commander of "Police Station 1", "Police station 15" and "Police Station 3" then all of these would be treated as the same person given the match of at least one ``posting`` across all citations and the similar names of the person in each citation.


about_entity:name:qa
====================

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

Example of use
~~~~~~~~~~~~~~

``a848de4e-ebeb-49d6-9099-7e68ca3b57fc``

Guidance on use
~~~~~~~~~~~~~~~

This is the Universally Unique Indentifier (UUID) of the person who is being posted to a unit. A record for the person must already exist in the dataset. 


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

Example of use
~~~~~~~~~~~~~~

``Hla Min``

Guidance on use
~~~~~~~~~~~~~~~

This is human readible name for the ``person`` with the ``posting`` to the ``unit``. The field can be manually entered or automatically populated by the system. Best practice for this field is to use the ``name:annotation`` for the ``person``.


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

Example of use
~~~~~~~~~~~~~~

``a848de4e-ebeb-49d6-9099-7e68ca3b57fc``

Guidance on use
~~~~~~~~~~~~~~~

This is the Universally Unique Indentifier (UUID) of the unit who is being posted to a unit. A record for the unit must already exist in the dataset. 

Guidance on use
~~~~~~~~~~~~~~~


posting:unit:names:qa
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

Example of use
~~~~~~~~~~~~~~

``a848de4e-ebeb-49d6-9099-7e68ca3b57fc``

Guidance on use
~~~~~~~~~~~~~~~

This is the Universally Unique Indentifier (UUID) of the unit who is being posted to a unit. A record for the unit must already exist in the dataset. 

Guidance on use
~~~~~~~~~~~~~~~


posting:roles:assertion
====================

Description
~~~~~~~~~~~

The role a person plays in the unit, which is not immediate apparent their rank or title.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``Commander``

Guidance on use
~~~~~~~~~~~~~~~

The most common value we record in this attribute is ``Commander``.

There are a variety of other roles a person can have including ``Second in Command``, ``Chief of Staff`` along with other less common entries. They will vary between countries.

In nearly all cases, the value placed in this attribute is taken verbatim from the source. As a special note, heads of academic or other security force institutions will sometimes be referred to as the ``Commandant``. In these cases, ``Commandant`` should be recorded in the `Person Posting: Title`_ attribute , and their role should be recorded here as ``Commander``.

If a person is referred to as “the head”, “chief” or some other variation indicating that they are in charge of a unit, they should be regarded as the ``Commander`` for the purposes of entering a value in this attribute.


posting:titles:assertion
=====================

Description
~~~~~~~~~~~

A title held by a person that is separate from their rank or role.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``General Officer Commanding``, ``Jefe Del Estado Mayor``, ``Vice Chairman``

Guidance on use
~~~~~~~~~~~~~~~

The range of titles will vary from country to country. For example, commanders of army divisions in Nigeria, who usually hold the rank of ``Major General`` also hold the title of ``General Officer Commanding``. The value placed in this attribute is taken verbatim from the source and not edited or standardized.


posting:ranks:assertion
====================

Description
~~~~~~~~~~~

The official position of a person in the hierarchy of a security force.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``General de División``, ``Teniente Coronel``, ``Air Vice Marshal``, ``Lieutenant Colonel``

Guidance on use
~~~~~~~~~~~~~~~

In most cases, the value placed in this attribute is taken verbatim from the source and not edited or standardized. In some cases, we remove any dashes from the entry.

    For example, we would enter ``Brigadier General`` rather than ``Brigadier-General``.


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

For a ``posting`` the only allowed entry for this field is ``claim``.
