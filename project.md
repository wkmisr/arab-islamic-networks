---
layout: page
title: Project
permalink: /project/
---
## The question

What resources did people in the Arabic-speaking world draw on to build and keep up their social networks, and how did they do it? Biographical dictionaries record exactly this kind of evidence: who studied with whom, who held which post, who married into which family, who travelled where. The project asks the question of the Mamluk period (1250–1517), when soldiers of slave origin ruled Egypt, Syria and the Hijaz together with scholars, city notables and rural elites.

## The problem

Earlier work has read these dictionaries closely, but mostly for famous people and well-known events. The sources are large, and the people in them are not identified consistently from one project to the next. Variant spellings of Arabic names and the gap between historical and modern place names make the work of matching people by hand slow. That gap is why so many ordinary members of the elite, the scholars and officials of middling rank, have stayed out of sight.

Advances in AI now let machines and humans share this work: machines propose identifications and normalise spelling variants, and scholars judge the results. AINet-DB is built on that division of labour.

## Three parts

<span id="a"></span>**A. An integrated biographical database.** Two dictionaries are encoded in TEI-XML with a shared identifier system: al-Sakhāwī's *al-Ḍawʾ al-Lāmiʿ* (15th century, 12 volumes, nearly 14,000 people) and Ibn Ḥajar's *al-Durar al-Kāmina* (14th century, 4 volumes, about 6,000 people). Chronicles and other sources are consulted when a person or a work cannot otherwise be identified.

<span id="b"></span>**B. Structure and extensibility.** The amount and kind of information differ between centuries and regions. By studying the geographical and occupational make-up of each dictionary, the project designs a database that can take in further dictionaries. For comparison it looks to al-Andalus, using a history of Granada compiled at about the same time.

<span id="c"></span>**C. Social relations and comparison.** From life events such as study, appointment, marriage and travel, the project maps ties between people, institutions, offices and places. It then asks how the networks of soldiers, scholars, Sufis and merchants relate to the political and social order.

## What is new

- **Events as the unit of evidence.** Recording people and life events lets the same data serve close reading of one entry and analysis of whole networks.
- **Identifiers others can reuse.** Each person and place gets one identifier, with its uncertainty and source stated openly, so later studies can build on it.
- **Human judgment with machine processing.** The project develops a method for combining the two, one that can be applied to other regions and periods.

## Four-year plan

| Year | Work |
|---|---|
| 1 | Build a sample of 3,000 people from *al-Ḍawʾ al-Lāmiʿ*. Draft the design guidelines: identifiers and tagging. Test AI-assisted extraction. |
| 2 | Encode the remaining 10,000 or so people and complete the 15th-century database. Hold an international workshop. |
| 3 | Encode *al-Durar al-Kāmina* and begin the comparison between the 14th and 15th centuries. |
| 4 | Release a beta version of the integrated 14th–15th century database. Publish the comparative results and hold an international symposium. |

## Standards and openness

- Each biography is a TEI-XML document; the data are also published as RDF.
- Links to Wikidata, VIAF and GeoNames connect the database to existing resources. Data from the Mamluk Prosopography Project (about 4,000 people) and from *Prosopografía de los ulemas de al-Andalus* (more than 30,000 scholars) will be brought in under the same identifiers.
- The work is versioned with Git. Datasets are planned to be released with DOIs under a CC BY licence, in an institutional repository and an international one.

## Related work

The project builds on the KITAB project's digitised Arabic corpus, and on computational studies of biographical collections such as Maxim Romanov's network analysis of scholars' movements between cities (2017). AINet-DB differs in scale and method: where large-scale analysis takes in hundreds of thousands of records at once, this project checks each record against its source and reads the structure of each entry with care.

"AINet-DB" is a working title.
