Establishing Start and End Dates for Postings
#############################################

Determining when a ``person`` was in their position is a central concern of the Security Force Monitor's methodology. Even with seemingly clear sources, establishing when someone began or ended a position, or ``posting``, can be particularly challenging.

Security force personnel often have formalities tied to how they start or end a position, which must be captured in the data carefully to accurately establish when someone is or is not in their ``posting``.


Appointments versus Ceremonies
******************************

There are two types of formalities that can establish the start and/or end dates for postings of security force personnel. 

1) Appointment announcements are the most common source of information for establishing the start date of a person's ``posting``. Usually, appointments are announced in government decrees or other official acts, or in reported in news media. These can also establish the end date for the person being replaced by the appointee (see below for examples).
2) Ceremonies are the other source for information on start and end dates for postings, though in aggregate across all countries covered by the Monitor to date there are generally less sources about ceremonies than appointments. These ceremonies can vary from a single person assuming a posting to "hand-over" ceremonies where the previous person in the position ceremonially passes the position to their replacement (see below for examples).

The Security Force Monitor's general guidance is that the date of appointment is used as the start date for a posting * unless * there is sourcing for a ceremony date. Ceremonies establish that even though a person may have been appointed to a ``posting`` they were not yet in their ``role`` until the date of the ceremony. This may be due to a variety of reasons, but often simple logistics of physically moving from a posting in one place to a posting in another location is enough to have days, if not longer, between an appointment and a ceremony.

Importantly, when there is sourcing for * both * an appointment date and a ceremony date we would have both entered into the dataset and simply enter ``conflict`` in the ``status:meta`` for the appointment date which by its very nature conflicts with the ceremony date.

.. admonition:: Example

    A citation states: "Today 2014-08-03 John Smith took over as commander of the 1 Brigade in ceremony at the brigade's headquarters. Smith was appointed commander of the 1 Brigade on 2014-08-01."
    
    In this case the ``posting`` would have two different start dates, one using the date of the appointment of ``2014-08-01`` (with ``status:meta`` of ``conflict``) and the other for the date of the ceremony of ``2014-08-03`` (with ``status:meta`` of ``accepted``). 


Guidance on Appointments and Ceremonies
***************************************

Citations for appointments or ceremonies may be extremely specific and limited, allowing for straight-forward data entry.

.. admonition:: Example

    A citation states: "John Smith was appointed commander of the 1 Brigade on 2014-08-01."
    A citation states: "Today 2017-11-12 Xavier Johnson took the reins as commander of the 1 Brigade, formally receiving the brigade flag from the division commander."

    Both citation establish start dates for their respective postings (in other terms the ``starting:range`` for each ``posting`` is ``Y``). With no other citations or information in these citations data entry is simple.


Occasionally, citations reporting on appointments may also reference the current occupant in the posting which can establish both a start date and end date.

.. admonition:: Example

    A citation states: "John Smith was appointed commander of the 1 Brigade on 2014-08-01, replacing Christopher Butler, the previous commander."

    In this example the ``posting`` for ``John Smith`` still starts on ``2014-08-01`` (``starting:range`` for Smith's ``posting`` is ``Y``), and it also establishes the end for the ``posting`` of ``Christopher Butler`` on ``2014-08-01`` (in other terms the ``ending:range`` for Butler`s ``posting`` is ``Y``). Bulter would also have an imprecise range of ``since_beginning_of_time`` to ``2014-07-31`` (see :ref:`How Dates Work` for more guidance).

When with Both Appointments and Ceremonies Have Issues
******************************************************

.. note::

   A forth-coming piece will detail how to resolve complex situations where citations exist for appointments and ceremonies, but ceremonies *cannot* be used as the start date due to conflicting with other citations. Once published, this section will be updated.
