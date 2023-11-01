Publication
###########

Publications are the organisations that issue sources. Typical records in this entity type include media organisations, non-governmental organisations, state bodies, and governments. We record these distinctly from sources and citations, rather than simply as values within those types of record.

This document provides an overview of what information we store about publications.

Source: Summary of attributes
*****************************

The table below summarises the following dimensions of source records:

 - Attribute label: a human readable label for the attribute
 - Attribute name: a unique machine-readable name for the attribute, used during data capture
 - Status: whether the attribute is optional or required in a records
 - Data type: the sort of data that can be entered into the attributes
 - Conformed name: a standardized name that simplifies attribute use in SFM databases


.. csv-table::
   :file: _static/cluster-source-publications.csv
   :header-rows: 1
   :delim: tab


Source: Details of attributes
*****************************

This section contains further information about each attribute, including descriptions, examples of use, and guidance on use.


Publication: Unique Identifier
==============================

Attribute name
~~~~~~~~~~~~~~

``::publication/id``

Description
~~~~~~~~~~~

A unique 32 character code assigned to each publication.

Attribute type
~~~~~~~~~~~~~~

String in UUID format.

Status
~~~~~~

This attribute is required.

Example of use
~~~~~~~~~~~~~~

``1c03ec21-0fae-4243-9de6-686568afc2b8``

Guidance on use
~~~~~~~~~~~~~~~

This value is a Universally Unique Indentifier (UUID) generated using a computer program. The attribute :ref:`Source: Publication Unique Identifier` draws from the values stored in this attribute. 


Publication: Name
=================

Attribute name
~~~~~~~~~~~~~~

``::publication/name``

Description
~~~~~~~~~~~

Full name of the publication

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``Agence Malienne de Presse``, ``Voice of Nigeria``, ``The Aviationist``

Guidance on use
~~~~~~~~~~~~~~~

This attribute is used to record the full, official name of a publication. 

Publication: Level of State Control
===================================

.. Warning::

   This is an experimental field, and is not yet fully implemented. A better way to approach this would be to reframe this as a claim about a publication, meaning the specific page/datapoint of State Media Monitor's research would become a citation that could also change over time.


Attribute name
~~~~~~~~~~~~~~

``::publication/state-control``

Description
~~~~~~~~~~~

An attribute to store an assessment made about the extent of state control of the publication.

Attribute type
~~~~~~~~~~~~~~

Single value from controlled list

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``CaPu``, ``IP``

Guidance on use
~~~~~~~~~~~~~~~

This experimental attribute is designed to enable the analysis of the data we hold that is derived from both state sources.

In this attribute, we store information about the publication which is drawn from the research of `State Media Monitor <https://statemediamonitor.com/>`_ into the degree of state control over a publication. There are seven categories in State Media Monitor's `typology <https://statemediamonitor.com/typology/>`_:

- ``SC``: State Controlled Media
- ``CaPu``: Captured Public/State Managed Media
- ``CaPr``: Captured Private Media
- ``ISFM``: Independent State Funded and State Managed Media
- ``ISF``: Independent State Funded Media
- ``ISM``: Independent State Managed Media
- ``IP``: Independent Public Media


Publication: Country
==============================

ttribute name
~~~~~~~~~~~~~~

``::publication/country``

Description
~~~~~~~~~~~

The primary country where the publication is established.

Attribute type
~~~~~~~~~~~~~~

Single vaue, from list

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``mx``

Guidance on use
~~~~~~~~~~~~~~~

Values for this attribute are chosen from the list of ISO 3166-1 alpha-2 codes, which can be found (`on the ISO website <https://www.iso.org/obp/ui/#search/code/>`_ and on `Wikipedia <https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Officially_assigned_code_elements>`_. Sometimes, this attribute is  difficult to populate as the country of establishment of a publication can be obscure. 


Publication: Research Comments
==============================

Attribute name
~~~~~~~~~~~~~~

``::publication/comments``

Description
~~~~~~~~~~~

Observations specific to the process of reviewing data about this publication, including fixes, refinements and other suggestions.

Attribute type
~~~~~~~~~~~~~~

String

Status
~~~~~~

This attribute is optional.

Example of use
~~~~~~~~~~~~~~

``Publication country is incorrect``, ``State Media Monitor doens't have an entry for this publication``

Guidance on use
~~~~~~~~~~~~~~~

Staff Researchers use this attribute to pass on feedback about the data about the publication itself. This may include the progress made in extracting information from the sources this publication has issued, and other specific remarks about the quality of the data about a publication. Data in this attribute are not intended for publication.