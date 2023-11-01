Overview: Location
##################

What are Locations?
-------------------

Locations are unique places or positions. A named town or city can be a Location, as can an administrative area like a county, district or state. In fact, anything that be drawn on a map can be a Location: a specific point, a section of a road, a military line of control, and so on.

Locations are the way we sketch out the geographical footprint of security units. We use Locations to describe the "sites" and "areas of operation" of :ref:`Units`. Locations describe security forces' infrastructure (bases, facilities, checkpoints, air fields, bunkers), as well as their territorial jurisdictions and operations as they change over time. We also use Locations to describe the places where security force units are alleged to have committed human rights abuses.

In the Security Force Monitor (SFM) data model, Locations are a discrete set of datapoints that can be referenced in other parts of the dataset. 


.. figure:: _static/location_general_concept.png
   :width: 95%
   :figwidth: 100%
   :align: center
   :alt: Chart from the Security Force Monitor Research Handbook that describes what Locations are, and how they work in the Security Force Monitor research approach.

To define a Location, we start with information included in the sources contain the claims on which our research is based (see :ref:`What is a claim?` and :ref:`Sources`). The Location descriptions contained in sources vary greatly in their precision and accuracy:

 - At a precise coordinate: "Artillery Brigade deployed to latitude x, longitude y".
 - At a very specific place: "Has a checkpoint on the corner of street A and street B in Test Town".
 - At a very specific named place: "Based at Famous General Army Camp in Test Town".
 - At a nonspecific place in a particular settlement: "In Test Town".
 - In a named subdivision of a particular settlement: "Suburb A in Test Town".
 - In a named but nonspecific place near a particular settlement: "At the Smoth family borehole north of Test Town"
 - In a nonspecific place near a particular settlement: "Around Test Town".
 - In a definable area that is not a settlement: "In Test County".
 - In an area that is difficult to define: "Somewhere in the north of the country"

When we have decided on what Location is actually described in the source, we use Location attributes to capture and structure data about that place. In most cases, we  do this by consulting existing sources of geospatial information. Our first source for geographical information is `OpenStreetMap <https://openstreetmap.org>`_. We can also consult other geospatial datasets such as those published on `Humanitarian Data Exchange <https://data.humdata.org/>`_, a number of commercial mapping services such as Google Maps, and (where they exist) original data provided by the relevant national geospatial agencies. We reconcile the information we gain from the sources with options provided to us by a number of geospatial information sources, which we then turn into a Location we can use in the dataset.

For example. if a source describes a place called "Potiskum" in Yobe State, Nigeria we can `look it up on OpenStreetMap <https://www.openstreetmap.org/node/255322295>`_. From this record, we can capture the Location's name, object ID number (``255322295``) and its geometry type ( a "node", which is a "point" for our purposes). We enter this basic data about the Location into the Location fieldset, generate a UUID for it (``41b3aec7-d88e-4ef1-a7d8-1b7fdf81a20c``), and create a "human readable" key that we can then use to reference this specific Location in other parts of the data model (``Potiskum (osm, point) 41b3aec7-d88e-4ef1-a7d8-1b7fdf81a20c``).

We can then use additional tools to get more information directly from OpenStreetMap about this Location, including its geometry (in this case, a coordinate pair), additional metadata (such as a name in Arabic or other local languages), and the various adminstrative areas (like states, local government areas, wards) in which it is sited. This additional information enables us to plot the Location on a map, such as in the image below snapped from our our WhoWasInCommand platform.


.. figure:: _static/potiskum_location_example_1.png
   :width: 95%
   :figwidth: 100%
   :align: center
   :alt: A screenshot from WhoWasInCommand showing that Joint Take Force Operation Restore Order III has a "site" in Potiskum, and an area of operation in the Nigerian state of Yobe.


Where there is not a good option in an existing geospatial data source, and where the source contains sufficient descriptive information, we can create the Location data directly using a Geographical Information System (GIS) tool like QGIS, Earth Pro or Google My Maps. This method is useful for describing Locations that may emerge from geolocation processes, such as views portrayed in images and other subjective descriptions of a place.

We create a datasets of Locations for each country we work on. 
