Claims with dates 
#################

.. admonition:: Example

  On 4 March 2018, Tatmadaw soldiers entered into areas under KNU control in Lu Thaw Township to build a road. Light Infantry Battalions (LIB) #20, #351, #439 and #598 (Strategic Operations Command (SOC) #2, Southern Command Headquarters (SCH)) built a road from Ler Muh Plaw to Moh Kyoh Hkoh. Infantry Battalions (IB) #60, #53, #48 and #350 (SOC #3, SCH) also started building a road from Hsa Law Kyoh to Paw Nah Kyoh under the supervision of SOC #3 commander Yang Pyay.

  `Hpapun Situation Update: Tatmadaw road construction activities results in skirmishes with the KNLA and displacement in Lu Thaw Township <https://khrg.org/2019/01/18-63-s1/hpapun-situation-update-tatmadaw-road-construction-activities-results-skirmishes>`_

This is a straightforward example of a source that provides a date alongside claims about various units of the Myanmar army. On 4 March 2018, the source claims at least eight different light infantry or infantry brigades were present at locations in Lu Thaw Township (also known as Hpapun Township) in Myanmar. There is also information about the organizational structure and command personnel, which can also be dated.

All claims may have a date or date range for which the information asserted in the claim is valid. When claims are grouped together to tell us more about, for example, a person’s posting to a specific unit, this means we can construct a timeline of a posting. Similarly, we can see how long a unit might have been operating in a particular location, or the time period for which a unit was subordinate to another.

Making claims “timebound” in this manner creates the basis for analysis of the data that doesn’t extend beyond what is supported by the sources that we use. 

Finding dates in sources
************************

Sources contain dates that have different levels of “granularity”, for example:

- A single specific date, like in the example above: 20 June 2023
- A specific date range: 20 June 2023 to 30 June 2023
- A less granular but specific range: “June 2023” or “2023”
- A relative date: “a fortnight earlier than 20 June 2023”: which can be reduced to a specific date, which in this example is  “6 June 2023”. If the source had said “a few weeks earlier than 20 June 2023”, we would not be able to calculate a specific date.
- A subjective date: “late June 2023”, “summer 2023” or “early winter 2022” which cannot be reduced to a specific date. 

Regardless of the granularity, for us to use a date in a claim it must be possible for us to enclose fully the date expressed in the source within a part of a standard date format:

- Year: “2023”
- Year and month: “June 2023”
- Year, month and date: “20 June 2023”

We would capture the subject date “late June 2023”, for example, as “June 2023”. As we don’t know what the source means exactly by “late”, the only certain thing about this date is the month and year. Similarly, with “early winter 2022” - the most certain, non-subjective part is the year. This approach allows us to quantify ambiguous dates with a sufficient degree of accuracy, rather than  discarding them. We discard date information that can’t be reduced credibly to a year, at the very least. The Monitor doesn’t capture data that is beneath the granularity of day, such as a specific time (“3pm”) or period of time (“morning”), with one exception: we record the full publication timestamp of any social media content that we use as a source. 

We record dates using the ISO standard of YYYY-MM-DD, in whole or in part:

- “2023” would be “2023-” 
- “June 2023” would be “2023-06-”
- “20 June 2023” would be “2023-06-20”

If a source has date that we are capable of capturing we then class them as either precise or imprecise dates:

- Precise dates: a single day, such as “20 June 2023” (or “2023-06-20”)
- Imprecise dates: more than one day, such as “June 2023” (“2023-06-”), or “2023” (“2023-”)

Whatever the degree of granularity, however, in our data we represent the date as a range with a earlier and a later date:

- A precise date of 20 June 2023 has the same earlier and later date of 20 June 2023.
- An imprecise date of June 2023 has a different earlier and later date. The earlier date is 1 June 2023 and the later date of 30 June 2023.
- An imprecise date of “2023” has an earlier date of 1 January 2023 and a later date of 31 December 2023. 

Capturing dates in claims
*************************

All claim types in the Monitor’s data model have date capture attributes. For example, the Unit Relation model has the following fields that are used to capture the dates on which a hierarchical relationship between units exists:


.. csv-table::
   :file: _static/how-dates-work-table-1.csv
   :header-rows: 1
   :delim: tab


When constructing the claim, we first decide what type of date we have (precise or imprecise) and choose the appropriate range attributes. 

If a source has a precise date of “20 June 2023”, this would be represented as part of a claim in the following way:


.. csv-table::
   :file: _static/how-dates-work-table-2.csv
   :header-rows: 1
   :delim: tab


Capture of an imprecise date of “June 2023” would look like this:


.. csv-table::
   :file: _static/how-dates-work-table-3.csv
   :header-rows: 1
   :delim: tab


The table below shows how an imprecise date of “2023” would be captured:


.. csv-table::
   :file: _static/how-dates-work-table-4.csv
   :header-rows: 1
   :delim: tab


Assigning hard start and hard end dates
***************************************

Some sources contain information that signals an absolute beginning of one of the types of relationship that we document. For example, `this source about an army reshuffle <https://web.archive.org/web/20180511161135/https://www.mmtimes.com/national-news/11605-major-reshuffles-in-tatmadaw-ranks.html>`_ states that a number of persons have both started and ended postings on 8 September 2014:


