Data integrity measures
=======================

The data we create is carefully collected from a variety of publicly available sources, generally online, which include laws of the country, government media and press releases, reports from civil society groups, and local and international news reports and many others. We comb through these sources and use the information we find to populate a set of fields about persons, units and incidents, and the relationships between them. The resulting data is a synthesis of information provided within a tapestry of different sources - over 7,000 at the time of writing. We collect data on sources themselves, including their titles, date of publication, online location - the data model for sources is documented in the :doc:`sources` section of this handbook. 

As part of our data creation method, we have implemented four powerful integrity measures that help ourselves and others users of the data interrogate and assess its quality: data point level evidencing; data point confidence scores; making data timebound; and, differentiation of unknown and unnamed units in the command chain. We'll now look at each in turn

Data point level evidencing
---------------------------

Data point level evidencing is the practice of recording the exact source we used to create a specific piece of data right alongside that piece of data.

For example, records about units cover dimensions like the unit's basic identity (``Unit: Name``, ``Unit: Country``, ``Unit: Classification``), its relationships with other units (``Unit: Related Unit``, ``Unit: Membership``), its physical infrastructure (``Unit: Base Name``) and other dimensions.  Data on units are structured in standard formats of over 60 possible fields. We may use hundreds of different sources to create a record about a single unit: however, the sources used to evidence the existence of a unit's base or area of operations may be different from those we use to evidence its participation in a peacekeeping mission. Further, the sources that show when a unit entered a particular location may be different from those that show when it left.

To overcome this challenge, we state what sources are used for each and every data point. This gives us the advantage of being able to quickly audit a data point; it also means we can see all the data points evidenced by a specific source, or a specific part of the source. This point is important: sources can have multiple access points, which we create to show that we used material from a particular page number or archive version of a source. The :ref:`Sources and Access Points` section of this Research Handbook provides more detail on this important concept.

This is quite an unusual way to structure data. In most row-based data capture systems that include data drawn from different sources, there may be a column that contains all the sources for that *row*, leaving the user of the data to guess which sources refer to which data point in the row:

=========  ==========  =========
Unit name  Start date  Sources	
=========  ==========  =========
1 BAT      January     A,B,C,D,E
---------  ----------  ---------
2 BAT      February    C,D,E,F,G
=========  ==========  =========

In our model, the sources for each data point are recorded alongside the relevant data point like this:

=========  =================  ==========  ==================
Unit name  Unit name sources  Start date  Start date sources
=========  =================  ==========  ==================
1 BAT      A,B                January     C,D,E
---------  -----------------  ----------  ------------------
2 BAT      E,F,G              February    C,D,E
=========  =================  ==========  ==================

Implementing this sytem in practice is challenging. For simple data capture systems like spreadsheets, it means adding lots of additional columns to records the sources. If the data model has only a few columns, this isn't a problem; but for a model like ours with over 60 fields, it create a very wide and cumbersome spreadsheet. Where the data capture system is a database with some control over the user interface, it still presents a challenge: we have overcome this in WhoWasInCommand by creating a special "source picker" which enables the user to search for a source, and then associate it with a data point.

Confidence scores
-----------------

Confidence scores are measures of the degree to which the sources available to us agree on the content of a particular data point.

All the data points we create start with a confidence score of ``Low`` until a confluence of different sources indicate we should upgrade it to a designation of ``Medium``. The gap between upgrading the confidence score of a data point from ``Low`` to ``Medium`` is smaller than when moving from ``Medium`` to ``High``. This scoring system gives a useful indicator of a degree to which we can rely on a data point's accuracy.

Each data point (except those tied to an alleged ``incident``) has a confidence score attached to it. The confidence scores only relate to the specific data point to which they are attached.

For instance, if a wide variety of sources agree that the ``1 Division`` is the name of an ``unit`` a confidence score of ``High`` would be assigned to this data point. However, if there is only one source for ``One Division`` as an alias, a confidence score of ``Low`` would be merited.

Confidence scores are determined first by agreement amongst sources about the overall structure and nature of the security forces. Sources for this type of information generally are laws of the country, government websites, and books. For example, if the law states that police force is divided into Police Divisions and Police Stations and a Monitor researcher comes across a source that references a particular Police Division, we would accept that source with ``Low`` confidence as this conforms with what other sources state about the structure of the police. Conversely, if a Monitor researcher came across a source that referenced a "Police Command Zone" they would need to do more research before publishing information on this potential unit, as "Police Command Zone" does not fit into what other sources state about the structure of the police. This could mean the other sources are incorrect, or that a change has occurred in the structure of the police force, or simply that this is a formation not referenced by the Monitor's other sources. Additional research would help clarify the situation.

Timebound Data
--------------

Answering the question “who was where when?” is central for investigations into allegations of human rights abuse(s). Because of this perhaps one of the most defining, and complicaticating, features of the Security Force Monitor’s data is that almost everything we research is connected to time including:

-  Existence of units
-  Parent relationships between units
-  Location of units
-  Areas of operation for units
-  Membership/participation of units of in multi-unit operations
-  Positions held by people

While attaching time to data points aids our mission to support human rights investigations and advocacy, it raises methodological challenges and questions such as:

-  Why the Monitor would (or would not) connect two bits of data through time
-  How the Monitor handles gaps in the public record
-  Questions analysts run through while reviewing time based information

