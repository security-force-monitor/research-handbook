Sources and Confidence
======================

Every piece of data in Security Force Monitor has at least one source. Confidence scores are given to every piece of data from the Monitor's research with the exception of data related to alleged ``incidents.``\ This is because event data is a repetition of allegations made by other organizations without any judgement as to the validity of those allegations by the Monitor.

Sources
-------

**Citation format**

Every data point in Security Force Monitor must have one or more sources associated with it. A source should be recorded in this format:

    Title of article or website page. Name of publishing organization (country of organization). Date. url. Internet Archive link: url

For example:

    | Army parades oil bunkers in Kaduna. Premium Times (Nigeria). 8 May 2013. http://www.premiumtimesng.com/regional/nwest/133295-army-parades-oil-bunkers-in-kaduna.html
    | Internet Archive link: https://web.archive.org/web/20140912060820/https://www.premiumtimesng.com/regional/nwest/133295-army-parades-oil-bunkers-in-kaduna.html#sthash.Fc0DTTxe.dpbs

**Country information**

We include the country information because there could be a publication with the same name based in another country - for example there is `a publication based in Nigeria named The Guardian <https://guardian.ng/>`__ as well as `a publication based in the United Kingdom named The Guardian <https://www.theguardian.com/uk>`__.

**Date**

When recording the date of a source for use in its citation, we always use the format ``DAY MONTH YEAR (DD MMMM YYYY)``

    | 20 January 2012
    | 7 July 2016
    | 9 November 1999

Confidence
----------

Each data point (except those tied to alleged ``incidents``) has a confidence score attached to it. The confidence scores only relate to the specific data point to which they are attached.

For instance, if a wide variety of sources agree that the ``1 Division`` is the name of an ``organization`` a confidence score of ``High`` would be assigned to this data point. However, if there is only one source for ``One Division`` as an alias, a confidence score of ``Low`` would be merited.

Confidence scores are determined first by agreement amongst sources about the overall structure and nature of the security forces. Sources for this type of information generally are laws of the country, government websites, and books. For example, if the law states that police force is divided into Police Divisions and Police Stations and a Monitor researcher comes across a source that references a particular Police Division, we would accept that source with ``Low`` confidence as this conforms with what other sources state about the structure of the police. Conversely, if a Monitor researcher came across a source that referenced a "Police Command Zone" they would need to do more research before publishing information on this potential organization, as "Police Command Zone" does not fit into what other sources state about the structure of the police. This could mean the other sources are incorrect, or that a change has occurred in the structure of the police force, or simply that this is a formation not referenced by the Monitor's other sources. Additional research would help clarify the situation.

All data points begin with a confidence score of ``Low`` until a confluence of sources merit the designation of ``Medium``. The gap between upgrading the confidence score of a data point from ``Low`` to ``Medium`` is smaller than when moving from ``Medium to High``.
