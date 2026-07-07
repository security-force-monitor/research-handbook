Cross-Referencing Claims
########################

Creating a vast structured dataset allows us to use the data itself as a cross-reference system for any claim made by citations. Claims can be balanced against one another and where there is a conflict or discrepancy between two or more claims the Monitor can arrive at a decision of which claim can be coded as ``accepted`` or ``conflict``.

Cross-referencing is core to our approach because we do not grade one :ref:`publication` as any better than any other :ref:`publication`. In our experience official government webpages have misidentified the geography of their country, misidentified senior military commanders and contained other errors or omissions. This does not make them "low confidence" or "untrustworthy" sources of information, and that same principle applies to every other :ref:`publication`.

The Montior's data structure allows for a range of cross-referencing, comparing units or persons to one another, to more complex analysis. A public note should always accompany any cross-referencing analysis, and the various citations used should also be listed in the citation field for the claim. Some examples below show how cross-referencing data can be used to determine when claims are should be coded as ``conflict``.

.. admonition:: Example: Incorrect Commander

    Citations from ``2023-02-04``, ``2024-10-11`` and ``2025-01-18`` evidence that ``Liam Johnson`` was commander of ``18 Brigade`` on those dates. As a result, the data has one contiguous :ref:`posting` for Johnson from at least ``2023-02-04`` to at least ``2025-01-18``. One other citation states that ``Theodore Smith`` was commander of ``18 Brigade`` "in 2024". In this case we would cross-reference the claims made about other brigade commanders to see if any of those other brigades had a similar non-contiguous commander like Smith. If not, then the claim about Smith could be coded as ``conflict``.

.. admonition:: Example: Commander Too Senior

    A common issue is when a senior commander is identified as the "commander" of a low-level unit. Usually this means that they are ultimately in charge of the unit, but not the actual commander of the low-level unit. For example, a citation states that ``Major General`` ``John Smith`` was commander of ``22 Battalion``. Cross-referencing the postings of other major generals allows us to see that other citations evidence major generals in country command divisions, which command brigades, which in turn command battalions. Claims for other postings evidence that brigades are usually commanded by brigadier generals (a lower rank than Major General), and battalions are commanded by colonels (a lower rank than brigadier general). As a result, the claim could coded as ``conflict``.

.. admonition:: Example: Typo in Unit Name

    Typos often create issues that can be resolved through cross-referencing. For example, a citation states that ``Elijah Williams`` received an award as commander of ``Police Station 1`` for the actions of his officers in ``South Township`` on ``2023-03-05``. Other citations evidence that Williams was commander of ``Police Station 12`` from at least ``2022-12-02`` to at least ``2024-05-15``. Additionally, other citations evidence that ``Police Station 12`` operates in (has a :ref:`positioning` of) ``South Township`` from at least ``2021-09-06`` to at least ``2025-01-24``. No other citations about ``Police Station 1`` state that it operates in ``South Township``. As a result the claim could be coded as ``conflict``.
