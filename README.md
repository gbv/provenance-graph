# Provenance Graph

> Ideas to create a knowledge graph with provenance information about objects 

**[Provenance](https://en.wikipedia.org/wiki/Provenance)** is the chronology of the ownership, custody or location of a historical object. Objects include works of art, publications and artifacts in scientific collections. Data provenance (aka *data lineage*) is not covered here.

## Resources

### Germany

- [Thomas Schneider](https://orcid.org/0000-0001-5592-6183) has written the master's thesis *Modelling and Automated Retrieval of Provenance Relationships* in library and information science at Humboldt University Berlin, to be published in 2023

- There is a German library working group on provenience with focus on rare books. They manage [a public wiki](https://provenienz.gbv.de/) and have regular meetings.

- [Proveana](https://www.proveana.de/) is a database at the German Lost Art Foundation with focus on Nazi-looted art, wartime losses and related areas.

- The German Digital Library (DDB) plans to do something with provenance information as well

### International

...

## Data models and formats

- K10plus cataloging format and rules (see below)
- MARC21 field [561](https://www.loc.gov/marc/bibliographic/bd561.html) and [361](https://www.loc.gov/marc/bibliographic/bd361.html). There is no mapping to BIBFRAME yet (only parts of field 561).
- [BIBFRAME Ontology](https://id.loc.gov/ontologies/bibframe.html) contains property `custodialHistory` with literal value. There is a proposal to extent this to object type `CustodialHistory` from [Art and Rare Materials Core Ontology](https://art-and-rare-materials-bf-ext.github.io/arm/v1.0/ontology/arm_1_0.html#CustodialHistory). [Further plans](https://ld4p.github.io/arm/modeling_recommendations/custodial_history.html) with more extension based on a [Custodial History Ontology](https://art-and-rare-materials-bf-ext.github.io/arm/v0.1/custodial_history/ontology/0.1/custodial_history.html) have been developed in the LD4P project (2016-2018) but seem to not been followed yet. The [RBMS Committee](https://rbms.info/committees/bibliographic_standards/) might still work on this.
- Linked Art contains a [provenance model in RDF](https://linked.art/model/provenance/) based on CIDOC-CRM. This model is also going to be applied to the [Getty Provenance Index](https://www.getty.edu/research/tools/provenance/index.html) (see [here on updates](https://www.getty.edu/research/tools/provenance/provenance_remodel/index.html))

More research is needed to find out how provenance is handled in sciences for other types of objects. For instance archeology or tracing of meteorites from their origin in the solar system to finding, aquisition and exhibition (to answer questions like "where are pieces of mars publically exhibited and how did they get there?").

### Abstract data model

A very abstract data model of provenance information could be summarized with entity types and relation types like this:

- **Items**: individual physical objects
- **Works**: abstract works of art, connected to items via **exemplar** relation (in most cases this only applies to publications)
- **Agent**: a person or organization
- **Collection**: a set of items
- Relations such as **owned**, **aquired**, **saled**, **part-of**... with optional qualifiers of time and sources to justify the claim (depending on the modeling language, such relations could also be **Event** entities)

The data model could be extened with further relations beyond provenance information, e.g. **creator**, **collaborator**, **reader**...

This or a similar abstract model needs to be expressed in RDF. A quick look at existing RDF ontologies shows that there are at least two competing ways of expression: from arts und museums (based on CIDOC-CRM) and from libraries (based on BIBFRAME and MARC21).

## Data sources

### K10plus

Provenance information is catalogued in K10plus union catalogue in [PICA+ field 092B](https://swbtools.bsz-bw.de/cgi-bin/k10plushelp.pl?cmd=kat&val=9100&katalog=Standard) and there is [a special input form](https://wiki.k10plus.de/display/K10PLUS/Eingabeformular+9100). Current data [can be inspected here](https://analytics.gbv.de/kxp/qa-catalogue/?tab=completeness#completeness-092B) (download available on request, some cleanup needed).

### Wikidata

*In Wikidata there is (at least some) data about everything*

...

### ...

...
