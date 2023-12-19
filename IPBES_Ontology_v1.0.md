---
title: "Technical Guideline Series"
output:
  pdf_document:
    toc: yes
  html_document:
    toc: yes
    fig_width: 7
    fig_height: 6
    fig_caption: true
    toc_float: yes
---

# The IPBES Ontology

**Prepared by Maral Dadvar and Aidin Niamir**
  
**Contributors: Dave Thau, Benedict Omare and Renske Gudde**

*For any inquires please contact
[aidin.niamir\@senckenberg.de](mailto:aidin.niamir@senckenberg.de)*

Version: 1.0   
Last Updated: December 19th, 2023

DOI: [10.5281/zenodo.10404414](https://doi.org/10.5281/zenodo.10404414) 

## Abstract

The ontology developed for representing intergovernmental reports and the broad topics and information that they cover.

## Table of content
1. Introduction
2. Namespace Declarations
3. The IPBES Ontology Description
4. Classes and Attributes
5. References

## 1. Introduction
The Intergovernmental Science-Policy Platform on Biodiversity and Ecosystem Services (IPBES) is the intergovernmental body which assesses the state of biodiversity and of the ecosystem services it provides to society, in response to requests from decision makers. To this end, it produces regular regional, national and global assessment reports in collaborations with many experts, scientists and politicians from a wide range of expertise, nationalities and backgrounds. 
To our knowledge, there is no existing ontology for representation of intergovernmental reports and the broad topics and information that they cover. To this end, we have created the IPBES ontology as the stepping stone for representing these types of data as LOD and make them accessible for further exploration.

## 2. Namespace Declarations
This is the list of the namesspaces used in this ontology.

| namespace prefix | namespace URI |
| --- | --- | 
| ipbes | <https://ontology.ipbes.net/report> |
| foaf | <http://xmlns.com/foaf/0.1/> |
| skos | <http://www.w3.org/2004/02/skos/core#> |

## 3. The IPBES Ontology Description
The classes and properties used in IPBES ontology are created on the fly based on the information that we encounter and the concepts that we aimed to represent. However, the usage of the properties consistent and the coined URI’s are stable and unique. Currently our ontology consists of 6 classes, each representing a specific part of the data along with their corresponding properties. 

## 4. Classes and Attributes

| Classes |   |   |   |   |   |
| --- | --- | --- | --- | --- | --- |
| [Report](#CReport) | [Chapter](#CChapter) | [Subchapter](#CSubchapter) | [KeyMessage](#CKeyMessage) | [Reference](#CReference) | [Person](#CPerson) |

#### <a id="CReport"></a>**Report**
| Class |   |
| --- | --- |
| *ipbes.Report* | <http://ontology.ipbes.net/report> |

|Properties|    |
| --- | --- |
| *skos:prefLabel* | The label that is preferred to be used for a chapter, sub-chapter , report or person | 
| *Skos:altLabel* | Alternative writing format or language of the preferred label |
| *ipbes:year* | The publication year |
| *ipbes:hasDoi* | The DOI number |

#### <a id="CChapter"></a>**Chapter**
| Class |   |
| --- | --- |
| *ipbes.Chapter* | <http://ontology.ipbes.net/report/ch/> |

|Properties|    |
| --- | --- |
| *skos:prefLabel* | The label that is preferred to be used for a chapter, sub-chapter , report or person | 
| *ipbes:Report* | Link to the class Report of the chapter |
| *ipbes:hasDoi* | The DOI number |
| *ipbes:identifier* | The identifier of the chapter or sub-chapter or key message in the report | 
| *foaf.Person* | The list of persons who have a role in this chapter |

#### <a id="CSubchapter"></a>**Subchapter**
| Class |   |
| --- | --- |
| *ipbes.SubChapter* | <http://ontology.ipbes.net/report/sch/> |

|Properties|    |
| --- | --- |
| *ipbes:identifier* | The identifier of the chapter or sub-chapter or key message in the report  | 
| *ipbes:Chapter* | Link to the class Chapter of the sub-chapter |
| *ipbes:Report* | Link to the class Report of the sub-chapter |
| *ipbes:KeyMessage* | Link to the class KeyMessage for which the sub-chapter has been referred to |
| *ipbes:reference* | Link to the class reference for the citations used in each subchapter |
| *skos:prefLabel* | The label that is preferred to be used for a chapter, sub-chapter , report or person |
| *ipbes:hasDescription* | The text that further describes the content |


#### <a id="CKeyMessage"></a>**Key message**
| Class |   |
| --- | --- |
| *ipbes.KeyMessage* | <http://ontology.ipbes.net/report/key/> |

|Properties|    |
| --- | --- |
| *ipbes:SubChapter* | Link to the class SubChapter in which the key message has been referred to  | 
| *ipbes:identifier* | The identifier of the chapter or sub-chapter or key message in the report  |
| *ipbes:Report* | Link to the class Report of the key message |
| *skos:prefLabel* | The label that is preferred to be used for a chapter, sub-chapter, report or person |
| *ipbes:hasDescription* | The text that further describes the content  |
| *ipbes:hasEstablishedIncomplete* | Level of confidence |
| *ipbes:hasWellestablished* | Level of confidence |
| *ipbes:hasUnresolved* | Level of confidence |
| *ipbes:hasInconclusive* | Level of confidence |

#### <a id="CReference"></a>**Reference**

| Class |   |
| --- | --- |
| *ipbes.Reference* | <http://ontology.ipbes.net/report/ref/> |

|Properties|    |
| --- | --- |
| *ipbes:Chapter* | Link to the class Chapter in which the reference has been used |
| *ipbes:Report* | Link to the class Report |
| *ipbes:SubChapter* | Link to the class SubChapter in which the reference has been used |
| *ipbes:zotero* | Link to the zotero repository of the reference |
| *ipbes:hasDescription* | The text that further describes the content | 
| *ipbes:hasDoi* | The DOI number |

#### <a id="CPerson"></a>**Person** 
| Class |   |
| --- | --- |
| *foaf.Person* | <http://ontology.ipbes.net/report/person/> |

|Properties|    |
| --- | --- |
| *foaf:firstName* | First name of the person |
| *foaf:lastName* | Family name of the person |
| *skos:prefLabel* | The label that is preferred to be used for a chapter, sub-chapter, report or person |
| *ipbes:orcID* | ORCID identifier of the person |
| *ipbes:country* | Country of residence of the person |
| *ipbes:ca* | Contributing authors in the stated chapter and report |
| *ipbes:cl* | Coordinating lead authors in the stated chapter and report |
| *ipbes:fl* | Fellows in the stated chapter and report |
| *ipbes:cs* | Co-chairs in the stated chapter and report |
| *ipbes:la* | Lead authors in the stated chapter and report |
| *ipbes:re* | Review editors in the stated chapter and report |

## 5. References
<https://www.w3.org/2009/08/skos-reference/skos.html>

<http://xmlns.com/foaf/0.1/> 


