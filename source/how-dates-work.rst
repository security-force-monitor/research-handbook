How Dates Work 
##############

Dates, specifically time-bound claims, are the central focus of the Security Force Monitor's data and methodology. All claims in the Security Force Monitor dataset are time-bound.

We structure all dates into ranges with a first and last date. The first date in the range can be the "start" and the last date can be the "end" of the range. Even a single day, such as 5 May 2025 would be entered with a first date of 2025-05-05 and a last date of 2025-05-05. All dates should be entered in the YYYY-MM-DD format.


Precise ranges
**************

For a precise range all of the details of the claim are true for all dates in the range. Precise ranges can be for a single day with the first and last dates being the same value.

.. admonition:: Example

    A citation states that John Smith was appointed commander of the 1 Brigade on 2014-08-01. To structure this sentence into data we'd pull out multiple claims: 
    
    ``unit``
    ``1 Brigade`` (entry for ``name:annotation`` and ``unit:names:assertion``) would have a ``first_precise:range`` of ``2014-08-01`` and ``last_precise:range`` of ``2014-08-01``, with the ``starting:range`` of ``N`` and ``ending:range`` of ``N``.
    
    ``person``
    ``John Smith`` (entry for ``name:annotation`` and ``person:names:assertion``) would have a ``first_precise:range`` of ``2014-08-01`` and ``last_precise:range`` of ``2014-08-01``, with the ``starting:range`` of ``N`` and ``ending:range`` of ``N``.
    
    ``posting``
    ``John Smith`` as part of ``1 Brigade`` has ``posting:roles:assertion`` of ``Commander`` would have a ``first_precise:range`` of ``2014-08-01`` and ``last_precise:range`` of ``2014-08-01``, with the ``starting:range`` of ``Y`` and ``ending:range`` of ``N``.

In the example above the citation clearly states that the ``posting`` starts on a specific date of ``2014-08-01``. However, it does not indicate that the ``person`` was born on that day or that the ``unit`` was created on that day. Thus, the ``starting:range`` for the ``person`` and ``unit`` is ``N``.

The date of publication of the citation is always an important consideration when establishing date ranges for claims.

.. admonition:: Example

    A citation published on 2023-11-05 states "Xavier Johnson, commander of the 9 Battalion, discussed recent operations with reporters today. Since Johnson became commander on November 1st there have been a steady tempo of operations throughout Southern District." This citation would evidence the following claims:
    
    ``unit``
    ``9 Battalion`` (entry for ``name:annotation`` and ``unit:names:assertion``) would have a ``first_precise:range`` of ``2023-11-01`` and ``last_precise:range`` of ``2023-11-05``, with the ``starting:range`` of ``N`` and ``ending:range`` of ``N``.
    
    ``positioning``
    ``9 Battalion`` in ``Southern District`` with ``positioning:types:assertion`` of ``aoo`` would have a ``first_precise:range`` of ``2023-11-01`` and ``last_precise:range`` of ``2023-11-05``, with the ``starting:range`` of ``N`` and ``ending:range`` of ``N``.
    
    ``person``
    ``Xavier Johnson`` (entry for ``name:annotation`` and ``person:names:assertion``) would have a ``first_precise:range`` of ``2023-11-01`` and ``last_precise:range`` of ``2023-11-05``, with the ``starting:range`` of ``N`` and ``ending:range`` of ``N``.
    
    ``posting``
    ``Xavier Johnson`` as part of ``9 Battalion`` with ``posting:roles:assertion`` of ``Commander`` would have a ``first_precise:range`` of ``2023-11-011`` and ``last_precise:range`` of ``2023-11-05``, with the ``starting:range`` of ``Y`` and ``ending:range`` of ``N``.

In the example above the ``last_precise:range`` is established based on the the date of publciation of the citation, whereas the ``first_precise:range`` is explictly stated in the text of the citation.



Imprecise ranges
****************

For an imprecise range the details of the claim were true for at least one day in the range. Imprecise ranges give the ability to accurately capture ambiguity with dates in the data.

.. admonition:: Example

    A citation published on 2024-03-24 states "The 15 Regiment quickly responded to the attack on February 15th, conducting operations in several nearby areas, including Western, Upper, Lower and Central-South Governorates." The precise dates when the regiment was conducting these operations in any of the governorates is not clearly stated, however, we can establish an imprecise range for all of these positionings. For all of these positionings the ``first_imprecise:range`` would be ``2024-02-15`` and ``last_imprecise:range`` would be ``2024-03-24`` (the date of publication of the citation).
    
