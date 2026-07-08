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
