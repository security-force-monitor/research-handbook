How Dates Work 
##############

Dates, specifically time-bound claims, are the central focus of the Security Force Monitor's data and methodology. All claims in the Security Force Monitor dataset are time-bound. Sometimes citations clearly state the dates for claims that they make and the methodology for structuring these claims into time-bound data is simple. Often, however, citations contain ambigious claims about dates which need careful consideration to properly capture as data.

We structure all dates into ranges with a first and last date. The first date in the range can be the "start" and the last date can be the "end" of the range. Often most This means even a single day, such as 5 May 2025 would be entered with a first date of 2025-05-05 and a last date of 2025-05-05. All dates should be entered in the YYYY-MM-DD format.


Precise ranges
**************

Precise ranges mean all of the details of the claim were true for all dates in the range.

.. admonition:: Example

    A citation states that John Smith was appointed commander of the 1 Brigade on 2014-08-01. To structure this sentence into data we'd pull out multiple claims: 
    
    ``unit`` with a ``name:annotation`` and ``unit:names:assertion`` of ``1 Brigade`` would have a ``first_precise:range`` of ``2014-08-01`` and ``last_precise:range`` of ``2014-08-01``, with the ``starting:range`` of ``N`` and ``ending:range`` of ``N``.
    
    ``person`` with a ``name:annotation`` and ``person:names:assertion`` of ``John Smith`` would have a ``first_precise:range`` of ``2014-08-01`` and ``last_precise:range`` of ``2014-08-01``, with the ``starting:range`` of ``N`` and ``ending:range`` of ``N``.
    
    ``posting`` of ``John Smith`` to ``1 Brigade`` with ``posting:roles:assertion`` of ``Commander`` would have a ``first_precise:range`` of ``2014-08-01`` and ``last_precise:range`` of ``2014-08-01``, with the ``starting:range`` of ``Y`` and ``ending:range`` of ``N``.

In the example above the citation clearly states that the ``posting`` starts on a specific date of ``2014-08-01``. However, it does not indicate that the ``person`` was born on that day or that the ``unit`` was created on that day. Thus, the ``starting:range`` for the ``person`` and ``unit`` is ``N``.


Imprecise ranges
****************

Imprecise ranges mean details of the claim were true for at least one date in the range.


.. admonition:: Example

    TO DO

Many times citations will be so ambigious that the true range of a claim may appear impossible to capture.

.. admonition:: Example

    A citation states that John Smith was appointed commander of the 1 Brigade on 2014-08-01. The citation also states that "John Smith previously commanded the 8 Battalion".

The scope of "previously" may appear unclear, but with imprecise ranges we can faithfully capture the time-bound claim being made. The value of ``since_beginning_of_time`` may be entered in the ``first_imprecise:range`` field to capture the scale of "previously" or similar statements from citations which, put another way, mean "at some point in time before the date of publication this claim was true." In the case of hte example above, the ``posting`` of ``John Smith`` to the ``8 Battalio`` would have a ``first_imprecise:range`` of ``since_beginning_of_time`` and a ``last_imprecise:range`` of ``2014-08-01``.

In a single claim any precise ranges should be contained within the imprecise range.

Example imprecise/precise - Before commanding the 1st Battalion he served in various positions including: chief of staff of the 3rd Brigade, operations commander for the 3rd Battalion and deputy commander of the 10th Regiment. From June 5th 2012 to April 19th 2015 he was commander of the 1st Battalion. Afterwards he served in variety of positions: head of the Officer Training School, deputy commander of the 4th Brigade, and section coordinator for Operation Enforcement. He retired from the army in 2019.


Overlapping Precise and Imprecise ranges
****************************************

Often citations have multiple time-bound claims which must be carefully identified to properly enter into the dataset.

.. admonition:: Example

    A citation published on 2019-06-30 states: "Police from Central Police Station arrested the suspect in North District yesterday. Speaking to reporters the commander of Central Police Station, Julian Black, said officers uncovered multiple weapons in the suspect's home." These two setences contain multiple time-bound claims. The citation clearly identifies that the operation in North District occurred "yesterday" which would be ``2019-06-29`` as that is the day before the date of publication of the citation. All other claims should be understood to be tied to the date of publication, as there is no other indication they occurred at any other time. As a result, for the ``unit`` of ``Central Police Station`` it has a ``first_precise:range`` of ``2019-06-29``, "yesterday" from the date of publication of the citation, and ``last_precise:range`` of ``2019-06-30``. The ``positioning`` for ``Central Police Station`` with an ``aoo`` of ``North District`` is ``first_precise:range`` of ``2019-06-29`` and ``last_precise:range`` also of ``2019-06-29``, "yesterday" from the date of publication of the citation. The ``person`` of ``Julian Black`` has ``first_precise:range`` of ``2019-06-30`` and ``last_precise:range`` also of ``2019-06-30``. His ``posting`` to ``Central Police Station`` also has a ``first_precise:range`` of ``2019-06-30`` and ``last_precise:range`` also of ``2019-06-30``, the date of publication of the citation. There is no indication from the citation that ``Julian Black`` had his ``posting`` "yesterday" when the operation occurred.


.. note::

   Our article :ref:`Fragmentation in timelines` provides extended guidance to help researchers decisions about whether a timeline is continuous or not. 






