Overview: Trainings (Draft)
###########################

.. warning::

   Security Force Monitor publishes a a dataset on unclassified training activities for non-US security forces arranged and funded by the United States Department of State and Department of Defence between 2001 and 2021. Sources, scraping, cleaning and publishing toolset included. The  data can be accessed `online <https://trainingdata.securityforcemonitor.org>`_

   We are in the process of integrating this dataset on the training provided by the United States to foreign militaries. The documentation here is in draft from. Full documentation, along with raw data and codebase for the existing project is also available `online <https://github.com/security-force-monitor/fmtrpt_data/>`_.


A key question we have is whether specific units and personnel implicated in human rights abuses have received training or assistance from the United States government. Whether the training or assistance was given prior to or after the unit's implication in a human rights abuse, it raises important questions about the effectiveness of the implementation of the `Leahy laws <https://www.state.gov/key-topics-bureau-of-democracy-human-rights-and-labor/human-rights/leahy-law-fact-sheet/>`_, which are a vetting and due diligence processes in place to prevent this from happening. 

These questions can in part be answered by looking at the joint Department of State and Department of Defence report, "Foreign Military Training and DoD Engagement Activities of Interest". Released annually since 2000 (the 2000 report covered the U.S. government's fiscal year 1999-2000) this important, statutorily-mandated report shows in great detail how the US has spent much of its training and assistance budget, and with what aims. Generally, the US Department of State will release these reports as PDFs. They  can be found at the following locations online:

 * FY 2016-2017 to FY 2020-2021 and onwards are available `here <https://www.state.gov/foreign-military-training-and-dod-engagement-activities-of-interest>`_
 * FY 1999-2000 to FY 2015-2016 are officially archived `here <https://2009-2017.state.gov/t/pm/rls/rpt/fmtrpt/index.htm>`_

Training activities that were completed in each fiscal year are recorded in Volume I: Section IV of the report, mostly in tabular form. For most years this data includes the name of the training course, the trainee unit, their country, the exact start and end date of the training, and so on. We include more detail on this below.

The value of the data is high, but its accessibility is low because of the way the data are published. To establish, for example, every training a single student unit had received since 1999, an analyst would have to manually search over 80 different PDFs.

This project addresses this challenge by providing clean, accurate and standardized machine-readable copy of all the data contained in the reports. We also aim to provide a simple and effective way for anyone to search the data and retrieve it in a standard, easy to use format. Importantly, we also show how the data were created and processed, keeping a direct link between the original report and the data. We also wanted to create a way to quickly update and analyse the dataset with each new release from the Department of State.

Longer term, our aim is to extend this dataset to include non-US security assistance and training, including that provided bilaterally by governments, and by international organizations like the United Nations and the European Union. 

We also intend to integrate this dataset with the information on our  WhoWasinCommand.com platform, which will give our community even greater insight into who has provided support to the security forces they are researching. 