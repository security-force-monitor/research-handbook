Claims With Multiple Citations
##############################

Occasionally, the information in one citation can only be surfaced or made sense of with additional evidence from other citations. In these cases, the claim would have multiple citations, instead of a single citation. Whenever multiple citations are used there must be a explanatory note in the ``public_notes:meta`` field detailing what the additional citations help evidence. This process is another type of cross-referencing which information from other citations can be brought to bear on any one claim (see the section :ref:`Cross-Referencing Claims` for more details).

Citations with both Accepted and Conflicted Information
*******************************************************

The most common use for combining citations is for instances where a citation has both accepted and conflict information for a single claim.

.. admonition:: Example

    One citation evidences a :ref:`posting` as of ``2020-06-07`` for ``John Smith`` to the ``15 Battalion`` as ``commander`` (:ref:`posting:roles:assertion`) with the :ref:`posting:ranks:assertion` of ``Major General``. Other citations before and after ``2020-06-07`` evidence that ``John Smith`` had the rank of ``Colonel``. Other citations also establish that commanders of other battalions have the rank of ``Colonel`` or ``Lieutenant Colonel``. The full :ref:`posting` claim for ``John Smith`` with the rank of ``Major General`` should be entered as a ``conflict`` claim. However, the citation does contain information that matches other citations, and this should be captured as well. An additional entry is made for a :ref:`posting` for ``John Smith`` as commander of ``15 Battalion`` as of ``2020-06-07``. Notably this second entry does not contain the ``conflict`` information of the rank of ``Major General``. The additional contextual citations for ``John Smith`` as commander of ``15 Battalion`` with rank of ``Colonel``, along with the other citations for other battalion commanders have the rank of ``Colonel`` or ``Lieutenant Colonel`` should be added to this entry with an explanatory :ref:`public_notes:meta <posting-public-notes>`.

"Unknown" Units
***************

Unknown units are created when citations establish the hierarchy for units, but do not evidence the specific :ref:`relation` for one or more units. See the :ref:`Unknown and Unnamed units` section for a fuller discussion of this issue.

.. admonition:: Example

    Citations establish that light infantry divisions of Myanmar are made up of three tactical operations commands, each of which in turn command battalions. For the ``99 Light Infantry Division`` citations establish there are the following tactical operations commands under it: ``991 Tactical Operations Command``, ``992 Tactical Operations Command``, and the ``993 Tactical Operations Command``. Thus all tactical operations commands exist in the Monitor's dataset. However, citations often reference battalions as being a part of the ``99 Light Infantry Division``, without specifying which tactical operations command the particular battalion is under. Because of this, even though all possible tactical operations commands are known and represented in the data, the Monitor has created an "Unknown" unit, the ``Unknown Tactical Operations Command (99 Light Infantry Division)``. Any citation that states a battalion is part of the ``99 Light Infantry Division``, without referencing a tactical operations command, is used to evidence a :ref:`relation` between the battalion and the ``Unknown Tactical Operations Command (99 Light Infantry Division)``. Of course, the supporting citations that establish battalions are under tactical operations command would also be entered in the :ref:`citation:refs:claim <citation-relation>` for the claim, and an explanatory note would be entered in :ref:`public_notes:meta <relation-public-notes>`.

Clarifying Positionings
***********************

In many countries a city, small administrative division, and sub national division may all share similar names and be referenced with the same name. When it is unclear which location is being referenced the largest possible area should be used. Sometimes, however, citations can bring additional context to the :ref:`positioning` claim to help evidence that a smaller division, or even specific city is the appropriate claim.

.. admonition:: Example

    Bawlakhe in Myanmar is the name of a city, a township (a small administrative division) and a district (a larger administrative division that contains one or more townships). If a citation states that a :ref:`unit` is based in Bawlakhe it should be coded as Bawlakhe District as that is the largest area. However, if other citations evidence the same unit is based in the city of Bawlakhe then these could be added as contextual citations and the claim could be coded as * also * evidencing a :ref:`positioning` for the unit in the city of Bawlakhe. 


Taking on Classifications of Positionings of Subordinate Units
**************************************************************

The classifcations and positionings of subordinate units should be taken by their superior units, (units that have a :ref:`relation` to the subordinate unit). By its very nature this approach creates multiple citations for the claim. See the :ref:`Assumption of Poistioning and Classifications By Superior Units` section for a fuller discussion of this issue.


