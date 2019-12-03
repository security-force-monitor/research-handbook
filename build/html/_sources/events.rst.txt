Events
======

Events describe publicly-documented allegations of human rights violations committed by security forces. These include extrajudicial killings, rape, torture and other forms of violence. Security Force Monitor does not make allegations itself, but compiles allegations made by governmental bodies, human rights organizations and other civil society actors.

The Security Force Monitor focuses its research on the structure, personnel and operations of security forces. As such we treat all reports of human rights abuses as “alleged” in our documentation. This simply means these are claims that other organizations have made and which we are repeating without further verification. The Security Force Monitor does not make allegations against security forces and the data that we publish does not attempt to demonstrate involvement of individuals or units human rights abuses outside of what other organizations have alleged.

For each event, we includes data about what happened and when, the location(s) it occurred at, the alleged perpetrators and the type of human rights violation.

Fields in events are not sourced and rated for confidence individually as in the data we create about organizations and persons. We provide a single source for the entire event, cited in our standard format.

We use the term ``incident`` interchangeably with the term ``event``.

Event: ID
---------

**Description**

A unique code assigned to each event in the dataset.

**Type of field**

Text and numbers

**Example of use**

``a407be6a-28e6-4237-b4e9-307f27b1202e``

**Guidance for use**

This field is created automatically when data is uploaded into the Monitor's online platform.

Event: Start date
-----------------

**Description**

The date on which an event started.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Guidance for use**

If an event occurred within a single day, ``Event: Start date`` and ``Event: End date`` should be the same.

Events may occur at some point during a range:

    For example: “On or about August 9, 2006, personnel of the NPF paraded 12 alleged armed robbers—including a 12-year-old—before the media at the Central Police Station in Umuahia, capital of Abia State. They claimed to have arrested the suspects after an exchange of gunfire with the police. Some of those in custody had gunshot wounds, and four others were killed during the incident at Olokobe-Ndume community in Umuahia North Local Government Area of Abia State. Following the parade, the police summarily executed the suspects and deposited their bodies at the premises of the Federal Medical Centre in Umuahia. They claimed that the executed victims signed confessional statements before they were killed. On August 17, 2006, the authorities of the Federal Medical Centre arranged a mass burial for the decomposing bodies of the victims. There were no autopsies or inquests. The police later organized a press conference at which they announced the executions.”

We know from this source that the victims were alive as of 9 August 2006 and we know they were dead as of 17 August 2006. However the exact time of the killing occurred is not clear; it could have happened at any point during that time frame. To accommodate this, we would record ``2006-08-09`` in ``Event: Start date`` and ``2006-08-17`` in ``Event: End date``.

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Event: Start date`` .

Event: End date
---------------

**Description**

The date on which an event ended.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Guidance for use**

If ``Event: End date`` is unclear there are several ways to determine what should be used.

One option is to record the date of interview with victim as ``Event: End date``. We can assume that the violation(s) ended at least the month/day of the interview - or that we at least know they occurred up to that date.

    For example: "Abu Bakr, a former detainee in Giwa Barracks told Amnesty International that he had been forced to share a confined area with up to 400 other people [...] Abu Bakr who was held in Giwa barracks told Amnesty International in July 2014: “There was no toilet. To toilet you use a black plastic bag and when you go out you throw it… or if someone used his maybe he will give you.” He also explained: 'We had rice for breakfast. A small amount, they put it in your hand. You give your hand, they will put the rice, you swallow it, you go back to the cell. Later in the day they give you water once. It is in a jug and you drink and pass it to another inside the cell. In the evening it is rice and stew, small. They give it in a nylon bag. There is no washing, no showers. No sleep. You just sit down only, the place is very tight, just sit on your bottom. You can only pray in the cell where you are sitting.'"

In this example we could record ``2014-07`` in ``Event: End date`` because we know that at some time in July he talked to Amnesty International.

Here's another example:

    “Melvin, a 23-year-old sex worker in Port Harcourt, said she was raped twice by the police. She said: “I was arrested twice. Last month they took all of us to Mile 1 police station. We were six that day, we see different people. They put us in different places [in the police station]. We just have to allow them have sex with us. We were detained for three days. We were asked to pay N3,500 each. The one that will bail you will sleep with you. After that you can go.”

In this case, we can look at the footnotes. They often will give the date of when the victim was interviewed. In this case, both footnotes read: “Amnesty International interview in Port Harcourt, October 2011.” - so “last month” would be ``September 2011`` and we would record this as ``2011-09`` in ``Event: Start date``. While they were detained for three days it is unclear if the complete event occurred in September because Amnesty interviewed this person in October 2011. Accordingly, we could record ``2011-10`` in ``Event: End date`` as they could have been arrested on September 29 and then released on 1 October 2011.

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Event: End date``.

