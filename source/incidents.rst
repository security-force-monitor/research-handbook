Incidents
=========

What are incidents?
-------------------

Incidents are publicly-documented allegations of acts committed by state-controlled security forces that may violate human rights laws and standards, international criminal law and other sets of relevant norms. Incidents may include extrajudicial killings, rape, torture and other forms of violence. Security Force Monitor does not make these allegations itself, but compiles allegations made by governmental bodies, human rights organizations and other civil society actors around the world.

The Security Force Monitor focuses its research on the structure, personnel and operations of security forces; we do not directly investigate specific allegations of human rights abuse in the way that Amnesty International or Human Rights Watch do. As such we consider all reports of human rights abuses as “alleged” in our documentation. This simply means these are claims that other organizations have made and which we are repeating without further verification. The Security Force Monitor does not make allegations against security forces and the data that we publish does not attempt to demonstrate involvement of individuals or units in human rights abuses beyond that which other organizations have alleged.

For each incident, we include data about what happened and when, the location(s) it occurred at, the alleged perpetrators and the type of human rights violation the reporting organization claims has occurred.

In a departure from how we compile data about :doc:`units` and :doc:`persons`, individual fields in incident records are not sourced and rated for confidence. Rather, we provide a single source for the entire incident. This is because each incident is a direct copy of material from a single source rather than a tapestry of material from a range of different sources.

Incident: Unique Identifying Number
-----------------------------------

**Description**

A unique 32 character code assigned to each incident in the dataset.

**Type of field**

Text and numbers

**Example of use**

``a407be6a-28e6-4237-b4e9-307f27b1202e``

**Spreadsheet column name**

``incident:id:admin``

**Shortcode**

``i_id_a``

**Sources**

No

**Confidence**

No

**Guidance for use**

This value is a Universally Unique Indentifier (UUID) generated using a computer program. UUIDs can be created easily using either installable or online tools, for example:

- Linux and OSX users: `uuidgen` command line tool.
- On the web: `UUID Generator <https://www.uuidgenerator.net/version>`__.

The field is administrative, providing a reliable way to differentiate between different incidents.

When a new incident is created directly in WhoWasInCommand, the platform automatically creates a UUID for that incident and stores it in this field. If a new incident is created in a spreadsheet, the Staff Researcher must generate a unique identifying number for that incident and copy it into the field ``incident:id:admin`` for the single row associated with that specific incident. This manual, copy-and-paste step is a potential source of error and the Staff Researcher must be careful not to re-use a UUID.

Bulk updates made to WhoWasInCommand.com by spreadsheet import are based on the values in this field. For example, changes made in the row ``a407be6a-28e6-4237-b4e9-307f27b1202e`` in the spreadsheet will be applied to the incident with that UUID in WhoWasInCommand. 

Incident: Research Owner
------------------------

**Description**

Initials of the Staff Researcher who first created the incident.

**Type of field**

Text

**Example of use**

``TL``, ``TW``, ``MM``

**Spreadsheet column name**

``incident:owner:admin``

**Shortcode**

``i_own_a``

**Sources**

No

**Confidence**

No

**Guidance for use**

This field is adminstrative and only used where data are created in a spreadsheet. It is a simple measure to help researchers keep track of records they have created. These data are not imported into WhoWasInCommand. Instead, WhoWasInCommand keeps a record of the changes (edits, new records, deletion) by the name of the system user who made them.

Incident: Research Status
-------------------------

**Description**

The place of a row of data in the research workflow.

**Type of field**

Number range from 0 to 3.

**Example of use**

``1``

**Spreadsheet column name**

``incident:status:admin``

**Shortcode**

``i_sta_a``

**Sources**

No

**Confidence**

No

**Guidance for use**

This administrative field is only used in spreadsheets. Staff Researchers use this field to indicate where a row of data stands in the research workflow between the first cut of a row of data, review by other researchers, and final readiness for publication. Values in this field are taken from the below controlled list:


- `0`: First commit. This row of data has just been added and needs review.
- `1`: Fixes needed. A reviewer has made comments that need to be addressed, which will be recorded in the ``incident:comment:admin`` field.
- `2`: Fixes made. The owner of this data has addressed the reviewer's comments.
- `3`: Clean. A final check has been made by a reviewer, and this row of data can be published.

