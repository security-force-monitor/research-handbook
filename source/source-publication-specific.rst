Publication
###########

Publications are the organisations, individuals or accounts that publish sources. Typical records in this entity type include media organisations, non-governmental organisations, government agencies, and social media accounts. We record these distinctly from sources and citations, rather than simply as values within those types of record.

This document provides an overview of what information we store about publications.

Source: Summary of attributes
*****************************

The table below summarises the following dimensions of source records:

 - Attribute label: a human readable label for the attribute
 - Status: whether the attribute is optional or required in a record
 - Data type: the sort of data that can be entered into the attribute
 - Key name: a standardized name that simplifies attribute use in SFM databases

.. csv-table::
   :file: _static/cluster-source-publications.csv
   :header-rows: 1
   :delim: tab


Source: Details of attributes
*****************************

This section contains further information about each attribute, including descriptions, examples of use, and guidance on use.


source:publication_country
==========================

Description
~~~~~~~~~~~

The primary country where the publication is established.

Attribute type
~~~~~~~~~~~~~~

Single vaue, from list

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

Values for this attribute are chosen from the list of ISO 3166-1 alpha-2 codes, which can be found (`on the ISO website <https://www.iso.org/obp/ui/#search/code/>`_ and on `Wikipedia <https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Officially_assigned_code_elements>`_. Sometimes, this attribute is  difficult to populate as the country of establishment of a publication can be obscure. 


source:publication_name
=======================

Description
~~~~~~~~~~~

Full name of the publication

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

``Agence Malienne de Presse``, ``Voice of Nigeria``, ``The Aviationist``

Guidance on use
~~~~~~~~~~~~~~~

This attribute is used to record the full, official name of a publication.