Event: Date of publication
--------------------------

**Description**

The date of publication of the source used to evidence the event.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Guidance for use**

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Event: Date of publication``.

Event: Date of last update
--------------------------

**Description**

The date of most recent update about the event

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Guidance for use**

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Event: Date of last update``.

Event: Status as of last update
-------------------------------

**Description**

Most recently available status of the event

**Type of field**

Text, controlled vocabulary

**Example of use**

Field is not yet implemented.

**Guidance for use**

Field is not yet implemented.

Event: Location
---------------

**Description**

A description of the where the event occurred.

**Type of field**

Text and numbers

**Example of use**

``Giwa Barracks``, ``Rikkos neighborhood``, ``Campo Militar Número 6-B``

**Guidance for use**

We use this field to record the location of an event.

Example:

    "Stanley Adiele Uwakwe and Faka Tamunotonye Kalio were arrested on 10 May and brought to Old GRA detention centre in Port Harcourt. After several days, they were transferred to another police station, but officers there told relatives that the men were not in detention. Unofficially, relatives were informed that the men had been killed by the police."

While they were detained at Old GRA detention centre - the location of their killing is unclear. It is also not clear where they were located before they were disappeared - was it at the Old GRA or at the unnamed police station? Since we don’t know we’d leave the Location field blank.

Here's another example of how to use this field:

    "And in yet a third case, Human Rights Watch interviewed three witnesses who saw soldiers shoot five men on the Customs Bridge in Maiduguri. One of the victims survived. He told Human Rights Watch that on the afternoon of July 28 soldiers entered a mosque where he was praying with four other men. The soldiers removed their robes, beat them, and marched them to their commander at the bridge. He described what happened next: The soldiers told us to lie down. Four of the soldiers opened fire on us. The commander was watching. I was lying on my side. They saw that some of us were moving and shot us again. I then lost consciousness. I regained consciousness in the night and dragged myself to an area in the dirt near Dandal Community Bank. I spent the night under a bus. In the morning an achaba [commercial motorcycle taxi] man who knew me took me to my house. My family called a doctor…. They removed four bullets from my body. A former Boko Haram member who witnessed the shootings at the Customs Bridge insisted to Human Rights Watch that the five men were not Boko Haram members. According to him, “The old man was holding prayer beads, and Boko Haram members don’t do that. The two youth wore T-shirts and the [other] two men wore long pants, not the short pants of Boko Haram.” The soldiers left the corpses on the bridge for three days."

The location would be ``the Customs Bridge`` - while ``Maiduguri`` would be the ``City or other Node Name`` (more on that below)

A common issue is the separation of specific events contained within a single account of violations based on geography.

Often a person is arrested and, for example, beaten at a specific site (and the account might include information about other victims being killed at the site of arrest). They are then transported to another site where they are detained and tortured. Moreover, the conditions during the transportation of detainees/prisoners may amount to violations of fundamental rights and often the narrator describes people dying while being transported.

In such instances, researchers should consider the initial arrest and transportation to the site of detention to be one ``event`` and abuses committed or otherwise tied to site of detention a separate ``event``.

Event: Exact location (Longitude or OSM object Name)
----------------------------------------------------

**Description**

**Type of field**

**Example of use**

**Guidance for use**

Event: Exact location (Latitude or OSM object ID number)
--------------------------------------------------------

**Description**

**Type of field**

**Example of use**

**Guidance for use**

Event: Settlement (OSM object Name)
-----------------------------------

**Description**

The city, town or village in which an event occurred.

**Type of field**

Text, OSM object name, first in a pair of values

**Example of use**

``Monclova``

**Guidance for use**

Often, information about events does not list a settlement by name. If so, we will leave this field blank even if by the description it seems to indicate a particular place. This is because we do not add to reporting only to transcribe what other groups have reported.

Event: Settlement (OSM object ID Number)
----------------------------------------

**Description**

The city, town or village in which an event occurred.

**Type of field**

Number, OSM object ID number, second in a pair of values

**Example of use**

``747101009``

**Guidance for use**

Often, information about events does not list a settlement by name. If so, we will leave this field blank even if by the description it seems to indicate a particular place. This is because we do not add to reporting only to transcribe what other groups have reported.

Event: Top Administrative Area (OSM object name)
------------------------------------------------

**Description**

The OSM object name of the highest sub-national administrative area in which an organization site is based.

**Type of field**

Text, OSM relation name, first in a pair of values

**Example of use**

``Michoacán``

**Guidance for use**

