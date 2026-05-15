Incidents
#########

Incidents are publicly-documented allegations of acts committed by state-controlled security forces that may violate human rights laws and standards, international criminal law and other sets of relevant norms.

Incidents may include extrajudicial killings, rape, torture and other forms of violence. Security Force Monitor does not make these allegations itself, but compiles allegations made by governmental bodies, human rights organizations and other civil society actors around the world.

The Security Force Monitor does not make allegations against security forces. Nothing in the Monitor’s work should be taken as the Monitor making an allegation against a unit or person. In our work we treat all claims of human rights violations as “alleged” to indicate that these are claims that other organizations have structured into data without further verification.

For each incident, we include a description of the incident from the organization making the allegation, and from this structure data for the alleged type of human rights violation(s), the alleged perpetrator(s), date range and location the alleged type of human rights violation occurred. The data that we publish does not attempt to demonstrate involvement of individuals or units in human rights abuses beyond that which other organizations have alleged.


Incident: Summary of claim attributes
*************************************

The table below summarizes the following dimensions of Incident claims:

 - Attribute label: a human readable label for the attribute
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the attribute
 - Key name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-incident-fields.csv
   :header-rows: 1

Incident: Details of claim attributes
*************************************

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

Entering ``incident`` defines the claim and establishes the fields to be used in further data entry about an incident.


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

Claims are marked ``accepted`` when all of the data can be entered in accordance with the guidance of this handbook. The ``conflict`` flag is used whenever a claim conflicts with another claim (or claims) and a review of citations show it to be the incorrect or false claim. A ``public_notes:meta`` should always accompany any ``conflict`` claim. If the data itself cannot be brought into the SFM standard the flag ``issue`` should be used. Finally, if the current citations cannot establish whether a claim should be flagged as ``accepted`` or ``conflict`` then the flag ``work_needed`` should be used as additional research is needed.


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

Researchers may use this field to make temporary notes or leave temporary comments intended for others in the research team about a claim. These should eventually be addressed and the field cleared by the researcher or research team. If the claim needs an explanatory note or comment to be better understood, then that should be entered in the ``public_notes:meta`` field.


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

Every claim must have at least one citation to evidence the data in the claim. When two or more citations are needed to evidence a claim then a corresponding explanatory note should be entered in the ``public_notes:meta`` field. This field is for the Universally Unique Identifier (UUID) for each citation, found in the ``ref:source:access_point_id:admin`` field in the Sources sheet. When multiple citations are needed every UUID should be semi-colon separated.


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

Every entity has a Universally Unique Identifier (UUID) to distinguish it from any other entity. For an ``incident`` this UUID distinguishes them from any other ``incident`` in the dataset.


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

``Shot Dead in Hsipaw Township``

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the ``about_entity:ref:claim`` which combines the various elements of the claim into a single text field. This field can be manually added by a researcher or automatically populated by the system after import.


country:annotation
==================

Description
~~~~~~~~~~~

Associated country of the unit used for grouping claims.

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

``mx``, ``ph``

Guidance on use
~~~~~~~~~~~~~~~

Values for this field are chosen from the list of ISO 3166-1 alpha-2 codes, which can be found (`on the ISO website <https://www.iso.org/obp/ui/#search>`). The specific country code should be chosen based on the ``incident:location:refs:assertion``.


incident:location:descriptions:assertion
========================================

Description
~~~~~~~~~~~~~~

A textual description of a location which cannot be represented in data, copied directly from the citation.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~
``:assertion/incident:location:descriptions``

Example of use
~~~~~~~~~~~~~~

``gold mining site``

Guidance for use
~~~~~~~~~~~~~~~~

We use this attribute to record the location of an incident exactly as described in the source. Here is an example:

.. admonition:: Example

    "According to Karen Human Rights Group: "On March 18th 2017, a C--- villager named U D---, was shot and killed by Tatmadaw soldiers from LIB #589 at a gold mining site in Shwegyin Township. The leaders of the Tatmadaw and the gold mining company each provided one million kyat (US $736) to the victim’s family as compensation."

