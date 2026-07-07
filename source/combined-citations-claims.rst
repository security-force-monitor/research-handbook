Evidencing Claims By Combining Citations
########################################

Occassionally, claims made by multiple citations can be brought together to clarify or enhance the claims made by another citation. 


.. admonition:: Example

    Citations establish that light infantry divisions of Myanmar are made up of three tactical operations commands, each of which in turn command battalions. For the ``99 Light Infantry Division`` citations establish there are the following tactical operations commands under it: ``991 Tactical Operations Command``, ``992 Tactical Operations Command``, and the ``993 Tactical Operations Command``. Thus all tactical operations commands exist in the Monitor's dataset. However, citations often reference battalions as being a part of the ``99 Light Infantry Division``, without specifying which tactical operations command the particular battalion is under. Because of this, even though all possible tactical operations commands are known and represented in the data, the Monitor has created an "Unknown" unit, the ``Unknown Tactical Operations Command (99 Light Infantry Division)``. Any citation that states a battalion is part of the ``99 Light Infantry Division``, without referencing a tactical operations command, is used to evidence a :ref:`relation` between the battalion and the ``Unknown Tactical Operations Command (99 Light Infantry Division)``. Of course, the supporting citations that establish battalions are under tactical operations command would also be entered in the :ref:`citation:refs:claim <citation-relation>` for the claim, and an explanatory note would be entered in :ref:`public_notes:meta <relation-public-notes>`.



Parent Units Assuming Poistioning and Classifications
*****************************************************



Unit Classifications
====================

Classifications are "pushed up" to parent units or the :ref:`relation:related_unit:refs:assertion` units, meaning that a :ref:`unit` should have all of the :ref:`unit:classifications:assertion` of any subordinate :ref:`unit`. For example, the :ref:`unit` representing the head of state or head of government which acts as commander-in-chief of the armed forces would have a :ref:`unit:classifications:assertion` of ``Military``, among others.

Positionings
============

Every :ref:`positioning` should be "pushed up" to parent units or the :ref:`relation:related_unit:refs:assertion` units, which have a :ref:`relation` that overlaps any :ref:`positioning` claim for any subordinate :ref:`unit`.

.. admonition:: Example

    The Myanmar Army contains ten light infantry divisions which control battalions. A citation references the ``79 Infantry Battalion`` operating in ``Lashio Township`` on ``2020-04-24``, giving that battalion a :ref:`positioning` for ``Lashio Township`` on ``2020-04-24``. Other citations establish a :ref:`relation` between the ``79 Infantry Battalion`` and the ``99 Light Infantry Division`` before and after the :ref:`positioning` of the battalion to ``Lashio Township``. In this case, a :ref:`positioning` claim for ``99 Light Infantry Division`` operating in ``Lashio Township`` on ``2020-04-24`` should be created. The claim would be evidenced by the original citation for the ``79 Infantry Battalion`` :ref:`positioning` in ``Lashio Township``, along with all of the citations evidencing the :ref:`relation` between the ``79 Infantry Battalion`` and the ``99 Light Infantry Division``. Best practice is to add a :ref:`public_notes:meta <positionings-public-notes>` to this claim as well to explain the connection for a general audience.