We identify ``Events`` with a number of different levels of geographical precision. In ``Event: Top Administrative Area (OSM relation name)`` we record the text name of highest level subnational boundary for the country in which the site is located, `as found in in OpenStreetMap <http://wiki.openstreetmap.org/wiki/Tag:boundary%3Dadministrative#Super-national_administrations>`__.

    For example Mexico has both *municipios* (administrative level 6 in OSM) and states (administrative level 4). For a ``site`` based in Mexico, we would record in ``Event: Top Administrative Area (OSM relation name)`` the name the "state" (admin level 4).

Event: Top Administrative Area (OSM object ID number)
-----------------------------------------------------

**Description**

The OSM relation ID number of the highest sub-national administrative area in which an organization site is based.

**Type of field**

Text, OSM relation ID number, second in a pair of values

**Example of use**

``2340636``

**Guidance for use**

We identify ``Events`` with a number of different levels of geographical precision. In ``Event: Top Administrative Area (OSM relation ID number)`` we record the text name of highest level subnational boundary for the country in which the event occurred, `as found in in OpenStreetMap <http://wiki.openstreetmap.org/wiki/Tag:boundary%3Dadministrative#Super-national_administrations>`__.

    For example Mexico has both *municipios* (administrative level 6 in OSM) and states (administrative level 4). For an event that occurred in Mexico, we would record in ``Event: Top Administrative Area (OSM relation ID number)`` the name the "state" (admin level 4).

Event: Country
--------------

**Description**

The country in which an event occurred.

**Type of field**

Two letter country code

**Example of use**

``mx``, ``ug``, ``ng``

**Guidance for use**

We identify the location of events with a number of different levels of geographical precision. The ``Event: Country`` field identifies the country in which an event occurred. All entries in this field are two letter country codes taken from `ISO 3166 which can be searched here <https://www.iso.org/obp/ui/#search>`__.

    For example, an event that occurred in Nigeria would have the code ``ng`` and an event that occurred in Brazil would have the code ``br``.

Event: Violation type
---------------------

**Description**

Type of alleged violation of human rights committed during the event.

**Type of field**

Text, controlled vocabulary

**Example of use**

``Torture``, ``Violations of the Right to Life``

**Guidance for use**

In ``Event: Violation type``, values are taken "as is" from the source.

Event: Description
------------------

**Description**

A description of the event.

**Type of field**

Text and numbers

**Example of use**

    According to Amnesty International: "Usman Modu, a 26-year-old scrap metal dealer from Maiduguri, spent almost two and a half years in Giwa barracks. He was arrested in April 2012 in Gwange, Maiduguri, during a screening operation after a Boko Haram attack. All the people who left the mosque were gathered together: the elderly and children were allowed to go home. The men were brought before a “pointer”, who pointed at him and 17 other men. He was first taken to a JTF station called NEPA and then to Giwa Barracks. “One by one we were brought in front of an armoured tank. I never saw anything. People said there was someone inside. When I went up, soldiers said I should go left. They started beating me. One soldier beat me with his gun and I fell down. They tied my hands behind my back and beat me. Then told me to go inside the car. I don't know why I was chosen. I was surprised, I don't know what I have done.” The military released Usman with 41 others in November 2014. The 17 men arrested with Usman all died in military custody."

**Guidance for use**

In this field we record a direct quotation from the civil society, governmental or other source about the event. When an event has more than one report tied to it, start the quotation as below:

    According to X organization, “Description of event”. According to Y organization, “Description of event”.

Event: Perpetrator name
-----------------------

**Description**

The name of the person alleged to have committed the human rights violation(s) in the event.

**Type of field**

Text and numbers, taken from ``Person: Name``

**Example of use**

``Friday Iyamabo``

**Guidance for use**

If a person or persons are named in the sources for the event, we will record it in the ``Event: Perpetrator name`` field. The value in ``Event: Perpetrator name`` will correspond to a value in ``Person: Name``.

    For example: "Nwanneka narrated to NOPRIN researchers her experience at the SCID in Enugu in May 2002. She was initially arrested with two other females by officers of the Ninth Mile Police Station on the outskirts of Enugu on charges of assisting an armed robbery suspect, before being transferred to the SCID on May 3, 2002. After taking the statements of the female detainees, NPF Inspector Friday Iyamabo ordered them detained in the cells of the SCID. He later reportedly returned to the cell with pepper spray and powdered chili pepper, ordered the female detainees to strip and one after the other applied the mixture of pepper spray and chili to their genitals after severely beating them with batons. The detainees were denied access to medical treatment. Five years after this experience, Nwanneka reported to NOPRIN researchers in April 2007 that, as a result of this experience, she continues to suffer from complications with both her reproductive system and urinary tract."