The above example illustrates an important aspect of coding dates as ranges as opposed to collasping data entry into a singular date values. An alternative approach  using "fuzzy dates" such as ``February 2024`` creates major problems for these types of imprecise claims by "streching" the time range of the data beyond what the underlying citation actually is claiming. Using a "fuzzy date" of ``February 2024`` would mean the regiment could have been conducting operations in the four governorates *before* the attack on February 15th - something the citation explictly does not evidence. Similarly, a "fuzzy-date" approach would introduce errors for the last date which using "fuzzy-dates" could be entered as ``March 2024``. Taking that approach streches the claim beyond what the citation evidences as it projects into the future, after the citation was published. To avoid either scenario Security Force Monitor enters dates as a range with full YYYY-MM-DD values.

Often citations will have claims which effectively translate to "at some point in time before this citation was published."

.. admonition:: Example

    A citation states that John Smith was appointed commander of the 1 Brigade on 2014-08-01. The citation also states that "John Smith previously commanded the 8 Battalion."
    
    The scope of "previously" may appear unclear, but with imprecise ranges we can faithfully capture the time-bound claim being made. The value of ``since_beginning_of_time`` may be entered in the ``first_imprecise:range`` field to capture the scale of "previously" or similar statements from citations which, put another way, mean "at some point in time before the date of publication this claim was true." In the case of the example above, the ``posting`` of ``John Smith`` to the ``8 Battalion`` would have a ``first_imprecise:range`` of ``since_beginning_of_time`` and a ``last_imprecise:range`` of ``2014-08-01``.


Connecting Precise and Imprecise ranges
****************************************

Often citations have a combination of precise and imprecise time-bound claims which must be carefully identified to properly enter into the dataset. When a claim has both a precise and imprecise range these must be entered so that there is a seamless date range that connects both ranges.

.. admonition:: Example

    A citation published on 2005-06-03 states: "Steven Wendell met with local officials at the 165 Battalion's headquarters today. Wendell, who as appointed as battalion commander last month addressed concerns about security for the coming election season."
    
    ``unit``
    ``165 Battalion`` (entry for ``name:annotation`` and ``unit:names:assertion``) would have a ``first_precise:range`` of ``2005-06-01`` and ``last_precise:range`` of ``2005-06-03``, ``first_imprecise:range`` of ``2005-05-01`` and ``last_imprecise:range`` of ``2005-05-31`` with the ``starting:range`` of ``N`` and ``ending:range`` of ``N``.
    
    ``person``
    ``Xavier Johnson`` (entry for ``name:annotation`` and ``person:names:assertion``) would have a ``first_precise:range`` of ``2023-11-01`` and ``last_precise:range`` of ``2023-11-05``, with the ``starting:range`` of ``N`` and ``ending:range`` of ``N``.
    
    ``posting``
    ``Xavier Johnson`` as part of ``9 Battalion`` with ``posting:roles:assertion`` of ``Commander`` would have a ``first_precise:range`` of ``2023-11-011`` and ``last_precise:range`` of ``2023-11-05``, with the ``starting:range`` of ``Y`` and ``ending:range`` of ``N``.



.. admonition:: Example

    A citation published on 2019-06-30 states: "Police from Central Police Station arrested the suspect in North District yesterday. Speaking to reporters the commander of Central Police Station, Julian Black, said officers uncovered multiple weapons in the suspect's home." These two setences contain multiple time-bound claims. The citation clearly identifies that the operation in North District occurred "yesterday" which would be ``2019-06-29`` as that is the day before the date of publication of the citation. All other claims should be understood to be tied to the date of publication, as there is no other indication they occurred at any other time. As a result, for the ``unit`` of ``Central Police Station`` it has a ``first_precise:range`` of ``2019-06-29``, "yesterday" from the date of publication of the citation, and ``last_precise:range`` of ``2019-06-30``. The ``positioning`` for ``Central Police Station`` with an ``aoo`` of ``North District`` is ``first_precise:range`` of ``2019-06-29`` and ``last_precise:range`` also of ``2019-06-29``, "yesterday" from the date of publication of the citation. The ``person`` of ``Julian Black`` has ``first_precise:range`` of ``2019-06-30`` and ``last_precise:range`` also of ``2019-06-30``. His ``posting`` to ``Central Police Station`` also has a ``first_precise:range`` of ``2019-06-30`` and ``last_precise:range`` also of ``2019-06-30``, the date of publication of the citation. There is no indication from the citation that ``Julian Black`` had his ``posting`` "yesterday" when the operation occurred.

In a single claim any precise ranges should be contained within the imprecise range.

Example imprecise/precise - Before commanding the 1st Battalion he served in various positions including: chief of staff of the 3rd Brigade, operations commander for the 3rd Battalion and deputy commander of the 10th Regiment. From June 5th 2012 to April 19th 2015 he was commander of the 1st Battalion. Afterwards he served in variety of positions: head of the Officer Training School, deputy commander of the 4th Brigade, and section coordinator for Operation Enforcement. He retired from the army in 2019.

.. note::

   Our article :ref:`Fragmentation in timelines` provides extended guidance to help researchers decisions about whether a timeline is continuous or not. 