Data created and managed in WhoWasInCommand does not use this mechanism. At the time of writing, a simple review system is being implemeneted in WhoWasInCommand.

Incident: Research Comments
---------------------------

**Description**

Observations specific to the process of reviewing data in this row, including fixes, refinements and other suggestions.

**Type of field**

Text

**Example of use**

``Check location``, ``Missing OSM objects``

**Spreadsheet column name**

``incidents:comments:admin``

**Shortcode**

``i_com_a``

**Sources**

No

**Confidence**

No

**Guidance for use**

This is an adminstrative field specific to data created in spreadsheets. Staff Researchers use it to pass on feedback about the data in the row. This may included changes needs to specific fields, references to sources that the owner of the row might look at, and other observations that can improve the quality of the data. Data in this field are not intended for publication. 

Incident: Start Date
--------------------

**Description**

The date on which an incident started.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Spreadsheet column name**

``incident:start_date``

**Shortcode**

``i_sd``

**Sources**

No

**Confidence**

No

**Guidance for use**

If an incident occurred within a single day, ``Incident: Start Date`` and ``Incident: End Date`` should be the same.

Incidents may occur at some point during a range:

    For example: “On or about August 9, 2006, personnel of the NPF paraded 12 alleged armed robbers—including a 12-year-old—before the media at the Central Police Station in Umuahia, capital of Abia State. They claimed to have arrested the suspects after an exchange of gunfire with the police. Some of those in custody had gunshot wounds, and four others were killed during the incident at Olokobe-Ndume community in Umuahia North Local Government Area of Abia State. Following the parade, the police summarily executed the suspects and deposited their bodies at the premises of the Federal Medical Centre in Umuahia. They claimed that the executed victims signed confessional statements before they were killed. On August 17, 2006, the authorities of the Federal Medical Centre arranged a mass burial for the decomposing bodies of the victims. There were no autopsies or inquests. The police later organized a press conference at which they announced the executions.”

We know from this source that the victims were alive as of 9 August 2006 and we know they were dead as of 17 August 2006. However the exact time of the killing occurred is not clear; it could have happened at any point during that time frame. To accommodate this, we would record ``2006-08-09`` in ``Incident: Start Date`` and ``2006-08-17`` in ``Incident: End Date``.

In keeping with all date fields we include in this dataset, where research indicates that only a year or a year and a month, these partial dates can be included in ``Incident: Start Date`` .

Incident: End Date
------------------

**Description**

The date on which an incident ended.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Spreadsheet column name**

``incident:end_date``

**Shortcode**

``i_ed``

**Sources**

No

**Confidence**

No

**Guidance for use**

If ``Incident: End Date`` is unclear there are several ways to determine what should be used.

One option is to record the date of interview with victim as ``Incident: End Date``. We can assume that the allegation(s) ended at least the month/day of the interview - or that we at least know they occurred up to that date.

    For example: "Abu Bakr, a former detainee in Giwa Barracks told Amnesty International that he had been forced to share a confined area with up to 400 other people [...] Abu Bakr who was held in Giwa barracks told Amnesty International in July 2014: “There was no toilet. To toilet you use a black plastic bag and when you go out you throw it… or if someone used his maybe he will give you.” He also explained: 'We had rice for breakfast. A small amount, they put it in your hand. You give your hand, they will put the rice, you swallow it, you go back to the cell. Later in the day they give you water once. It is in a jug and you drink and pass it to another inside the cell. In the evening it is rice and stew, small. They give it in a nylon bag. There is no washing, no showers. No sleep. You just sit down only, the place is very tight, just sit on your bottom. You can only pray in the cell where you are sitting.'"

In this example we could record ``2014-07`` in ``Incident: End Date`` because we know that at some time in July he talked to Amnesty International.

Here's another example:

    “Melvin, a 23-year-old sex worker in Port Harcourt, said she was raped twice by the police. She said: “I was arrested twice. Last month they took all of us to Mile 1 police station. We were six that day, we see different people. They put us in different places [in the police station]. We just have to allow them have sex with us. We were detained for three days. We were asked to pay N3,500 each. The one that will bail you will sleep with you. After that you can go.”

