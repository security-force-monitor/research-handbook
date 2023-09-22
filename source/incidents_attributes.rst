Incidents
#########

The "Incident" claim type stores information about publicly-documented allegations of acts committed by state-controlled security forces that may violate human rights laws and standards, international criminal law and other sets of relevant norms. Incidents may include extrajudicial killings, rape, torture and other forms of violence. Security Force Monitor does not make these allegations itself, but compiles allegations made by governmental bodies, human rights organizations and other civil society actors around the world.

The Security Force Monitor focuses its research on the structure, personnel and operations of security forces; we do not directly investigate specific allegations of human rights abuse in the way that Amnesty International or Human Rights Watch do. As such we consider all reports of human rights abuses as “alleged” in our documentation. This simply means these are claims that other organizations have made and which we are repeating without further verification. The Security Force Monitor does not make allegations against security forces and the data that we publish does not attempt to demonstrate involvement of individuals or units in human rights abuses beyond that which other organizations have alleged.


Incident: Summary of claim attributes
*************************************

The table below summarises the following dimensions of Incident claims:

 - Attribute label: a human readable label for the attribute
 - Attribute name: a unique machine-readable name for the attribute, used during data capture
 - Status: whether the attribute is optional or required in a claim
 - Data type: the sort of data that can be entered into the attribute
 - Conformed name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-incident-fields.csv
   :header-rows: 1
   :delim: tab

Incident: Details of claim attributes
*************************************

This section contains further information about each attribute, including descriptions, examples of use, and guidance on use.

Incident: Unique Identifier
===========================

Attribute name
~~~~~~~~~~~~~~

``::incident:name``

Description
~~~~~~~~~~~

A unique 32 character code assigned to each incident in the dataset.

Attribute type
~~~~~~~~~~~~~~

String

Example of use
~~~~~~~~~~~~~~

``a407be6a-28e6-4237-b4e9-307f27b1202e``

Guidance for use
~~~~~~~~~~~~~~~~

This value is a Universally Unique Indentifier (UUID) generated using a computer program. UUIDs can be created easily using either installable or online tools, for example:

- Linux and OSX users: `uuidgen` command line tool.
- On the web: `UUID Generator <https://www.uuidgenerator.net/version>`__.

The field is administrative, providing a reliable way to differentiate between different incidents.

Incident: Claim Citation Identifier
===================================

Attribute name
~~~~~~~~~~~~~~

``::unit:claim:citation:id``

Description
~~~~~~~~~~~

A unique 32 character code of a citation from a source that evidences the other attribute(s) in this claim.

Atrribute type
~~~~~~~~~~~~~

String in UUID format

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``16d013b5-7073-4446-b22b-46b0edb25632``

Guidance on use
~~~~~~~~~~~~~~~

All claims require a citation, which is a reference to a specific part of a source (for example a page or paragraph reference). The page on citations provides more information about this evidentiary mechanism.

Incident: Earliest Precise Date
===============================

.. Note::
   To Do

Incident: Latest Precise Date
=============================

.. Note::
   To Do

Incident: Earliest Imprecise Date
=================================

.. Note::
   To Do

Incident: Latest Imprecise Date
===============================

.. Note::
   To Do

Incident: Date range is a Start Date
====================================

.. Note::
   To Do

Incident: Date range is an End Date
===================================

.. Note::
   To Do

Incident: Location
==================

Attribute name
~~~~~~~~~~~~~~

``::incident:location``

Description
~~~~~~~~~~~~~~

The unique identifier of a location, drawn from the data on existing locations

Attribute type
~~~~~~~~~~~~~~

String, or string in UUID format

Example of use
~~~~~~~~~~~~~~

``4d7d97a6-d85e-436b-9511-81e8d55ceff3``(the identifier for the location``Baga (osm, point) 4d7d97a6-d85e-436b-9511-81e8d55ceff3``)

Guidance on use
~~~~~~~~~~~~~~~

This field is used to store information about the Location where an incident happened. The value included in this field must be taken from :ref:`Location: Location Identifier` attribute from the Location dataset. For further guidance on the creation, management and use of Locations visit the :ref:`Locations` documentation.

Incident: Location Description
==============================

Attribute name
~~~~~~~~~~~~~~
``::incident:location_description``

Description
~~~~~~~~~~~~~~

A description of the location where the source says the incident occurred.

Attribute type
~~~~~~~~~~~~~~

String

Example of use
~~~~~~~~~~~~~~

``Giwa Barracks``, ``Rikkos neighborhood``, ``Campo Militar Número 6-B``

Guidance for use
~~~~~~~~~~~~~~~~

We use this attribute to record the location of an incident exactly as described in the source. Here is an example:

    "Stanley Adiele Uwakwe and Faka Tamunotonye Kalio were arrested on 10 May and brought to Old GRA detention centre in Port Harcourt. After several days, they were transferred to another police station, but officers there told relatives that the men were not in detention. Unofficially, relatives were informed that the men had been killed by the police."

