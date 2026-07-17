Establishing Contiguous or Non-Contiguous Claims
################################################

.. note:: 

   To learn more about the fundamentals of dates and timelines in Security Force Monitor's approach read :ref:`How Dates Work` first.


Answering the question “who was where when?” is central for investigations into allegations of human rights abuse(s). Because of this perhaps one of the most defining, and complicating, features of the Security Force Monitor’s data is that almost everything we research is connected to time including:

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

    Example: the Monitor finds Source A published on 1 July 2012 stating that the 1 Battalion is based in Lagos. If Source B published on 3 August 2012 also states that the 1 Battalion is based in Lagos we have a decision point about what claim we should make.

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

An argument could be the Monitor should always make “separate claims” as that would be more faithful to the sources. However, the result likely mean an almost incomprehensible amount of detail in the records of people and units, which would obscure when changes really did occur, for instance when a person changed positions or a unit ends operations in an area. To some extent, our claim-based system (see :ref:`How Dates Work`) allows us to manage this complexity more easily. It gives us the ability to check specific underlying dates and data points, to plot timelines that have both claimed and inferred date ranges, and to make choices about continuity as described in this article.

Time is a constant challenge, but given that is a key element in identifying perpetrators of human rights abuses it is necessary to get it right.


Positionings
************

Each :ref:`positioning` is always treated as a contiguous, meaning it has the same UUID, unless citations establish it is non-contiguous. 

A :ref:`positioning` should always be given the same UUID if there is an overlap or if the time-ranges of two or more citations fall within 1 day of each other. 

.. admonition:: Example

    Citations establish that the ``502 Light Infantry Battalion`` is part of a mobile formation which is deployed around Myanmar for operations, and because of this :ref:`positioning` claims should not be treated as contiguous. However, there are two different claims that the ``502 Light Infantry Battalion`` has a :ref:`positioning` ``site`` of ``Mantong Township``, one claim on ``2013-04-19`` and the other on ``2013-04-20``. Because these two claims are within a day of each other, they are coded as part of the same :ref:`positioning` giving the ``502 Light Infantry Battalion`` a :ref:`positioning` ``site`` of ``Mantong Township`` from at least ``2013-04-19`` to at least ``2013-04-20``. Another claim giving the ``502 Light Infantry Battalion`` a :ref:`positioning` ``site`` of ``Mantong Township`` on ``2014-04-20`` is coded as a separate, non-contiguous positioning because of the citations stating that the battalion is part of a mobile formation which is deployed around Myanmar for operations.


Relations
*********

Every :ref:`relation` between the same two units is always treated as a contiguous, meaning it has the same UUID, unless citations establish it should be treated as non-contiguous.

.. admonition:: Example

    The ``33 Light Infantry Division`` has multiple citations establishing that it is a mobile unit which can change :ref:`relation` to whatever regional military command controls the area where it is operating. One citation puts the division in an area under ``Northeastern Regional Military Command`` as of ``2016-11-13`` which establishes a :ref:`relation` between the division and the regional command for the same time-range. Another citation places the division in an area under ``Northeastern Regional Military Command`` on ``2016-12-05``. Even though the related units are the same, because citations establish the division is a mobile unit that can change :ref:`relation` based on location these two claims are coded as separate, non-contiguous relations.

Two or more :ref:`relation` claims should always be treated as contiguous if there is an overlap in the time range of the two claims, or if the time-ranges of the claims fall within 1 day of each other.

.. admonition:: Example

    The ``33 Light Infantry Division`` has multiple citations establishing that it is a mobile unit which can change :ref:`relation` to whatever regional military command controls the area where it is operating. One citation puts the division in an area under ``Northeastern Regional Military Command`` from at least ``2016-03-10`` to at least ``2016-03-11``, which establishes a :ref:`relation` between the division and the regional command for the same time-range. Another citation places the division in an area under ``Northeastern Regional Military Command`` on ``2016-03-12``, which again establishes a :ref:`relation` between the division and the regional command for the same time-range. These two claims are coded as the same :ref:`relation` given that they fall within 1 day of each other.

A :ref:`unit` may have multiple, overlapping relations.

.. admonition:: Example

    Citations establish that regional military commands in the Myanmar Army control units that operate in their area of operations. Citations establish through time that the ``290 Infantry Battalion`` is under command of the ``Northeastern Regional Military Command`` and also based in areas under ``Northeastern Regional Military Command`` through time. Combined these citations evidence a contiguous :ref:`relation` between the battalion and ultimately the ``Northeastern Regional Military Command``. Other citations, however, evidence the battalion also operated in areas controlled by different regional military commands. These establish additional relations for the battalion during the time ranges it was operating in areas under the ``Eastern Central Regional Military Command``, ``Northern Regional Military Command``, ``Southeastern Regional Military Command`` or ``Triangle Regional Military Command``.


Postings
********

Every claim has a Universally Unique Identifier (UUID) to distinguish it from any other claim. For a :ref:`posting` this UUID distinguishes them from any other :ref:`posting` in the dataset. This allows a person to have contiguous or non-contiguous :ref:`posting` with the same :ref:`unit`.

For each :ref:`person` their :ref:`posting` is always treated as contiguous, meaning it has the same UUID, unless citations establish it is non-contiguous.

.. admonition:: Example

    Citations establish that on ``2010-08-27`` ``Hla Min`` stopped being commander of the ``Southern Regional Military Command`` and became commander of the ``3 Bureau of Special Operations``. One citation also evidences his being commander of the ``3 Bureau of Special Operations`` on ``2011-07-05`` and another citation states he retired as commander of the ``3 Bureau of Special Operations`` on ``2015-08-10``. All three of these claims are treated as evidencing the same :ref:`posting`. In contrast, the ``2011-07-05`` citation also establishes that ``Hla Min`` once again became commander of the ``Southern Regional Military Command`` on a temporary basis as its commander was removed. This :ref:`posting` as commander of the ``Southern Regional Military Command`` is treated as a separate :ref:`posting` with a different UUID as the previous :ref:`posting` held on ``2010-08-27``.

Determining whether one person held multiple postings is based on some match of postings among different citations.

.. admonition:: Example

    If citation stated ``John Alfred Smith`` was commander of ``Police Station 1`` and another citation stated ``J. Smith`` was commander of ``Police Station 3`` there would be no match and these should be coded as two separate people each with their own :ref:`about_entity:ref:claim <person-about-entity>`. If a third citation stated that during the career of ``John Smith`` he was commander of ``Police Station 1``, ``Police station 15`` and ``Police Station 3`` then all of these would be treated as the same person given the match of at least one :ref:`posting` across all citations and the similar names of the person in each citation.