In this case, we can look at the footnotes. They often will give the date of when the victim was interviewed. In this case, both footnotes read: “Amnesty International interview in Port Harcourt, October 2011.” - so “last month” would be ``September 2011`` and we would record this as ``2011-09`` in ``Incident: Start Date``. While they were detained for three days it is unclear if the complete incident occurred in September because Amnesty interviewed this person in October 2011. Accordingly, we could record ``2011-10`` in ``Incident: End Date`` as they could have been arrested on September 29 and then released on 1 October 2011.

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Incident: End Date``.

Incident: Date of Publication
-----------------------------

**Description**

The date of publication of the source used to evidence the incident.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Spreadsheet column name**

``incident:pub_date``

**Shortcode**

``i_pd``

**Sources**

No

**Confidence**

No

**Guidance for use**

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Incident: Date of Publication``.

Incident: Date of Last Update
-----------------------------

**Description**

The date of most recent update about the incident.

**Type of field**

Date (YYYY-MM-DD), fuzzy

**Example of use**

``2012``, ``2012-11``, ``2012-11-23``

**Spreadsheet column name**

``incident:update_date``

**Shortcode**

``i_ud``

**Sources**

No

**Confidence**

No

**Guidance for use**

In keeping with all date fields we include in this dataset, where our research can only find a year or a year and a month, this can be included in ``Incident: Date of Last Update``.

Incident: Status as of Last Update
----------------------------------

**Description**

Most recently available status of the incident.

**Type of field**

Text, controlled vocabulary

**Example of use**

Field is not yet implemented.

**Spreadsheet column name**

``incident:update_status``

**Shortcode**

``i_us``

**Sources**

No

**Confidence**

No

**Guidance for use**

Field is not yet implemented.

Incident: Location Description
------------------------------

**Description**

A description of the where the incident occurred.

**Type of field**

Text and numbers

**Example of use**

``Giwa Barracks``, ``Rikkos neighborhood``, ``Campo Militar Número 6-B``

**Spreadsheet column name**

``incident:location_description``

**Shortcode**

``i_ld``

**Sources**

No

**Confidence**

No

**Guidance for use**

We use this field to record the location of an incident exactly as described in the source. Here is an example:

    "Stanley Adiele Uwakwe and Faka Tamunotonye Kalio were arrested on 10 May and brought to Old GRA detention centre in Port Harcourt. After several days, they were transferred to another police station, but officers there told relatives that the men were not in detention. Unofficially, relatives were informed that the men had been killed by the police."

While they were detained at "Old GRA detention centre" the location of their killing is unclear. It is also not clear where they were located before they were disappeared - was it at the Old GRA or at the unnamed police station? Since we don’t know we’d leave the ``Incident: Location Description`` field blank.

Here's another example of how to use this field:

    "And in yet a third case, Human Rights Watch interviewed three witnesses who saw soldiers shoot five men on the Customs Bridge in Maiduguri. One of the victims survived. He told Human Rights Watch that on the afternoon of July 28 soldiers entered a mosque where he was praying with four other men. The soldiers removed their robes, beat them, and marched them to their commander at the bridge. He described what happened next: The soldiers told us to lie down. Four of the soldiers opened fire on us. The commander was watching. I was lying on my side. They saw that some of us were moving and shot us again. I then lost consciousness. I regained consciousness in the night and dragged myself to an area in the dirt near Dandal Community Bank. I spent the night under a bus. In the morning an achaba [commercial motorcycle taxi] man who knew me took me to my house. My family called a doctor…. They removed four bullets from my body. A former Boko Haram member who witnessed the shootings at the Customs Bridge insisted to Human Rights Watch that the five men were not Boko Haram members. According to him, “The old man was holding prayer beads, and Boko Haram members don’t do that. The two youth wore T-shirts and the [other] two men wore long pants, not the short pants of Boko Haram.” The soldiers left the corpses on the bridge for three days."

The location we would enter into ``Incident: Location Description`` would be  "the Customs Bridge",  while we would enter ``Maiduguri`` into the field called ``Incident: Site, Settlement`` (a field that is documented  below).

A common issue is the separation of specific incidents contained within a single account of violations based on geography.

Often a person is arrested and, for example, beaten at a specific site (and the account might include information about other victims being killed at the site of arrest). They are then transported to another site where they are detained and tortured. Moreover, the conditions during the transportation of detainees/prisoners may amount to violations of fundamental rights and often the narrator describes people dying while being transported.