While geographic data can be found for Shwegyin Township, the location of the "gold mining site" cannot be determined and geolocated based on this description. Because of this it is entered into the ``incident:location:descriptions:assertion`` field.


incident:location:refs:assertion
================================

Description
~~~~~~~~~~~~~~

The unique identifier of a location, drawn from the data on existing locations

Attribute type
~~~~~~~~~~~~~~

String, or string in UUID format

String

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:assertion/incident:location:refs``

Example of use
~~~~~~~~~~~~~~

``4d7d97a6-d85e-436b-9511-81e8d55ceff3``(the identifier for the location``Baga (osm, point) 4d7d97a6-d85e-436b-9511-81e8d55ceff3``)

Guidance on use
~~~~~~~~~~~~~~~

This field is used to store information about the Location where an incident happened. The value included in this field must be taken from :ref:`Location: Location Identifier` attribute from the Location dataset. For further guidance on the creation, management and use of Locations visit the :ref:`Locations` documentation.


incident:location:names:qa
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

``:assertion/incident:location:refs``

Example of use
~~~~~~~~~~~~~~

``Hpruso Township (osm, poly) fd51e411-0a21-439c-ba3b-b6aa787541d1``

Guidance on use
~~~~~~~~~~~~~~~

The best practice for this field is to use the ``location:humane_id:qa`` of the ``incident:location:refs:assertion``.


incident:violation:types:assertion
==================================

Description
~~~~~~~~~~~

Type of alleged violation of human rights law, international humanitarian law or other relevant laws committed during the incident.

Attribute type
~~~~~~~~~~~~~~

Text, multiple entry

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:assertion/incident:violation:types``

Example of use
~~~~~~~~~~~~~~

``Torture; Violations of the Right to Life``, ``Intentionally directing attacks against the civilian population``

Guidance for use
~~~~~~~~~~~~~~~~

In `Incident: Violation Type`_, a value is taken "as is" from the source, without change. If the source states "torture", we transcribe this without further analysis. This is because the Monitor does not make specific direct allegations, but reports verbatim the allegations made by the source.


incident:violation:descriptions:assertion
=========================================

Description
~~~~~~~~~~~

A description of the incident.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``assertion/incident:violation:descriptions``

Example of use
~~~~~~~~~~~~~~

    According to Amnesty International: "Usman Modu, a 26-year-old scrap metal dealer from Maiduguri, spent almost two and a half years in Giwa barracks. He was arrested in April 2012 in Gwange, Maiduguri, during a screening operation after a Boko Haram attack. All the people who left the mosque were gathered together: the elderly and children were allowed to go home. The men were brought before a “pointer”, who pointed at him and 17 other men. He was first taken to a JTF station called NEPA and then to Giwa Barracks. “One by one we were brought in front of an armoured tank. I never saw anything. People said there was someone inside. When I went up, soldiers said I should go left. They started beating me. One soldier beat me with his gun and I fell down. They tied my hands behind my back and beat me. Then told me to go inside the car. I don't know why I was chosen. I was surprised, I don't know what I have done.” The military released Usman with 41 others in November 2014. The 17 men arrested with Usman all died in military custody."

Guidance for use
~~~~~~~~~~~~~~~~

In this attribute we record a direct quotation from the civil society, governmental or other source that describes the incident. When an incident has more than one report tied to it, start the quotation as below:

    According to X organization, “Description of incident”. According to Y organization, “Description of incident”.


incident:perpetrator:refs:assertion
===================================

Description
~~~~~~~~~~~

The UUID of the unit or person against which the allegation is made, selected from the dataset.

Attribute type
~~~~~~~~~~~~~~

String, formatted as a UUID

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:assertion/incident:perpetrator:refs``

Example of use
~~~~~~~~~~~~~~

``a27d4e1f-7add-4302-ab2e-70c426cce519``

Guidance on use
~~~~~~~~~~~~~~~

Where a source make an allegation against a specific unit or person, this attribute is used to store that entity's identifier. The unit or person must already exist in the dataset.


incident:perpetrator:names:qa
=============================

Description
~~~~~~~~~~~~~~

Human readable name for alleged unit or person perpetrator(s).

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:assertion/incident:perpetrator:refs``

