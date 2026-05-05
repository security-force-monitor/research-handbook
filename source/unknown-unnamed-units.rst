Unknown and Unnamed units
#########################


The Monitor regularly encounters ambiguity in sourcing which it has sought to highlight and resolve through the creation of units with "Unknown" or "Unnamed" in the :ref:`Unit Identity: Name` attribute. The methodology behind how we make these decisions is laid out below:

1. For "Unknown" units the Monitor will have sources for the overall hierarchical structure of a branch of the security forces, laying out how units should relate to one another up the organizational structure. However, the Monitor often will find claims about a unit which indicate where it should be in the chain of command, but do themselves source claims of the unit's direct parent. In this case the Monitor creates a record for a unit with "Unknown" in the ``name:annotation`` and ``Placeholder`` for the ``unit:classifications:assertion`` field. This unit would also "inherit" the ``positionings`` of its "child" unit.

.. admonition:: Example

    Multiple sources, including the laws of Nigeria, lay out that the chain of command for the Police goes from each state (and the Federal Capital Territory) having a single Police Command, under which are Police Area Commands and under Police Area Command are Police Divisions. For the Abayi Police Division the Monitor has sources placing it in Aba, Abia state, making it ultimately under the control of the Abia State Police Command, per the law. However, the Monitor does not have sources indicating which Police Area Command controls Abayi Police Division, thus the Monitor has created a unit called ``Unknown Police Area Command in Abia State`` which is the parent unit of ``Abayi Police Division``. In turn ``Abia State Police Command`` is the parent of ``Unknown Police Area Command in Abia State``, which connects ``Abayi Police Division`` to the wider police command structure.

.. admonition:: Example

    Citations establish that light infantry divisions of Myanmar are made up of three tactical operations commands, each of which in turn command battalions. For the ``99 Light Infantry Division`` citations establish there are the following tactical operations commands under it: ``991 Tactical Operations Command``, ``992 Tactical Operations Command``, and the ``993 Tactical Operations Command``. Thus all tactical operations commands exist in the Monitor's dataset. However, citations often reference battalions as being a part of the ``99 Light Infantry Division``, without specifying which tactical operations command the particular battalion is under. Because of this, even though all possible tactical operations commands are known and represented in the data, the Monitor has created an "Unknown" unit, the ``Unknown Tactical Operations Command (99 Light Infantry Division)``. Thus any citation that states a battalion is part of the ``99 Light Infantry Division`` without referencing a tactical operations command, is used to evidence a ``relation`` with the ``Unknown Tactical Operations Command (99 Light Infantry Division)``. Of course, the supporting citations that establish battalions are under tactical operations command would also be entered in the ``citation:refs:claim`` for the claim, and an explantory note would be entered in ``public_notes:meta``.


2. When citations reference a specific unit, but do not include enough information for a proper name the Monitor will create an "Unnamed" unit and continue to update relevant attributes related to this unit until such a time that a source is discovered to give it a proper name.

.. admonition:: Example

    Every tactical operations command in the Myanmar Army is given a numerical identifier which is the core of the name of the unit, with those under regional commands are usually numbered 1 through 3, such as ``1 Tactical Operations Command`` under the ``Coastal Regional Military Command``. However, a citation references some tactical operations commands by location, with no numerical identifier. Until another citation can be found to evidence a numerical idenfitier these units are given an "Unnamed" ``name:annotation``, such as the  ``Unnamed Tactical Operations Command (Mong Mit)``.

"Unknown" units exist solely to connect subordinate units to the wider command hierarchy, and additional sourcing could eliminate the need for them in a dataset as the specific "parent" units were idenfitied. In contrast, for "Unnamed" units the only impact additional sourcing would have would be a change in the ``name:annotation`` for the unit. A ``person`` can have a ``posting`` to an "Unnamed" unit, but not to an "Unknown" unit. Similarly, for purposes of analyis an "Unknown" unit cannot be a perpetrator or ``incident:perpetrator:refs:assertion`` of an incident, but an "Unnamed" unit could.