In such instances, researchers should consider the initial arrest and transportation to the site of detention to be one ``incident`` and abuses committed or otherwise tied to site of detention a separate ``incident``.

Incident: Site, Exact location (Coordinate Pair or Gazetteer Name and Identity Number)
--------------------------------------------------------------------------------------

**Description**

A pair of fields used to capture the most precise location of an incident, using whichever is the more precise of a set of geographical coordinates or a name and reference/identity number from a gazetteer.

**Type of field**

Field pair that takes as input an EPSG:4326 coordinate pair, or a name and reference/identity number from a gazetteer.

**Example of use**

``Ciudad Juárez`` and ``4145208823``

``104.64728`` and ``24.0506``

**Spreadsheet column name**

``incident:site_exact_location_name_longitude`` and ``incident:site_exact_location_id_latitude``

**Shortcode**

``i_selnlon`` and  ``i_selidlat``

**Sources**

No

**Confidence**

No

**Guidance for use**

Where research indicates that an incident occurred at a location that can be geocoded precisely, we record this data in the pair of fields called ``Incident: Site, Exact Location (Coordinate Pair or Gazetteer Name and Identity Number)``. This field pair will take input in two ways:

- A coordinate pair in EPSG:4326 format: The number for longitude should go in ``incident:site_exact_location_name_longitude`` and the number for latitude should go in ``incident:site_exact_location_id_latitude``.
- if the gazetteer in use is Open Street Maps, then we use an OSM object name and ID number: The OSM object name should go in ``incident:site_exact_location_name_longitude`` and the OSM object ID should go in ``incident:site_exact_location_id_latitude``.

Incident: Site, Nearest Settlement
----------------------------------

**Description**

A pair of fields used to capture data on the nearest city, town or village to where an incident occurred.

**Type of field**

Field pair that takes as an input a name and reference/identity number from a gazetteer.

**Example of use**

``Monclova`` and ``747101009``

**Spreadsheet column name**

``incident:site_settlement_name`` and ``incident:site_settlement_id``

**Shortcode**

``i_ssn`` and ``i_ssid``

**Sources**

No

**Confidence**

No

**Guidance for use**

Where a source states that an incident happened in a particular settlement (whether village, town or city), we find the appropriate name and reference/idetity number provided by the gazetteer in use for the dataset, and record it in this pair of fields. If the gazetteer is Open Street Map, for example, we would do the following:

- The OSM object name should be placed in ``incident:site_settlement_name``
- The OSM object ID number should be placed in ``incident:site_settlement_id``

Often, information about incidents does not list a settlement by name. If so, we will leave this field blank even if by the description it seems to indicate a particular place. This is because we only transcribe what other groups have reported about an incident, and do not augment it. 


Incident: Site, First-level Administrative Area
-----------------------------------------------

**Description**

A pair of fields used to record the highest sub-national administrative area of the incident location.

**Type of field**

Field pair that takes as an input a name and reference/identity number from a gazetteer.

**Example of use**

``Michoacán`` and ``2340636``

**Spreadsheet column name**

``incident:site_first_admin_area_name`` and ``incident:site_first_admin_area_id``

**Shortcode**

``i_sfaan`` and ``i_sfaaid``

**Sources**

No

**Confidence**

No

**Guidance for use**

We identify ``incidents`` with a number of different levels of geographical precision. In this field pair we record details of the first level subnational administrative area for the country in which the incident site is located, as defined by the gazetteer in use. For example, if Open Street Map is the gazetteer in use for the dataset, the administrative areas are  `defined here<http://wiki.openstreetmap.org/wiki/Tag:boundary%3Dadministrative#Super-national_administrations>`__. 

For example, in  Mexico there are "*municipios*" (classified as administrative level 6 in OSM) and states (administrative level 4 in OSM). "States" are larger in area than "*municipios*" but in the hierarchy of administrative areas are immediately beneath the international national boundary of Mexico: therefore, "states" are the first-level administrative area. For a ``incident`` which occurred in Mexico, we would record the OSM object name and ID number of the relevant "state" in the field pair called ``Incident: Site, First-level Administrative Area``.

This pair of fields takes input in the following form, using Open Street Map as an example:

- the OSM object name should be placed in the field ``incident:site_first_admin_area_name``
- the OSM object ID number should be placed in the field ``incident:site_first_admin_area_id``

Incident: Country
-----------------

**Description**

The country in which an incident occurred.

**Type of field**

Two letter country code

**Example of use**

``mx``, ``ug``, ``ng``

**Spreadsheet column name**

``incident:site_country``

**Shortcode**

``i_sc``

**Sources**

No

**Confidence**

No

**Guidance for use**

We identify the location of incidents with a number of different levels of geographical precision. The ``Incident: Country`` field identifies the country in which an incident occurred. All entries in this field are two letter country codes taken from `ISO 3166 which can be searched here <https://www.iso.org/obp/ui/#search>`__.

    For example, an incident that occurred in Nigeria would have the code ``ng`` and an incident that occurred in Brazil would have the code ``br``.

Incident: Violation type
------------------------

**Description**

Type of alleged violation of human rights law, international humanitarian law or other relevant laws committed during the incident.

**Type of field**

Text, multiple entry, controlled vocabulary

**Example of use**

``Torture; Violations of the Right to Life``, ``Intentionally directing attacks against the civilian population``

**Spreadsheet column name**

``incident:violation_type``

**Shortcode**

``i_vt``

**Sources**

No

**Confidence**

No

**Guidance for use**

In ``Incident: Violation Type``, a values is taken "as is" from the source. If the source states "torture", we transcribe this without further analysis.

This field can accept multiple entries. If the field is created in a spreadsheet, the discrete entries must be separated with semi-colon.

Incident: Violation Description
-------------------------------

**Description**

A description of the incident.

**Type of field**

Text and numbers

**Example of use**

    According to Amnesty International: "Usman Modu, a 26-year-old scrap metal dealer from Maiduguri, spent almost two and a half years in Giwa barracks. He was arrested in April 2012 in Gwange, Maiduguri, during a screening operation after a Boko Haram attack. All the people who left the mosque were gathered together: the elderly and children were allowed to go home. The men were brought before a “pointer”, who pointed at him and 17 other men. He was first taken to a JTF station called NEPA and then to Giwa Barracks. “One by one we were brought in front of an armoured tank. I never saw anything. People said there was someone inside. When I went up, soldiers said I should go left. They started beating me. One soldier beat me with his gun and I fell down. They tied my hands behind my back and beat me. Then told me to go inside the car. I don't know why I was chosen. I was surprised, I don't know what I have done.” The military released Usman with 41 others in November 2014. The 17 men arrested with Usman all died in military custody."

**Spreadsheet column name**

``incident:violation_description``

**Shortcode**

``i_vd``

**Sources**

No

**Confidence**

No

**Guidance for use**

In this field we record a direct quotation from the civil society, governmental or other source that describes the incident. When an incident has more than one report tied to it, start the quotation as below:

    According to X organization, “Description of incident”. According to Y organization, “Description of incident”.

Incident: Perpetrator Name
--------------------------

**Description**

The name of the person alleged to have committed the act(s) described in the incident.

**Type of field**

Text and numbers, multiple entry, taken from entries recorded in ``Person: Name``

**Example of use**

``Friday Iyamabo``

**Spreadsheet column name**

``incident:perpetrator_name``

**Shortcode**

``i_pn``

**Sources**

No

**Confidence**

No

**Guidance for use**

If a person or persons are named in the sources for the incident, we will record this information in the ``Incident: Perpetrator Name`` field. The value in ``Incident: Perpetrator Name`` will correspond to a value in ``Person: Name``.

    For example: "Nwanneka narrated to NOPRIN researchers her experience at the SCID in Enugu in May 2002. She was initially arrested with two other females by officers of the Ninth Mile Police Station on the outskirts of Enugu on charges of assisting an armed robbery suspect, before being transferred to the SCID on May 3, 2002. After taking the statements of the female detainees, NPF Inspector Friday Iyamabo ordered them detained in the cells of the SCID. He later reportedly returned to the cell with pepper spray and powdered chili pepper, ordered the female detainees to strip and one after the other applied the mixture of pepper spray and chili to their genitals after severely beating them with batons. The detainees were denied access to medical treatment. Five years after this experience, Nwanneka reported to NOPRIN researchers in April 2007 that, as a result of this experience, she continues to suffer from complications with both her reproductive system and urinary tract."