Example of use
~~~~~~~~~~~~~~

``115 Light Infantry Battalion``

Guidance on use
~~~~~~~~~~~~~~~

The best practice for this field is to use the ``name:annotation`` of the unit or person.


incident:perpetrator:classifications:assertion
==============================================

Description
~~~~~~~~~~~

General branch or tier of the security force alleged to have committed the act(s) described in the incident.

Attribute type
~~~~~~~~~~~~~~

Text, multiple entry, controlled vocabulary taken from ``unit:classifications:assertion``

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:assertion/incident:perpetrator:classifications``

Example of use
~~~~~~~~~~~~~~

``Army``, ``Ejército``, ``Police``, ``Military``, ``Military Police ; Joint Operation``

Guidance for use
~~~~~~~~~~~~~~~~

Sometimes a source will report general information about the alleged perpetrators of an act. For example, rather than state a unit or a specific person the source might include something generic like “soldiers” or “police". In cases like these where we can't be more specific we use this field to record the branch or general classification of the force implicated in the incident.

.. admonition:: Example

    According to Amnesty International: "On 1 May 2012, around midnight, Nigerian soldiers arrested 37-year-old Dungus Ladan (not his real name), at his home in Maiduguri. Fatima, Dungus’ wife, told Amnesty International that the soldiers promised to just take him for an interrogation that should not last more than a few hours. When her husband did not return, she said, his father went on 3 May to Giwa barracks to check what had happened. Soldiers told him that Dungus had already been released. When he still did not return, the father went back again to the barracks, where soldiers told him that he should come back the next day to bail out his son. The following day, several relatives went together and gave the soldiers “what they could,” and the soldiers again promised to release Dungus that day. His wife said that the soldiers kept asking for money, and the family kept paying, but Dungus was never released. In February 2014, his father saw Dungus in the detention facility; they spoke briefly. Dungus said he had been framed by some people who owed him money and they arranged for him to be arrested and detained. Since then, his family has not seen him again; soldiers at Giwa barracks have told them he is not there."

The only alleged perpetrators described in this alleged incident are "soldiers". The most appropriate term to enter in `Incident: Perpetrator Classification`_ to match this description which would be "military" because "soldiers" could refer to personnel of the Army, Navy or other armed services of a country.

Entries used in in `Incident: Perpetrator Classification`_ correspond to the list in `Unit Identity: Classification`_.


incident:victim:refs:assertion
==============================

Description
~~~~~~~~~~~

A unique 32 character code assigned to each entity in the dataset.

Attribute type
~~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This is a draft field.

Key name
~~~~~~~~

``:assertion/incident:victim:refs``

Example of use
~~~~~~~~~~~~~~

``521ebf18-f161-4ac9-8c72-5a246efa0458``

Guidance on use
~~~~~~~~~~~~~~~

Every entity has a Universally Unique Identifier (UUID) to distinguish it from any other entity. For a ``person`` this UUID distinguishes them from any other ``person`` in the dataset. This UUID is used in other fields to tie a ``person`` to a ``posting`` or ``incident``.


incident:victim:names:qa
========================

Description
~~~~~~~~~~~

Field that provides human readable name for entity.

Attribute type
~~~~~~~~~~~~~~

Text string

Status
~~~~~~

This is a draft field.

Key name
~~~~~~~~

``:assertion/incident:victim:refs``

Example of use
~~~~~~~~~~~~~~

``John Smith``

Guidance on use
~~~~~~~~~~~~~~~

This field provides a human readable counterpart to the ``incident:victim:refs:assertion``. This field can be manually added by a researcher or automatically populated by the system after import. The best practice is to use the ``name:annotation`` in this field.


first_precise:range
===================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


last_precise:range
==================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


first_imprecise:range
=====================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


last_imprecise:range
====================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


starting:range
==============

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


ending:range
============

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


starting_context:range
======================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


ending_context:range
====================

Full guidance on rationale for and differences between precise and imprecise date ranges, the use of this attribute can be found in the Handbook page :ref:`Claims with dates`.


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

For an ``incident`` the only entry allowed for this field is ``claim``.
