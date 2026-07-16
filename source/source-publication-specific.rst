Publication
###########

Publications are the organizations, individuals or accounts that publish sources. Typical records in this entity type include security forces themselves, media organizations, non-governmental organizations, government agencies, and social media accounts. We record these distinctly from a :ref:`source` or :ref:`citation`, rather than simply as values within those types of record.

This document provides an overview of what information we store about publications.

Publication: Summary of attributes
**********************************

The table below summarizes the following dimensions of source records:

 - Attribute label: a human readable label for the attribute
 - Status: whether the attribute is optional or required in a record
 - Data type: the sort of data that can be entered into the attribute
 - Key name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-source-publications.csv
   :header-rows: 1


Publication: Details of attributes
*****************************

This section contains further information about each attribute, including descriptions, examples of use, and guidance on use.


source:publication_country
==========================

Description
~~~~~~~~~~~

The primary country where the publication is established.

Attribute type
~~~~~~~~~~~~~~

Single value, from list

Status
~~~~~~

This attribute is optional.

Key name
~~~~~~~~

``:publication/country``

Example of use
~~~~~~~~~~~~~~

``mx``

Guidance on use
~~~~~~~~~~~~~~~

Values for this field are chosen from the list of ISO 3166-1 alpha-2 codes, which can be found (on the `ISO website <https://www.iso.org/obp/ui/#search>`_). This value is determined based on the location of the organization (often found in the "Contact Us" section of a website) or the location a platform gives a social media account. If this cannot be determined the field should be left blank.


source:publication_name
=======================

Description
~~~~~~~~~~~

Full name of the publisher or publication of the source.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is required.

Key name
~~~~~~~~

``:publication/name``

Example of use
~~~~~~~~~~~~~~

``Agence Malienne de Presse``, ``Human Rights Watch``, ``@CapitaineIb226``

Guidance on use
~~~~~~~~~~~~~~~

This attribute is used to record the full, official name of a publisher or publication. This can be the security force itself (such as Nigerian Army), a news organization (such as Reuters), a non-profit organization (such as Amnesty International), a user account on social media (such as @CapitaineIb226), or other similar types of publishers of information.