In this case, the alleged perpetrator is named in the source report. We would record the name ``Friday Iyamabo`` in the field ``Incident: Perpetrator Name``.

Incident: Perpetrator Unit 
--------------------------

**Description**

The unit(s) alleged to have committed the act(s) described in the incident.

**Type of field**

Text and numbers, multiple entry, taken entries recorded in ``Unit: Name``

**Example of use**

``2 Batallón de Fuerzas Especiales``

**Spreadsheet column name**

``incident:perpetrator_unit``

**Shortcode**

``i_pu``

**Sources**

No

**Confidence**

No

**Guidance for use**

If the source for the incident states that specific units committed the alleged human rights violations described in the incident, we include these names in ``Incident: Perpetrator Unit``. The value in ``Incident: Perpetrator Unit`` will correspond to a value in ``Unit: Name``.

Here is an example of source material that contains information that would be included in ``Incident: Perpetrator Unit``:

    According to the United States Department of State, Bureau of Democracy, Human Rights and Labor: "On March 24, the JTF reportedly killed four men near Isaka in the Okrika Local Government Area, Rivers State, when they confronted them and other armed men attempting to hijack a barge. There was no investigation conducted."

In this case, we would search ``Unit: Name`` for the canonical entry for "JTF" and include it in the field ``Incident: Perpetrator Unit``.

Incident: Perpetrator classification
------------------------------------

**Description**

General branch or tier of the security force alleged to have committed the act(s) described in the incident.

**Type of field**

Text and numbers, multiple entry, controlled vocabulary taken from ``Unit: Classification``

**Example of use**

``Army``, ``Ejército``,\ ``Police``, ``Military``,\ ``Military Police ; Joint Operation``

**Spreadsheet column name**

``incident:perpetrator_classification``

**Shortcode**

``i_pcl``

**Sources**

No

**Confidence**

No

**Guidance for use**

Sometimes a source will report general information about the alleged perpetrators of an act. For example, rather than state a unit or a specific person the source might include something generic like “soldiers” or “police". In cases like these where we can't be more specific we use this field to record the branch or general classification of the force implicated in the incident. For example:

    According to Amnesty International: "On 1 May 2012, around midnight, Nigerian soldiers arrested 37-year-old Dungus Ladan (not his real name), at his home in Maiduguri. Fatima, Dungus’ wife, told Amnesty International that the soldiers promised to just take him for an interrogation that should not last more than a few hours. When her husband did not return, she said, his father went on 3 May to Giwa barracks to check what had happened. Soldiers told him that Dungus had already been released. When he still did not return, the father went back again to the barracks, where soldiers told him that he should come back the next day to bail out his son. The following day, several relatives went together and gave the soldiers “what they could,” and the soldiers again promised to release Dungus that day. His wife said that the soldiers kept asking for money, and the family kept paying, but Dungus was never released. In February 2014, his father saw Dungus in the detention facility; they spoke briefly. Dungus said he had been framed by some people who owed him money and they arranged for him to be arrested and detained. Since then, his family has not seen him again; soldiers at Giwa barracks have told them he is not there."

The only alleged perpetrators described in this alleged incident are "soldiers". The most appropriate term to enter in ``Incident: Perpetrator Classification`` to match this description which would be "military" because "soldiers" could refer to personnel of the Army, Navy or other armed services of a country.

Entries in ``Incident: Perpetrator Classification`` correspond to those in ``Unit: Classification``.

Incident: Source
----------------

**Description**

The UUID of the access point in the source that provides information about the incident.

**Type of field**

Text and numbers, chosen from list

**Example of use**

``5b8362d6-b13a-4764-9ff0-2d7cfd7d5f37``

**Spreadsheet column name**

``incident:all:source``

**Shortcode**

``i_all_s``

**Sources**

No

**Confidence**

No

**Guidance for use**

Unlike data captured about ``units`` or ``person``, data about ``incidents`` are not sourced at the level of each individual field. Instead, we have a single source for the whole incident. The entry in ``Incident: Source`` should be a Unique Identifier ("UUID") for a source access point that has been alreayd created in the master list of sources. The relevant values will be found in the field ``Source: Access Point Unique Identifier``.
