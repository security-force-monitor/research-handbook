Training
########

.. warning::

   Draft documentation. The format described in this documentation is a proposed format which may change with further research and development.

Trainings are training and assistance intervention provided bilaterally by a state or by a multilateral security actor like the European Union to the security or defense forces of another state. 


Training: Summary of claim attributes 
*************************************

The table below is a draft summarizing the following dimensions of a proposed training claim type:

 - Attribute label: a human readable label for the attribute
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the attribute
 - Key name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-training.csv
   :header-rows: 1

Training: details of claim attributes
*************************************

This section will contain further information about each attribute, including descriptions, examples of use, and guidance on use.


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

``training``

Guidance on use
~~~~~~~~~~~~~~~

Entering ``training`` defines the claim and defines the relevant fields to be used in further data entry about a :ref:`training`. For quality assurance purposes, any other entry should create an error.


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

Claims are marked ``accepted`` when all of the data can be entered in accordance with the guidance of this handbook. The ``conflict`` flag is used whenever a claim conflicts with another claim (or claims) and a review of citations show it to be the incorrect or false claim (see :ref:`Citations with both Accepted and Conflicted Information` for guidance when one claim from a citation contains both ``accepted`` and ``conflict`` information). A :ref:`public_notes:meta <training-public-notes>` should always accompany any ``conflict`` claim.

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

Researchers may use this field to make temporary notes or leave temporary comments intended for others in the research team about a claim. These should eventually be addressed and the field cleared by the researcher or research team. If the claim needs an explanatory note or comment to be better understood, then that should be entered in the :ref:`public_notes:meta <training-public-notes>` field.

.. _training-citation:

citation:refs:claim
===================

Description
~~~~~~~~~~~

Field unique 32-character code assigned to citation(s) evidencing the claim.

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

Every claim must have at least one citation to evidence the data in the claim. When two or more citations are needed to evidence a claim then a corresponding explanatory note should be entered in the :ref:`public_notes:meta <training-public-notes>` field. This field is for the Universally Unique Identifier (UUID) for each citation, found in the :ref:`source:access_point_id:admin` field in the Sources sheet. When multiple citations are needed every UUID should be semi-colon separated.

.. _training-about-entity:

about_entity:ref:claim
======================

Description
~~~~~~~~~~~

A unique 32-character code assigned to each entity in the dataset.

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

Every entity has a Universally Unique Identifier (UUID) to distinguish it from any other entity. For a :ref:`training` this UUID distinguishes them from any other :ref:`training` in the dataset.


about_entity:name:qa
====================

Description
~~~~~~~~~~~

Field that provides human readable name for claim.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a

Example of use
~~~~~~~~~~~~~~

n/a - proposed field

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the :ref:`about_entity:ref:claim <training-about-entity>` which combines the various elements of the claim into a single text field. This field can be manually added by a researcher or automatically populated by the system after import.


training:program:refs:assertion
===============================

Description
~~~~~~~~~~~

The name of program which the :ref:`training:course:refs:assertion` is part.

Attribute type
~~~~~~~~~~~~~~

Text string.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed field

Example of use
~~~~~~~~~~~~~~

n/a - proposed field

Guidance on use
~~~~~~~~~~~~~~~

The name of the program should be entered as stated from the citation. Future development may require this field to be updated as a separate claim to allow for standardized names of programs.


training:course:refs:assertion
==============================

Description
~~~~~~~~~~~

The name of the specific training course.

Attribute type
~~~~~~~~~~~~~~

Text string.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed field

Example of use
~~~~~~~~~~~~~~

n/a - proposed field

Guidance on use
~~~~~~~~~~~~~~~

The name of the course should be entered as stated from the citation. Future development may require this field to be updated as a separate claim to allow for standardized names of courses.


training:trainer_unit:refs:assertion
====================================

Description
~~~~~~~~~~~

The unique 32-character code of the unit providing the training.

Attribute type
~~~~~~~~~~~~~~

String in UUID format.

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

n/a - proposed field

Example of use
~~~~~~~~~~~~~~

n/a - proposed field

Guidance on use
~~~~~~~~~~~~~~~

The Universally Unique Identifier (UUID) used must be for a :ref:`unit` which already exists in the dataset.


training:trainer_unit:names:qa
==============================

Description
~~~~~~~~~~~

The human readable name of the unit providing the training.

Attribute type
~~~~~~~~~~~~~~

Text string.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed field

Example of use
~~~~~~~~~~~~~~

n/a - proposed field

Guidance on use
~~~~~~~~~~~~~~~

This is human readable name for the :ref:`training:trainer_unit:refs:assertion`. The field can be manually entered or automatically populated by the system. Best practice for this field is to use the :ref:`name:annotation <unit-name-annotation>` for the :ref:`unit`.


