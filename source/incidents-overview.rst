Overview: incidents
###################

What are incidents?
*******************

Incidents are publicly-documented allegations of acts committed by state-controlled security forces that may violate human rights laws and standards, international criminal law and other sets of relevant norms. 

Incidents may include extrajudicial killings, rape, torture and other forms of violence. Security Force Monitor does not make these allegations itself, but compiles allegations made by governmental bodies, human rights organizations and other civil society actors around the world.

The Security Force Monitor does not make allegations against security forces. Nothing in the Monitor’s work should be taken as an allegation made by the Monitor against a unit or person. In our work we treat all claims of human rights violations as “alleged” to indicate that these are claims that other organizations have made.

For each incident, we include a description of the incident from the organization making the allegation, and from this description we structure data for the alleged type of human rights violation(s), the alleged perpetrator(s), date range and the location where the alleged type of human rights violation occurred.

Each incident is stored in a claim, so we may have numerous claims about the same incident. In these cases, each claim would share the same entity id (``about_entity:ref:claim``), but the rest of the fields would tied to the information contained in the specific citation.

Data about incidents is captured in a single claim type:

- :ref:`Incident`: date, location, description, types of alleged human rights violations and alleged perpetrator information.
