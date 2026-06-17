Establishing Start and End Dates for Postings
#############################################

Determining when a ``person`` was in their postion is a central concern of the Security Force Monitor's methodology. Perhaps counterintuitively, establishing when someone began or ended a position, or ``posting``, is an area of particular challenge even with seemingly clear sources.

Personnel, usually commanders, in security forces often have formalities tied to how they start or end a position, which must be captured in the data carefully to accurately establish when someone is or is not in their ``posting``.


Appointments versus Ceremonies
******************************

The most common source for information for the start of a person's ``posting`` is an announcement that they have been appointed to a particular ``unit``. These can occur in media reporting, official government decrees, or other types of sources.

.. admonition:: Example

    A citation states: "John Smith was appointed commander of the 1 Brigade on 2014-08-01."

    This citation establishes that the ``posting`` for ``John Smith`` starts on ``2014-08-01`` (in other terms the ``starting:range`` for the ``posting`` is ``Y``).

Occassionally, citations reporting on appointments may also reference the current occupant in the posting which can establish both a start date and end date.

.. admonition:: Example

    A citation states: "John Smith was appointed commander of the 1 Brigade on 2014-08-01, replacing Christopher Butler, the previous commander."

    In this example the ``posting`` for ``John Smith`` still starts on ``2014-08-01`` (``starting:range`` for Smith's ``posting`` is ``Y``), and it also establishes the end for the ``posting`` of ``Christopher Butler`` on ``2014-08-01`` (in other terms the ``ending:range`` for Butler`s ``posting`` is ``Y``).

People may have  

.. admonition:: Example

    A citation states: "Today 2014-08-03 John Smith took over as commander of the 1 Brigade in ceremony at the brigade's headquaters. Smith was appointed commander of the 1 Brigade on 2014-08-01."
    
The example citation shows 

However, some commanders may have a 

The date of publication of the citation is always an important consideration when establishing date ranges for claims.

.. admonition:: Example

    A citation published on 2023-11-05 states "Xavier Johnson, commander of the 9 Battalion, discussed recent operations with reporters today. Since Johnson became commander on November 1st there have been a steady tempo of operations throughout Southern District." This citation would evidence the following claims:
    
    **unit**

    ``9 Battalion`` (entry for ``name:annotation`` and ``unit:names:assertion``) would have a ``first_precise:range`` of ``2023-11-01`` and ``last_precise:range`` of ``2023-11-05``, with the ``starting:range`` of ``N`` and ``ending:range`` of ``N``.
    
    **positioning**

    ``9 Battalion`` in ``Southern District`` with ``positioning:types:assertion`` of ``aoo`` would have a ``first_precise:range`` of ``2023-11-01`` and ``last_precise:range`` of ``2023-11-05``, with the ``starting:range`` of ``N`` and ``ending:range`` of ``N``.
    
    **person**

    ``Xavier Johnson`` (entry for ``name:annotation`` and ``person:names:assertion``) would have a ``first_precise:range`` of ``2023-11-01`` and ``last_precise:range`` of ``2023-11-05``, with the ``starting:range`` of ``N`` and ``ending:range`` of ``N``.
    
    **posting**

    ``Xavier Johnson`` as part of ``9 Battalion`` with ``posting:roles:assertion`` of ``Commander`` would have a ``first_precise:range`` of ``2023-11-011`` and ``last_precise:range`` of ``2023-11-05``, with the ``starting:range`` of ``Y`` and ``ending:range`` of ``N``.

In the example above the ``last_precise:range`` is established based on the date of publication of the citation, whereas the ``first_precise:range`` is explictly stated in the text of the citation.



Imprecise ranges
****************

For an imprecise range the details of the claim were true for at least one day in the range. Imprecise ranges give the ability to accurately capture ambiguity with dates in the data.

.. admonition:: Example

    A citation published on 2024-03-24 states "The 15 Regiment quickly responded to the attack on February 15th, conducting operations in several nearby areas, including Western, Upper, Lower and Central-South Governorates." The precise dates when the regiment was conducting these operations in any of the governorates is not clearly stated, however, we can establish an imprecise range for all of these positionings. For all of these positionings the ``first_imprecise:range`` would be ``2024-02-15`` and ``last_imprecise:range`` would be ``2024-03-24`` (the date of publication of the citation).
    
The above example illustrates an important aspect of coding dates as ranges as opposed to collapsing dates into a singular value with "fuzzy dates" such as ``February 2024``. Fuzzy dates create major problems for these types of imprecise claims by "stretching" the time range of the data beyond what the underlying citation actually is claiming. Using a "fuzzy date" of ``February 2024`` would mean the regiment could have been conducting operations in the four governorates *before* the attack on February 15th - something the citation explicitly does not evidence. Similarly, a "fuzzy-date" approach would introduce errors for the last date which using "fuzzy-dates" could be entered as ``March 2024``. Taking that approach stretches the claim beyond what the citation evidences as it projects into the future, after the citation was published. To avoid either scenario Security Force Monitor enters dates as a range with full YYYY-MM-DD values.

Often citations will have claims which effectively translate to "at some point in time before this citation was published."

.. admonition:: Example

    A citation states that John Smith was appointed commander of the 1 Brigade on 2014-08-01. The citation also states that "John Smith previously commanded the 8 Battalion."
    
    The scope of "previously" may appear unclear, but with imprecise ranges we can faithfully capture the time-bound claim being made. The value of ``since_beginning_of_time`` may be entered in the ``first_imprecise:range`` field to capture the scale of "previously" or similar statements from citations which, put another way, mean "at some point in time before the date of publication this claim was true." In the case of the example above, the ``posting`` of ``John Smith`` to the ``8 Battalion`` would have a ``first_imprecise:range`` of ``since_beginning_of_time`` and a ``last_imprecise:range`` of ``2014-08-01``.


Connecting Precise and Imprecise ranges
****************************************

Often citations have a combination of precise and imprecise time-bound claims which must be carefully identified to properly enter into the dataset. When a claim has both a precise and imprecise range these must be entered so that there is a seamless date range that connects both ranges.

.. admonition:: Example

    A citation published on 2005-06-03 states: "Steven Wendell met with local officials at the 165 Battalion's headquarters today. Wendell, who was appointed as battalion commander last month, addressed concerns about security for the coming election season."
    
    **unit**

    ``165 Battalion`` (entry for ``name:annotation`` and ``unit:names:assertion``) would have a ``first_precise:range`` of ``2005-06-01`` and ``last_precise:range`` of ``2005-06-03``, as well as a ``first_imprecise:range`` of ``2005-05-01`` and ``last_imprecise:range`` of ``2005-05-31``. The ``starting:range`` and ``ending:range`` would both have an entry of ``N``.
    
    **person**

    ``Xavier Johnson`` (entry for ``name:annotation`` and ``person:names:assertion``) would have a ``first_precise:range`` of ``2005-06-01`` and ``last_precise:range`` of ``2005-06-03``, as well as a ``first_imprecise:range`` of ``2005-05-01`` and ``last_imprecise:range`` of ``2005-05-31``. The ``starting:range`` and ``ending:range`` would both have an entry of ``N``.
    
    **posting**

    ``Xavier Johnson`` as part of ``9 Battalion`` with ``posting:roles:assertion`` of ``Commander`` would have a ``first_precise:range`` of ``2005-06-01`` and ``last_precise:range`` of ``2005-06-03``, as well as a ``first_imprecise:range`` of ``2005-05-01`` and ``last_imprecise:range`` of ``2005-05-31``. The ``starting:range`` would have a value of ``Y`` and ``ending:range`` a value of ``N``.