training:trainer_country:annotation
===================================

Description
~~~~~~~~~~~

Country or entity providing training, used for grouping claims.

Attribute type
~~~~~~~~~~~~~~

Text, controlled vocabulary.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed

Example of use
~~~~~~~~~~~~~~

n/a - proposed

Guidance on use
~~~~~~~~~~~~~~~

Values for this field are chosen from the list of ISO 3166-1 alpha-2 codes, which can be found `on the ISO website <https://www.iso.org/obp/ui/#search>`_. This field is used to aid grouping trainings into datasets related to specific countries and does not denote the country of origin of a unit. The specific country code should be chosen based the :ref:`citation:refs:claim <training-citation>`.


training:recepient_unit:refs:assertion
======================================

Description
~~~~~~~~~~~

The unique 32-character code of the unit receiving the training.

Attribute type
~~~~~~~~~~~~~~

String in UUID format.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed field

Example of use
~~~~~~~~~~~~~~

n/a - proposed field

Guidance on use
~~~~~~~~~~~~~~~

The Universally Unique Identifier (UUID) used must be for a :ref:`unit` which already exists in the dataset.


training:recipent_unit:names:qa
===============================

Description
~~~~~~~~~~~

The human readable name of the unit receiving the training.

Attribute type
~~~~~~~~~~~~~~

Text string.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed field

Example of use
~~~~~~~~~~~~~~

n/a - proposed field

Guidance on use
~~~~~~~~~~~~~~~

This is human readable name for the :ref:`training:recepient_unit:refs:assertion`. The field can be manually entered or automatically populated by the system. Best practice for this field is to use the :ref:`name:annotation <unit-name-annotation>` for the :ref:`unit`.


training:recipient:classifications:assertion
============================================

Description
~~~~~~~~~~~~~~

A general descriptor of trainees, often matches a branch or branches of the security forces.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed field

Example of use
~~~~~~~~~~~~~~

n/a - proposed field

Guidance on use
~~~~~~~~~~~~~~~

Sometimes a citation will report general information about the trainee. For example, rather than state a unit or a specific person the citation might include something generic like “soldiers” or “police". In these cases we use the same methodology used assign a :ref:`training:recipient:classifications:assertion` to assign a :ref:`unit:classifications:assertion`. The list of possible entries used in :ref:`training:recipient:classifications:assertion` is the same for :ref:`unit:classifications:assertion`.


training:recipient_country:annotation
=====================================

Description
~~~~~~~~~~~

Traget country for training, used for grouping claims.

Attribute type
~~~~~~~~~~~~~~

Text, controlled vocabulary.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:annotation/country``

Example of use
~~~~~~~~~~~~~~

``mx``

Guidance on use
~~~~~~~~~~~~~~~

Values for this field are chosen from the list of ISO 3166-1 alpha-2 codes, which can be found `on the ISO website <https://www.iso.org/obp/ui/#search>`_. This field is used to aid grouping trainings into datasets related to specific countries and does not denote the country of origin of a unit. The specific country code should be chosen based the target country for the :ref:`training` as specified in the citation, or any related :ref:`positioning` the :ref:`training:recepient_unit:refs:assertion` holds, or any other contextual information from citations about the :ref:`training:recepient_unit:refs:assertion`.


training:location:descriptions:assertion
========================================

Description
~~~~~~~~~~~

A textual description of a location which cannot be represented in data, copied directly from the citation.

Attribute type
~~~~~~~~~~~~~~

Text string.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed field

Example of use
~~~~~~~~~~~~~~

n/a - proposed field

Guidance on use
~~~~~~~~~~~~~~~

We use this attribute to record the place a :ref:`training` occurred, exactly as described in the citation.


training:location:refs:assertion
================================

Description
~~~~~~~~~~~~~~

The unique identifier of a location, drawn from the data on existing locations

Attribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed field

Example of use
~~~~~~~~~~~~~~

``4d7d97a6-d85e-436b-9511-81e8d55ceff3``(the identifier for the location``Baga (osm, point) 4d7d97a6-d85e-436b-9511-81e8d55ceff3``)

Guidance on use
~~~~~~~~~~~~~~~

This field is used to store information about the :ref:`location` where the training occurred. The value included in this field must be taken from :ref:`id:entity` attribute from the location dataset. For further guidance on the creation, management and use of locations visit the :ref:`location` documentation.


training:location:names:qa
==========================

Description
~~~~~~~~~~~~~~

Human readable name for location.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed field

Example of use
~~~~~~~~~~~~~~

``Hpruso Township (osm, poly) fd51e411-0a21-439c-ba3b-b6aa787541d1``

Guidance on use
~~~~~~~~~~~~~~~

The best practice for this field is to use the :ref:`location:humane_id:qa` of the :ref:`training:location:refs:assertion`.