While they were detained at "Old GRA detention centre" the location of their killing is unclear. It is also not clear where they were located before they were disappeared - was it at the Old GRA or at the unnamed police station? Since we don’t know we’d leave the `Incident: Location Description`_ attribute blank.

Here's another example of how to use this attribute:

    "And in yet a third case, Human Rights Watch interviewed three witnesses who saw soldiers shoot five men on the Customs Bridge in Maiduguri. One of the victims survived. He told Human Rights Watch that on the afternoon of July 28 soldiers entered a mosque where he was praying with four other men. The soldiers removed their robes, beat them, and marched them to their commander at the bridge. He described what happened next: The soldiers told us to lie down. Four of the soldiers opened fire on us. The commander was watching. I was lying on my side. They saw that some of us were moving and shot us again. I then lost consciousness. I regained consciousness in the night and dragged myself to an area in the dirt near Dandal Community Bank. I spent the night under a bus. In the morning an achaba [commercial motorcycle taxi] man who knew me took me to my house. My family called a doctor…. They removed four bullets from my body. A former Boko Haram member who witnessed the shootings at the Customs Bridge insisted to Human Rights Watch that the five men were not Boko Haram members. According to him, “The old man was holding prayer beads, and Boko Haram members don’t do that. The two youth wore T-shirts and the [other] two men wore long pants, not the short pants of Boko Haram.” The soldiers left the corpses on the bridge for three days."

The location we would capture here would be  "the Customs Bridge",  while we would find the correct entry from the Locations dataset for``Maiduguri`` to capture in the `Incident: Location`_ attribute.

A common issue is the separation of specific incidents contained within a single account of violations based on geography.

Often a person is arrested and, for example, beaten at a specific site (and the account might include information about other victims being killed at the site of arrest). They are then transported to another site where they are detained and tortured. Moreover, the conditions during the transportation of detainees/prisoners may amount to violations of fundamental rights and often the narrator describes people dying while being transported.

In such instances, researchers should consider the initial arrest and transportation to the site of detention to be one ``incident`` and abuses committed or otherwise tied to site of detention a separate ``incident``.

Incident: Violation Type
========================

Attribute name
~~~~~~~~~~~~~~

``::incident:violation_type``

Description
~~~~~~~~~~~

Type of alleged violation of human rights law, international humanitarian law or other relevant laws committed during the incident.

Attribute type
~~~~~~~~~~~~~~

Text, multiple entry, controlled vocabulary

Example of use
~~~~~~~~~~~~~~

``Torture; Violations of the Right to Life``, ``Intentionally directing attacks against the civilian population``

Guidance for use
~~~~~~~~~~~~~~~~

In `Incident: Violation Type`_, a value is taken "as is" from the source, without change. If the source states "torture", we transcribe this without further analysis. This is because the Monitor does not make specific direct allegations, but reports verbatim the allegations made by human rights organizations and other credible sources.

Incident: Violation Description
===============================

Attribute name
~~~~~~~~~~~~~~

``::incident:violation_description``

Description
~~~~~~~~~~~

A description of the incident.

Attribute type
~~~~~~~~~~~~~~

String

Example of use
~~~~~~~~~~~~~~

    According to Amnesty International: "Usman Modu, a 26-year-old scrap metal dealer from Maiduguri, spent almost two and a half years in Giwa barracks. He was arrested in April 2012 in Gwange, Maiduguri, during a screening operation after a Boko Haram attack. All the people who left the mosque were gathered together: the elderly and children were allowed to go home. The men were brought before a “pointer”, who pointed at him and 17 other men. He was first taken to a JTF station called NEPA and then to Giwa Barracks. “One by one we were brought in front of an armoured tank. I never saw anything. People said there was someone inside. When I went up, soldiers said I should go left. They started beating me. One soldier beat me with his gun and I fell down. They tied my hands behind my back and beat me. Then told me to go inside the car. I don't know why I was chosen. I was surprised, I don't know what I have done.” The military released Usman with 41 others in November 2014. The 17 men arrested with Usman all died in military custody."

Guidance for use
~~~~~~~~~~~~~~~~

In this attribute we record a direct quotation from the civil society, governmental or other source that describes the incident. When an incident has more than one report tied to it, start the quotation as below:

    According to X organization, “Description of incident”. According to Y organization, “Description of incident”.

Incident: Perpetrator Unit Unique Identifier
============================================

Attribute name
~~~~~~~~~~~~~~

``::incident:perpetrator:unit:ids``

Description
~~~~~~~~~~~

The UUID of the unit against which the allegation is made, selected from the unit dataset.

Attribute type
~~~~~~~~~~~~~~

String, formatted as a UUID

Example of use
~~~~~~~~~~~~~~

``a27d4e1f-7add-4302-ab2e-70c426cce519``

Guidance on use
~~~~~~~~~~~~~~~

Where a source make an allegation against a specific unit, this attribute is used to store that unit's identifier. The unit must already exist in the dataset.

Incident: Perpetrator Person Unique Identifier
===============================================

AAttribute name
~~~~~~~~~~~~~~