.. admonition:: Example

	Military sources have confirmed that Commander-in-Chief Senior General Min Aung  Hlaing ordered a reshuffle of senior officers on September 8, with a number of important positions changing hands.

	As The Myanmar Times has previously reported, strong speculation emerged in June that a military reshuffle would occur in August to pave the way for Senior General Min Aung Hlaing to retire and embark on a political career.

	Military sources said the reshuffle, which was not publicly announced, occurred on September 8. Lieutenant General Mya Tun Oo was the big winner, promoted to full general and given the posts of chief of military security and chief of Bureau of Special Operations-6.

	Lieutenant General Kyaw Swe, who previously held those positions, took over Gen Mya Tun Oo’s former post of chief of staff (army) and was also appointed head of Bureau of Special Operations-5.

	Gen Mya Tun Oo, who is from the 25th intake of the Defence Services Academy, is widely tipped to take over the position of commander-in-chief when Senior General Min Aung Hlaing retires.

	Meanwhile, commander of Yangon Region Command, Major General Sann Oo, was promoted to adjutant-general, while the former adjutant-general, Lieutenant General Khin Zaw Oo, was shifted to the head of Bureau of Special Operations-4.

	Northern Region Command leader Major General Tun Tun Naung was appointed to take of Yangon Region Command.

This source, along with others, gives us confirmation that 8 September 2014 is the absolute start of a range of claims such as:

- Lieutenant General Mya Tun Oo started a posting as commander of 6 Bureau of Special Operations. 
- Major General Sann Oo started a posting as Adjutant General.
- Lieutenant General Khin Zaw Oo ended a posting as Adjutant General.
- Lieutenant General Khin Zaw Oo started a posting as commander of 4 Bureau of Special Operations.

These claims are different from those which just observe, for example, that Lieutenant General Mya Tun Oo is posted as commander of 6 Bureau of Special Operations without specifying that he was promoted or appointed on that specific date.  In that case, it would only be possible to say that it was the earliest or latest amongst a number of dates claims about the posting, rather than the absolute start or end of the posting.

These sort of absolute beginnings and ends can be used in different types of claims:

- :ref:`Unit Identity` claim type: A unit is first founded, or finally disbanded.
- :ref:`Unit Relation` claim type: A unit is first subordinated to a unit, or has that subordination severed.
- :ref:`Unit Positioning` claim type: A unit first establishes itself at a location, or permanently abandons a location.
- :ref:`Person Posting`: A person is first posted as commander of a specific unit, or promoted to a particular rank.

Where we will assess that a source has the sort of information that makes a date categorical in this way, we clarify it using special fields. For example, the Person Posting claim type has the following fields:


.. csv-table::
   :file: _static/how-dates-work-table-5.csv
   :header-rows: 1
   :delim: tab


Drawing from the source example above, we capture data from the source claiming that Lieutenant General Mya Tun Oo started a posting as commander of 6 Bureau of Special Operations on 8 September 2014 in the following way:


.. csv-table::
   :file: _static/how-dates-work-table-6.csv
   :header-rows: 1
   :delim: tab


From dates to timelines
***********************

Individual claims about our subjects of study - units, persons, and so on - carry a specific piece of information, usually included a date, and always with a citation back to the information source. 
To understand what information we have about a specific person, for example, we group  - or “aggregate”  - all the claims about that subject into a single record. As part of this, dates of any sort are turned into a timeline that shows the duration for which the information is supported by sources. Timelines cover:

- Person Identity: The duration of person’s time in a branch of the security or defence forces
- Person Posting: The duration of a person’s posting to a specific unit, at a specific rank or with a specific posting 
- Unit Identity: The duration of a unit’s existence as a specific entity inside a security or defense force
- Unit Relation: The duration of a relationship between two units in the context of a hierarchic or membership-based structure
- Unit Positioning: The duration of a unit’s emplacement at a site or authority over an area of operation.

In most cases, no single source evidences a duration from beginning to end. Rather, a tapestry of sources provide evidence of the relationship at different points in time - often with hard ends and starts. A timeline, then, is a composite of two different things:

- Claimed date ranges: this is where sources cover a period of time completely.
- Inferred date ranges: this is the time gaps between the time periods covered by claimed date ranges.

This mechanism allows us to use the available evidence to allow relationships between entities to endure over time. For example: 

- Claim A says a person was posted to Unit One on 12 March 2023
- Claim B says a person was posted to Unit One unit on 30 November 2023
- The posting has an inferred date range between 13 March 2023 and 29 November 2023

In these cases the Researcher can choose to keep the timeline intact and include an inferred date range. In which case, the posting is “continuous”. 

The researcher can also choose to sever the timeline, and remove the inferred date range, creating a separate, “contiguous” posting. 

The concepts of precise and imprecise dates, and hard start and end dates, are also reflected in the construction of timelines.

.. note::

   Our article :ref:`Fragmentation in timelines` provides extended guidance to help researchers decisions about whether a timeline is continuous or not. 