training:quanity:assertion
==========================

Description
~~~~~~~~~~~~~~

Number of trainees for the training.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed field

Example of use
~~~~~~~~~~~~~~

``300``

Guidance on use
~~~~~~~~~~~~~~~

If the citation reports the number of attendees or number of persons trained, it should be entered in this field.


training:cost:assertion
=======================

Description
~~~~~~~~~~~~~~

Cost of trainings.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed field

Example of use
~~~~~~~~~~~~~~

``17856``

Guidance on use
~~~~~~~~~~~~~~~

If citations report the total cost of the training, it should be entered in this field.


training:cost_currency:assertion
================================

Description
~~~~~~~~~~~

Associated currency of the country or supranational entity providing the training.

Attribute type
~~~~~~~~~~~~~~

Text, controlled vocabulary.

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

n/a - proposed

Example of use
~~~~~~~~~~~~~~

n/a - proposed

Guidance on use
~~~~~~~~~~~~~~~

Values for this field are chosen from the list of ISO 3166-1 alpha-2 codes, which can be found `on the ISO website <https://www.iso.org/obp/ui/#search>`_.


first_precise:range
===================

Description
~~~~~~~~~~~

The first precise date in the range.

Type of attribute
~~~~~~~~~~~~~~~~~

String-date

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:range-precise/first``

Example of use
~~~~~~~~~~~~~~

n/a - proposed

Guidance on use
~~~~~~~~~~~~~~~

Guidance on dates can be found in the section :ref:`How Dates Work`.


last_precise:range
==================

Description
~~~~~~~~~~~

The last precise date in the range.

Type of attribute
~~~~~~~~~~~~~~~~~

String-date

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:range-precise/last``

Example of use
~~~~~~~~~~~~~~

n/a - proposed

Guidance on use
~~~~~~~~~~~~~~~

Guidance on dates can be found in the section :ref:`How Dates Work`.


first_imprecise:range
=====================

Description
~~~~~~~~~~~

The first imprecise date in the range.

Type of attribute
~~~~~~~~~~~~~~~~~

String-date

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:range-imprecise/first``

Example of use
~~~~~~~~~~~~~~

n/a - proposed

Guidance on use
~~~~~~~~~~~~~~~

Guidance on dates can be found in the section :ref:`How Dates Work`.


last_imprecise:range
====================

Description
~~~~~~~~~~~

The last imprecise date in the range.

Type of attribute
~~~~~~~~~~~~~~~~~

String-date

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:range-imprecise/last``

Example of use
~~~~~~~~~~~~~~

n/a - proposed

Guidance on use
~~~~~~~~~~~~~~~

Guidance on dates can be found in the section :ref:`How Dates Work`.


starting:range
==============

Description
~~~~~~~~~~~

Flag for if first date in range is the start date or not.

Type of attribute
~~~~~~~~~~~~~~~~~

Y/N boolean

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:range/starting?``

Example of use
~~~~~~~~~~~~~~

n/a - proposed

Guidance on use
~~~~~~~~~~~~~~~

Guidance on dates can be found in the section :ref:`How Dates Work`.


ending:range
============

Description
~~~~~~~~~~~

Flag for if last date in range is the start date or not.

Type of attribute
~~~~~~~~~~~~~~~~~

Y/N boolean

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:range/ending?``

Example of use
~~~~~~~~~~~~~~

n/a - proposed

Guidance on use
~~~~~~~~~~~~~~~

Guidance on dates can be found in the section :ref:`How Dates Work`.


starting_context:range
======================

Description
~~~~~~~~~~~

Simple description of start date.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:range/starting-context``

Example of use
~~~~~~~~~~~~~~

n/a - proposed

Guidance on use
~~~~~~~~~~~~~~~

Guidance on dates can be found in the section :ref:`How Dates Work`.


ending_context:range
====================

Description
~~~~~~~~~~~

Simple description of end date.

Type of attribute
~~~~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:range/ending-context``

Example of use
~~~~~~~~~~~~~~

n/a - proposed

Guidance on use
~~~~~~~~~~~~~~~

Guidance on dates can be found in the section :ref:`How Dates Work`.


.. _training-public-notes:

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

This field should be used whenever any claim requires additional explanation because for a general reader the claim is not clearly and directly stated in the citation. For the example of use above a citation published on 15 July 2019 refers to something happening "last week" and as a result a researcher has determined the previous Sunday 7 July 2019 through Saturday 13 July 2019 should be entered into the appropriate fields of ``first_imprecise:range`` and ``last_imprecise:range``. That range would not be immediately clear to a public audience since neither date is directly referenced in the text of the citation. As a result, the researcher should explain how that date range was evidenced by the citation.


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

For a :ref:`training` the only entry allowed for this field is ``claim``.