In this case, the alleged perpetrator is named in the source report. We would record the name ``Friday Iyamabo`` in the field ``Event: Perpetrator name``.

Event: Perpetrator organization
-------------------------------

**Description**

The organization(s) alleged to have committed the human rights violation(s) in the event.

**Type of field**

Text and numbers, multiple entry, taken from ``Organization: Name``

**Example of use**

``2 Batallón de Fuerzas Especiales``

**Guidance for use**

If the sources that specific organizations committed the alleged human rights violations described in the event, we include these names in ``Event: Perpetrator name``. The value in ``Event: Perpetrator organization`` will correspond to a value in ``Organization: Name``.

Here is an example of source material that contains information that would be included in ``Event: Perpetrator name``:

    According to the United States Department of State, Bureau of Democracy, Human Rights and Labor: "On March 24, the JTF reportedly killed four men near Isaka in the Okrika Local Government Area, Rivers State, when they confronted them and other armed men attempting to hijack a barge. There was no investigation conducted."

Event: Perpetrator classification
---------------------------------

**Description**

General branch or tier of the security force alleged to have committed the human rights violation(s).

**Type of field**

Text and numbers, controlled vocabulary, taken from ``Organization: Classification``

**Example of use**

``Army``, ``Ejército``,\ ``Police``, ``Military``,\ ``Military Police``,\ ``Joint Operation``

**Guidance for use**

Sometimes a source will report that the alleged perpetrators of a human rights violation are from a generic security force such as “soldiers”, “police” or some other formulation. In this case, use this field to record a classification in the same way as for ``Organization: Classification``. For example:

    According to Amnesty International: "On 1 May 2012, around midnight, Nigerian soldiers arrested 37-year-old Dungus Ladan (not his real name), at his home in Maiduguri. Fatima, Dungus’ wife, told Amnesty International that the soldiers promised to just take him for an interrogation that should not last more than a few hours. When her husband did not return, she said, his father went on 3 May to Giwa barracks to check what had happened. Soldiers told him that Dungus had already been released. When he still did not return, the father went back again to the barracks, where soldiers told him that he should come back the next day to bail out his son. The following day, several relatives went together and gave the soldiers “what they could,” and the soldiers again promised to release Dungus that day. His wife said that the soldiers kept asking for money, and the family kept paying, but Dungus was never released. In February 2014, his father saw Dungus in the detention facility; they spoke briefly. Dungus said he had been framed by some people who owed him money and they arranged for him to be arrested and detained. Since then, his family has not seen him again; soldiers at Giwa barracks have told them he is not there."

The only alleged perpetrators described in this alleged event are "soldiers". The most appropriate term to enter in ``Event: Perpetrator classification`` to match this description which would be ``Military`` because "soldiers" could refer to personnel of the Army, Navy or other armed services of a country.

Event: Source
-------------

**Description**

The source of information about the event.

**Type of field**

Text and numbers

**Example of use**

``"Recomendación No. 49/2011 sobre el caso de retención ilegal y tortura en agravio de V1 en Ciudad Juárez, Chihuahua". Comisión Nacional de los Derechos Humanos (Mexico). 30 August 2011. http://www.cndh.org.mx/sites/all/doc/Recomendaciones/2011/Rec_2011_049.pdf Internet Archive link: http://www.cndh.org.mx/sites/all/doc/Recomendaciones/2011/Rec_2011_049.pdf``

**Guidance for use**

The values we enter here should follow the general citation format used by Security Force monitor, as set out in this Research Handbook:

    Title of article or website page. Name of publishing organization (country of organization). Date. URL. Internet Archive link: URL

Where there are multiple sources about the same event, they are listed in the order of the description.

Event: Notes
------------

**Description**

To DO.

**Type of field**

Text and numbers

**Example of use**

``"Recomendación No. 49/2011 sobre el caso de retención ilegal y tortura en agravio de V1 en Ciudad Juárez, Chihuahua". Comisión Nacional de los Derechos Humanos (Mexico). 30 August 2011. http://www.cndh.org.mx/sites/all/doc/Recomendaciones/2011/Rec_2011_049.pdf Internet Archive link: http://www.cndh.org.mx/sites/all/doc/Recomendaciones/2011/Rec_2011_049.pdf``

**Guidance for use**

The values we enter here should follow the general citation format used by Security Force monitor, as set out in this Research Handbook:

    Title of article or website page. Name of publishing organization (country of organization). Date. URL. Internet Archive link: URL

Where there are multiple sources about the same event, they are listed in the order of the description.
