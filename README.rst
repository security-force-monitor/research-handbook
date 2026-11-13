Security Force Monitor: Research Handbook
=========================================

This repository contains Security Force Monitor's Research Handbook, which is deployed publicly at `help.securityforcemonitor.org <https://help.securityforcemonitor.org>`_. The Research Handbook documents the approach used by Security Force Monitor (SFM) to research police, army and other security and defence forces alleged to have carried out violations of human rights law and international criminal law. It provides an overview of SFM's research methodology, along with documentation of SFM's data model. More information about SFM can be found at `securityforcemonitor.org/about <https://securityforcemonitor.org>`_.

Documentation toolset
---------------------

- The text of the Research Handbook is written in `reStructuredText <https://docutils.sourceforge.io/rst.html>`_. Earlier versions were written in Markdown, and published on GitBook.
- The `Sphinx Python Documentation Generator <https://www.sphinx-doc.org/en/master/>`_ turns this into nice webpages. Install with ``pip``.
- The Research Handbook is hosted on `ReadTheDocs <https://readthedocs.org>`_, using a free account.
- The whole thing is version controlled under git, and pushed to Github, which has a webhook to ReadTheDocs: changes pushed to the ``master`` branch of the repository will be automatically pushed to ReadTheDocs.

The system has been set up using the steps described in ReadTheDocs in their own documentation. The page on `Managing Translations <https://docs.readthedocs.io/en/stable/guides/manage-translations.html>`_ is particularly helpful.

How to do some common tasks
---------------------------

Here are some notes on how to accomplish a few tasks in this system.

How to make a simple update to existing Handbook content
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

- Create and checkout a new git branch to make the changes in (e.g. ``git checkout -b mychanges``)
- Update the .rst files in ``/source`` with any changes you want to make.
- Run ``make html`` and those changes will then be reflected in the files in ``/build``.
- Work through any errors that Sphinx throws at this point; it's got quite chatty and helpful error messages.
- Commit the changes to repo; merge and push them to ``master``.
- Marvel as ReadTheDocs rebuilds the documentation with the new changes and publishes it to the ``latest`` branch. If this doesn't happen automatically, check the webhooks.

How to add a new page to the Handbook
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

- Create and checkout a new git branch for the work.
- Create your new page ``foo.rst`` in ``/source`` and add in the content.
- Update ``/source/index.rst`` to ensure new the page appears in the document tree.

How to add a complete new translation to the Handbook
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

- Head to ReadTheDocs and set up a new project for the translation, and remember to set up and confirm the webhook that links Github and ReadTheDocs. The key here is that the new project pulls from the same git repo, but it will be treated by the system as a translation of the main Handbook. To to do this, the new project's language setting should match the translation. Then, in the main Handbook's project, specify that this new project is a translation of it.