In an ideal world the Monitor would have a source from every day of the year stating where a unit was located or conducting operations. Barring that, having multiple sources regularly making statements like “since X date this unit has been based in this city” would be tremendously helpful. Unfortunately, neither scenario currently occurs, or is likely to occur in the near future, making it necessary to develop a robust way of thinking through time.

Broadly speaking the Security Force Monitor uses agreement among sources to build up details on security force units and individuals. Most of the Monitor’s sources, like government press releases and newspaper articles, can be used to link a value, such as the location of a unit, to a specific date (usually the date of publication). As we collect more sources we need to determine what agreement among sources means for time based values, like the location of a unit.

    Example: the Monitor comes across Source A published on 1 July 2012 stating that the 1 Battalion is based in Lagos. If Source B published on 3 August 2012 also states that the 1 Battalion is based in Lagos we have a decision point about what claim we should make.

Using sources A and B we have two options which can be expressed in text:

1. Separate claims: “As of 1 July 2012 the 1 Battalion was based in Lagos and as of 3 August 2012 the 1 Battalion was based in Lagos, the Monitor does not know where the battalion was based between those two points in time.”
2. Contiguity claim: “From at least 1 July 2012 to at least 3 August 2012 the 1 Battalion was based in Lagos.”

Thus, whenever the Monitor gets a new source of information we have to decide whether to make a “separate” or “contiguity” claim. Based on the example of the 1 Battalion above the Monitor would run through a series of questions to determine which claim (if any) to make:

-  In general, how do other battalions operate, are they sedentary, or highly mobile?
-  How has the 1 Battalion acted in the past, has it been sedentary or highly mobile?
-  Are there other sources disputing these claims (i.e. 1 Battalion being based solely in another city)?
-  Are there any sources indicating the 1 Battalion was in Lagos in July and/or August as part of a “special”, “emergency” or otherwise temporary posting?
-  Are there sources that indicate the 1 Battalion moved in between these two points of time and thus these should be treated as separate deployments to Lagos?
-  Is there anything related to the 1 Battalion’s parent or child units that may impact where it was based?
-  Are there any other mitigating sources (i.e. major restructuring of the military, constitutional changes, etc.) which may impact the basing of the unit?
-  Is more research needed before the Monitor can make any claim?

An argument could be the Monitor should always make “separate claims” as that would be more faithful to the sources. However, the result likely mean an almost incomprehensible amount of detail in the records of people and units, which would obscure when changes really did occur, for instance when a person changed positions or a unit ends operations in an area.

Perhaps the most important point is that it even though data points, like where a unit is based, can be continuous through time, it should never be assumed that those types of features remain consistent between two or more sources. Time is a constant challenge, but given that is a key element in identifying perpetrators of human rights abuses it is necessary to get it right.

Unknown vs. Unnamed Units
-------------------------

The Security Force Monitor regularly encounters ambiguity in sourcing which it has sought to highlight and resolve through the creation of units with "Unknown" or "Unnamed" in the ``Unit: Name`` field. The methodology behind these decisions is laid out below:

1. For "Unknown" units the Monitor will have sources for the overall hierarchical structure of a branch of the security forces, laying out how units should relate to one another up the chain of command. However, the Monitor often will have data on a unit which indicates where it should be in the chain of command, but does not have sourcing for a direct parent. In this case the Monitor creates a unit with "Unknown" in the ``Unit: Name`` and "Placeholder" for the ``Unit: Classification`` field.

    Example: Multiple sources, including the laws of Nigeria, lay out that the chain of command for the Police goes from each state (and the Federal Capital Territory) having a single Police Command, under which are Police Area Commands and under Police Area Command are Police Divisions. For the Abayi Police Division the Monitor has sources placing it in Aba, Abia state, making it ultimately under the control of the Abia State Police Command, per the law. However, the Monitor does not have sources indicating which Police Area Command controls Abayi Police Division, thus the Monitor has created a unit called ``Unknown Police Area Command in Abia State`` which is the parent unit of ``Abayi Police Division``. In turn ``Abia State Police Command`` is the parent of ``Unknown Police Area Command in Abia State``, which connects ``Abayi Police Division`` to the wider police command structure.

For "Unnamed" units the Monitor will have sources that indicate an unit exists, but it does not give a proper name for that unit. In this case the Monitor will create an "Unnamed" unit and continue to update relevant fields related to this unit until such a time that a source is discovered to give it a proper name.

    Example: There are several Regional Operations Commands in the army of Myanmar. Many of these have proper names, such as the 2 Regional Operations Command. Multiple sources reference a Regional Operations Command based in the city of Sittwe, identifying subordinate units, areas of operation and other information related to units. None of these sources, however, give this unit a numerical identifier. In order to capture information about this unit the Monitor named this unit Unnamed Regional Operations Command at Sittwe and will maintain that name until a source with a numerical identifier can be identified.

"Unknown" units exist solely to connect subordinate units to the wider command hierarchy. Since they are a creation of the Monitor they will not have sites, area of operations, memberships or persons attached to them. In contrast, "Unnamed" units have all of the related attributes of a unit, and can have persons attached to them. The only thing they lack is a proper name. As a final note, additional sourcing would change an "Unnamed" unit into a unit with a proper name, whereas additional sourcing could result in the deletion of an "Unknown" unit as an actual parent unit would be identified, removing the need for the "Unknown" unit to exist.
