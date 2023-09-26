What is a claim?
################

A claim is an assertion of information evidenced by a source. 

The Monitor creates data from publicly available, mostly digital sources. We read and assess each source and turn the data we find in them into claims. Claims keep a piece of data together with the source from which it is derived, and may also tell us the time period for which the data  is valid. 

For example here is an excerpt from the news story `"Reshuffles in the military, war goes on”, published by the Shan Herald Agency for News (on the Burma News International website) on 10 September 2012 <https://www.bnionline.net/en/shan-herald-agency-for-news/item/13685-reshuffles-in-the-military-war-goes-on-.html>`_:


.. admonition:: Example

	Not only the government, but the military has been busy shuffling its commanders since the beginning of September, according to a source close to the War Office on Friday.

	At least 5 regional commanders and a number of Bureau of Special Operations (BSO) chiefs and division commanders have been moved to new jobs. They include:

	- Maj Gen Zeya Aung - Commander, Northern Region Command-to-Minister, Railway Transport
	- Brig Gen Aung Kyaw Zaw - Commander, Northeastern Region Command-to-Commander, Southern Region Command

	Their former commands were taken over by Central Eastern Region Command Commander Brig Gen Tun Tun Naung and head of the armed forces technical school Brig Gen Aung Soe respectively.


This source contains a mix of data that tells us something about the units of the Myanmar military and the people that hold positions in those units. The story contains data about the names of four persons: 

- Zeya Aung
- Aung Kyaw Zaw
- Tun Tun Naun
- Aung Soe

If we add information about their ranks, we can turn this data into a set of claims:

- The Shan Herald Agency for News claims that since the beginning of September 2012 a person called Zeya Aung had the rank of Maj Gen
- The Shan Herald Agency for News claims that since the beginning of September 2012 a person called Aung Kyaw Zaw had the rank of Brig Gen
- The Shan Herald Agency for News claims that at the beginning of September 2012 a person called Tun Tn Naun had the rank of Brig Gen
- The Shan Herald Agency for News claims that since the beginning of September 2012 a person called Aung Soe had the rank of Brig Gen

The source contains further claims about the military units to which each person has been posted. For example, the source now makes four claims about the person called “Aung Soe”:

- The Shan Herald Agency for News claims that at the beginning of September 2012 a person called Aung Soe has been a commander in the military.
- The Shan Herald Agency for News claims that since the beginning of September 2012 a person called Aung Soe had the rank of Brig Gen.
- The Shan Herald Agency for News claims that since the beginning of September 2012 a person called Aung Soe was head of a unit called the Armed Forces Technical School
- The Shan Herald Agency for News claims that since the beginning of September 2012 a person called Aung Soe became commander of a unit called the Northeastern Region Command

We can begin to express these claims more economically by using a set of standard fields. For example, we store the claimed name of a person in a field called “Person Name”, for example, to store their name:

- “Person Name” “Aung Soe”
- “Date of claim”: “September 2012”
- “Source of claim: ”Shan Herald Agency for News, 10 September 2012.

We can refine this further. In our system, claims have a range of different subjects: claims about the identity of a person, claims about a particular posting that a person has, claims about a unit’s identity or its relationships with others, and so on. Based on the type of information we’re pulling out from a source, we determine the type of claim that the source is making. So, data about a person’s name is a “Person Identity” claim type. 


.. csv-table::
   :file: _static/example-claim-as-table-A.csv
   :header-rows: 1
   :delim: tab


The data about the unit to which the person is posted is a “Person Posting” claim type: 


.. csv-table::
   :file: _static/example-claim-as-table-B.csv
   :header-rows: 1
   :delim: tab


From this point, we add shorter fieldnames to the claim to make it conform with the various data models we use. For example, a “Person Posting” claim type may include data about a person’s rank, role or title whilst posted to a unit, along with precise (or imprecise) dates for which this data are valid. 

We also add additional data about the claim itself, such as an identifier, that allows it to be managed in our technical systems. We also transform how the source is expressed, substituting the text for a specific identity number that cites the page, paragraph, line number (amongst others) in the source. The “look” of claim begins to change a bit, but this simply depends on the tool that is used to manage it. For example, here’s how this claim looks as a row in a spreadsheet:


.. csv-table::
   :file: _static/example-claim-as-row.csv
   :header-rows: 1
   :delim: tab


And here’s how the raw data looks in a database tool:

.. code::

	{:range-imprecise/first 1346457600000,
	 :entity/updated-at 1695045627318,
	 :meta/sheet-name :persons,
	 :range/starting? true,
	 :meta/extracted-by :sfm.data.formats.sheet.v1x/cluster:person:posting,
	 :entity/short-link "4c9cbf32",
	 :meta/status "3",
	 :meta/researcher "TW",
	 :entity/name "claim-4c9cbf32",
	 :claim/citation:ids [#uuid "9f01b1c1-563f-4b40-a534-b91c7e1a5062"],
	 :assertion/posting:unit:id
	 #uuid "dfe9a709-1a80-4bce-8040-68c6502b4f3e",
	 :entity/type :claim,
	 :entity/id #uuid "4c9cbf32-6de6-517b-8e44-e308fd27ad4c",
	 :claim/citation:refs [{:db/id 17592186130203}],
	 :assertion/posting:person:id
	 #uuid "bcce8f1d-8336-466c-be8e-c6074f96cde4",
	 :assertion/posting:rank "Brigadier General",
	 :range-imprecise/last 1348963200000,
	 :meta/latest-row-number 114,
	 :entity/spec :sfm.data.formats.records.claims.v1/claim,
	 :db/id 17592186095955,
	 :assertion/posting:role "Commander",
	 :claim/type :sfm.data.formats.records.claims.v1/posting,
	 :claim/about-entity:id #uuid "09a8dc6f-8f69-49cd-87f0-1eb996fb25db",
	 :entity/created-at 1695045627318,
	 :meta/spreadsheet-id "1PB3JNxpeCPlSy0GsJnElSiEPedfTzZuXk3AFHvrR58Y",
	 :range/starting-context "Appointed"}


The claim-based approach favors types of research - like that of Security Force Monitor - that involve the construct of a dataset from a wide range of different sources. In practice, this type of research means pulling data from thousands of different sources. The claim system keeps every single piece of data together with a citation of the specific source that evidence it, providing complete evidential transparency. It gives a two-way view showing all the sources that we have used to make a record about a specific person or unit, and also all the bits of data we have taken from specific sources (and exactly where in that source). It also affords us a fine degree of control over which specific pieces of data are used in any analysis. For example, we can exclude or include specific data points that have only official sources, or are only pulled  from specific publications. 

After creation, a claim is then aggregated with others into a record about a person, unit or other entity in the data model. In the present example, the data would be pulled together with other data about the person called “Aung Soe” - this could be other names that the person has used, units they were posted to, or incidents they have been involved in. These “aggregates” are then used in a wider analysis of the organization structure, history of commanders of a unit, and - perhaps most importantly - the construction of a command chain. 

The most useful things to read next are:

- How are claims aggregated into records?
- How do dates work in Security Force Monitor’s data?
- What are the rules for entering specific types of data?
- How do Locations work in Security Force Monitor’s data?
