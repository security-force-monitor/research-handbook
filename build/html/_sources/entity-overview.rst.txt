Our general data model
######################

Security Force Monitor investigates the conduct of security and defence forces around the world. We reconstruct their organisational structure, command personnel and chain of command, geographic footprint, and allegations of their involvement in committing human rights violations and violations of international criminal law. Further, we research the training and assistance that security and defence units have received from external security actors like the United States of America, the European Union, the United Nations, and through bilateral agreements with other states. All our information is drawn from sources that are nearly all online and in the public domain.

.. figure:: _static/sfm_general_data_model.png
   :width: 95%
   :figwidth: 100%
   :align: center
   :alt: Chart from the Security Force Monitor Research Handbook that describes the Monitor's general data model, including the main entities it collects informations about.

   
   ..

We use the general data model described in the above illustration to structure and organize the information we collect during the course of our research. It describes relationships between different "entities", which are logical groupings of data about a specific subject. For example, the "relation" entity is where we store data about the relationships between two different units;  culmulatively, all the records  of the "relation" entity type describe the hierarchical organizational structure that adopted by most security forces. 

Other sections of this Research Handbook expand on each of the entities and the relationships between these entities, including:

- A full description of each entity;
- The overall data structure and attributes we use for each entity;
- Examples on the types of data we enter into each attribute; and,
- Guidance on how we fill out each field and why. 

The diagram above also highlights the special place that "sources" and "claims" hold in our research approach. Security Force Monitor uses a claim-based approach to the creation of data. A claim is an assertion of information evidenced by a source. Throughout our work, all specific pieces of information about any entity are kept together with the specific source from which they were drawn.

This approach enables complete transparency about the origins of data, and is a powerful data integrity measure. All the data that comprise each record about each entity type are drawn from an aggregation of claims. This is discussed in much greater detail in the :ref:`What is a claim?` section of this Research Handbook. 

Finally, the general data model guides the construction of the technologies we have built to capture, store and analyse data.