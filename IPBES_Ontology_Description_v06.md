# The IPBES Ontology

**Prepared by Maral Dadvar and Aidin Niamir** 
  
**Contributors: Dave Thau, Benedict Omare and Renske Gudde** 


*For any inquires please contact
[aidin.niamir\@senckenberg.de](mailto:aidin.niamir@senckenberg.de)*

Version: 06 
Last Updated: May 12, 2025

DOI: [10.5281/zenodo.10404413](https://zenodo.org/doi/10.5281/zenodo.10404413) 

## Abstract

The ontology developed for representing intergovernmental reports and the broad topics and information that they cover.

## Table of content
1. Introduction
2. Namespace Declarations
3. The IPBES Ontology Description
4. Classes and Attributes
5. References

## 1. Introduction
The Intergovernmental Science-Policy Platform on Biodiversity and Ecosystem Services (IPBES) is the intergovernmental body which assesses the state of biodiversity and of the ecosystem services it provides to society, in response to requests from decision makers. To this end, it produces regular regional, national and global assessment reports in collaborations with many experts, scientists and politicians from a wide range of expertise, nationalities and backgrounds. To our knowledge, there is no existing ontology for representation of intergovernmental reports and the broad topics and information that they cover. To this end, we have created the IPBES ontology as the stepping stone for representing these types of data as LOD and make them accessible for further exploration.

## 2. Namespace Declarations
This is the list of the namesspaces used in this ontology.

| namespace prefix | namespace URI |
| --- | --- | 
| ipbes | <https://ontology.ipbes.net/report/> |
| foaf | <http://xmlns.com/foaf/0.1/> |
| skos | <http://www.w3.org/2004/02/skos/core#> |
| owl | <http://www.w3.org/2002/07/owl#> |

## 3. The IPBES Ontology Description
The classes and properties used in IPBES ontology are created on the fly based on the information that we encounter and the concepts that we aimed to represent. However, the usage of the properties is consistent and the coined URI’s are stable and unique. Currently our ontology consists of 6 classes, each representing a specific part of the data along with their corresponding attributes.


## 4. Classes and Attributes

| Classes |   |   |   |   |   |   |   |   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| [Report](#Report) | [Chapter](#Chapter) | [SubChapter](#Subchapter) | [KeyMessage](#KeyMessage) | [BackgroundMessage](#BackgroundMessage) | [SubMessage](#SubMessage) | [Illustration](#Illustration) | [Reference](#Reference) | [KnowledgeGap](#KnowledgeGap) | [Person](#Person) |


#### <a id="Report"></a>Report
| Class |   |
| --- | --- |
| *ipbes.Report* | <http://ontology.ipbes.net/report> |

|Properties|    |
| --- | --- |
| *skos:prefLabel* | The label that is preferred to be used for a chapter, sub-chapter, report or person | 
| *Skos:altLabel* | Alternative writing format or language of the preferred label |
| *ipbes:year* | The publication year |
| *ipbes:hasDoi* | The DOI number |
| *foaf.Person* | The list of co-chairs of this report|


#### <a id="Chapter"></a>Chapter
| Class |   |
| --- | --- |
| *ipbes.Chapter* | <http://ontology.ipbes.net/data/ch/> |

|Properties|    |
| --- | --- |
| *skos:prefLabel* | The label that is preferred to be used for a chapter, sub-chapter, report or person | 
| *ipbes:Report* | Link to the class Report of the chapter |
| *ipbes:hasDoi* | The DOI number |
| *dcterms:identifier* | The identifier of the chapter or sub-chapter or key message in the report | 
| *foaf.Person* | The list of persons who have a role in this chapter |


#### <a id="Subchapter"></a>Sub-chapter
| Class |   |
| --- | --- |
| *ipbes.SubChapter* | <http://ontology.ipbes.net/report/sch/> |

|Properties|    |
| --- | --- |
| *dcterms:identifier* | The identifier of the chapter or sub-chapter or key message in the report  | 
| *ipbes:Chapter* | Link to the class Chapter of the sub-chapter |
| *ipbes:Report* | Link to the class Report of the sub-chapter |
| *ipbes:KeyMessage* | Link to the class KeyMessage for which the sub-chapter has been referred to |
| *ipbes:Reference* | Link to the class reference for the citations used in each subchapter |
| *skos:prefLabel* | The label that is preferred to be used for a chapter, sub-chapter , report or person |
| *ipbes:hasDescription* | The text that further describes the content |


#### <a id="KeyMessage"></a>Key message
| Class |   |
| --- | --- |
| *ipbes.KeyMessage* | <http://ontology.ipbes.net/report/key/> |

|Properties|    |
| --- | --- |
| *ipbes:BackgroundMessage* | Link to the class BackgroundMessage which the key message has been referred to  | 
| *dcterms:identifier* | The identifier of the chapter or sub-chapter or key message in the report  |
| *ipbes:Report* | Link to the class Report of the key message |
| *skos:prefLabel* | The label that is preferred to be used for a chapter, sub-chapter, report or person |
| *ipbes:hasDescription* | The text that further describes the content  |
| *ipbes:hasEstablishedIncomplete* | Level of confidence |
| *ipbes:hasWellestablished* | Level of confidence |
| *ipbes:hasUnresolved* | Level of confidence |
| *ipbes:hasInconclusive* | Level of confidence |


#### <a id="BackgroundMessage"></a>Background message
| Class |   |
| --- | --- |
| *ipbes.BackgroundMessage* | <http://ontology.ipbes.net/report/bgm/> |

|Properties|    |
| --- | --- |
| *ipbes:SubMessage* | Link to the sub-messages used in each background message | 
| *dcterms:identifier* | The identifier of the chapter or sub-chapter or key message in the report  |
| *ipbes:Report* | Link to the class Report of the key message |
| *skos:prefLabel* | The label that is preferred to be used for a chapter, sub-chapter, report or person |
| *ipbes:hasDescription* | The text that further describes the content  |
| *ipbes:hasEstablishedIncomplete* | Level of confidence |
| *ipbes:hasWellestablished* | Level of confidence |
| *ipbes:hasUnresolved* | Level of confidence |
| *ipbes:hasInconclusive* | Level of confidence |


#### <a id="SubMessage"></a>Sub-message
| Class |   |
| --- | --- |
| *ipbes.SubMessage* | <http://ontology.ipbes.net/report/subm/> |

|Properties|    |
| --- | --- |
| *dcterms:identifier* | The identifier of the chapter or sub-chapter or key message in the report |
| *ipbes:hasDescription* | The text that further describes the content |
| *ipbes:SubChapter* | Link to class SubChapter. Use for subchapters mentioned in the sub-message |
| *ipbes:Illustration* | Link to class Illustration. Used for mentioned tables, figures or boxes in the sub-message |
| *ipbes:hasEstablishedIncomplete* | Level of confidence |
| *ipbes:hasWellestablished* | Level of confidence |
| *ipbes:hasUnresolved* | Level of confidence |
| *ipbes:hasInconclusive* | Level of confidence |


#### <a id="Illustration"></a>Illustration
| Class |   |
| --- | --- |
| *ipbes.Illustration* | <http://ontology.ipbes.net/report/il/> |

|Properties|    |
| --- | --- |
| *dcterms:identifier* | The identifier of the chapter or sub-chapter or key message in the report |
| *skos:prefLabel* | The label that is preferred to be used for a chapter, sub-chapter, report or person |
| *ipbes:hasDescription* | The text that further describes the content |
| *ipbes:hasDoi* | The DOI number |
| *owl:sameAs* | Link to other resources such as the zotero repository of the reference |


#### <a id="Reference"></a>Reference

| Class |   |
| --- | --- |
| *ipbes.Reference* | <http://ontology.ipbes.net/report/ref/> |

|Properties|    |
| --- | --- |
| *ipbes:Chapter* | Link to the class Chapter in which the reference has been used |
| *ipbes:Report* | Link to the class Report |
| *ipbes:SubChapter* | Link to the class SubChapter in which the reference has been used |
| *owl:sameAs* | Link to other resources such as the zotero repository of the reference |
| *ipbes:hasDescription* | The text that further describes the content | 
| *ipbes:hasDoi* | The DOI number |


#### <a id="KnowledgeGap"></a>KnowledgeGap

| Class |	|
| --- | --- |
| *ipbes.KnowledgeGap* | <http://ontology.ipbes.net/report/kg/> |

|Properties|    |
| --- | --- |
| *ipbes:Report* | Link to the class Report |
| *ipbes:SubChapter* | Link to the class SubChapter in which the knowledge gap was described |
| *ipbes:hasDescription* | The text that further describes each knowledge gap that is related to the subchapters mentioned in the text | 
| *dcterms:identifier* | The identifier of the sub-chapter or illustration mentioned in description |


#### <a id="Person"></a>Person
| Class |   |
| --- | --- |
| *foaf.Person* | http://ontology.ipbes.net/report/person/ |

|Properties|    |
| --- | --- |
| *foaf:firstName* | First name of the person |
| *foaf:lastName* | Family name of the person |
| *ipbes:Chapter* | Link to the class Chapter in which the person has a role |
| *ipbes:Report* | Link to the class Report |
| *skos:prefLabel* | The label that is preferred to be used for a chapter, sub-chapter, report or person |
| *owl:sameAs* | Link to other resources about the person, such as ORCID |
| *ipbes:country* | Country of residence of the person |
| *ipbes:ca* | Contributing authors in the stated chapter and report |
| *ipbes:cl* | Coordinating lead authors in the stated chapter and report |
| *ipbes:fl* | Fellows in the stated chapter and report |
| *ipbes:cs* | Co-chairs in the stated chapter and report |
| *ipbes:la* | Lead authors in the stated chapter and report |
| *ipbes:re* | Review editors in the stated chapter and report |



## 5. References
https://www.w3.org/2009/08/skos-reference/skos.html

http://xmlns.com/foaf/0.1/ 