``::incident:perpetrator:person:ids``

Description
~~~~~~~~~~~

The UUID of the person against which the allegation is made, selected from the person dataset.

Attribute type
~~~~~~~~~~~~~~

String, formatted as a UUID

Example of use
~~~~~~~~~~~~~~

``a27d4e1f-7add-4302-ab2e-70c426cce519``

Guidance on use
~~~~~~~~~~~~~~~

Where a source make an allegation against a specific person, this attribute is used to store that person's identifier. The person must already exist in the dataset.


Incident: Perpetrator Classification
====================================

Attribute name
~~~~~~~~~~~~~~

``::incident:perpetrator:classification``

Description
~~~~~~~~~~~

General branch or tier of the security force alleged to have committed the act(s) described in the incident.

Attribute type
~~~~~~~~~~~~~~

Text and numbers, multiple entry, controlled vocabulary taken from ``Unit: Classification``

Example of use
~~~~~~~~~~~~~~

``Army``, ``Ejército``, ``Police``, ``Military``, ``Military Police ; Joint Operation``

Guidance for use
~~~~~~~~~~~~~~~~

Sometimes a source will report general information about the alleged perpetrators of an act. For example, rather than state a unit or a specific person the source might include something generic like “soldiers” or “police". In cases like these where we can't be more specific we use this field to record the branch or general classification of the force implicated in the incident. For example:

    According to Amnesty International: "On 1 May 2012, around midnight, Nigerian soldiers arrested 37-year-old Dungus Ladan (not his real name), at his home in Maiduguri. Fatima, Dungus’ wife, told Amnesty International that the soldiers promised to just take him for an interrogation that should not last more than a few hours. When her husband did not return, she said, his father went on 3 May to Giwa barracks to check what had happened. Soldiers told him that Dungus had already been released. When he still did not return, the father went back again to the barracks, where soldiers told him that he should come back the next day to bail out his son. The following day, several relatives went together and gave the soldiers “what they could,” and the soldiers again promised to release Dungus that day. His wife said that the soldiers kept asking for money, and the family kept paying, but Dungus was never released. In February 2014, his father saw Dungus in the detention facility; they spoke briefly. Dungus said he had been framed by some people who owed him money and they arranged for him to be arrested and detained. Since then, his family has not seen him again; soldiers at Giwa barracks have told them he is not there."

The only alleged perpetrators described in this alleged incident are "soldiers". The most appropriate term to enter in `Incident: Perpetrator Classification`_ to match this description which would be "military" because "soldiers" could refer to personnel of the Army, Navy or other armed services of a country.

Entries used in in `Incident: Perpetrator Classification`_ correspond to the list in `Unit Identity: Classification`_.

Incident: Research Comments
=======================

Attribute name
~~~~~~~~~~~~~~

``::incident:claim:comment``

Description
~~~~~~~~~~~

Observations specific to the process of reviewing data in this claim, including fixes, refinements and other suggestions.

Atrribute type
~~~~~~~~~~~~~

String

Example of use
~~~~~~~~~~~~~~

``Parent unit missing``, ``Geography needs attention``, ``Possible duplicate - merge?``

Guidance on use
~~~~~~~~~~~~~~~

Staff Researchers use this attribute to exchange feedback about the data in the claim. This may included changes needed, references to sources that the owner of the claim might look at, and other observations that can improve the quality of the data. Data stored in this attribute are not intended for publication. The comments attribute is common to all claim types in the SFM data model.

Incident: Research Owner
====================

Attribute name
~~~~~~~~~~~~~~

``::incident:claim:researcher``

Description
~~~~~~~~~~~

Initials of Staff Reseacher who first created the unit.

Atrribute type
~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``TL``, ``TW``, ``MM``, ``NP``

Guidance on use
~~~~~~~~~~~~~~~

This attribute allows researchers keep track of claims they have created. It  may be used for arbitrary grouping and tagging of specific sets of claims if needed. This type of attribute is common to all types of claim in the SFM data model.

Incident: Research Status
=====================

Attribute name
~~~~~~~~~~~~~~

``::incident:claim:status``

Description
~~~~~~~~~~~

The place of the claim in the research workflow.

Atrribute type
~~~~~~~~~~~~~

String from controlled vocabulary.

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``1``, ``X``

Guidance on use
~~~~~~~~~~~~~~~

Staff Researchers use this attribute to indicate where a claim stands in the research workflow between the first cut of a claim, review by other researchers, and final readiness for use in analysis or for publication. The values to be used in this attribute are taken from the below list:

- ``X``: Claim should be deleted.
- ``0``: First commit. This claim has just been added and needs review.
- ``1``: Fixes needed. A reviewer has made comments that need to be addressed, which will be recorded in the `Incident: Research Comments`_ attribute.
- ``2``: Fixes made. The owner of this data has addressed the reviewer's comments.
- ``3``: Clean. A final check has been made by a reviewer, and this claim can be used in analysis and can be published.

This type of attribute is common to all claims in the SFM data model.