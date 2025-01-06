## Wikidata Tutorial - Congruence Engine

# Overview
This brief tutorial outlines steps taken by the Congruence Engine team to upload batches of museum objects and related terms to Wikidata. It is intended for museum professionals and other researchers interested in making their collections more linkable and accessible, in line with the principles of Linked Open Data. 


# What is Wikidata?
Wikidata is a free and collaborative online knowledge base maintained by the Wikimedia Foundation. Unlike Wikipedia, which consists of text articles about notable objects, places, people etc, Wikidata contains structured data which is formatted according to strict rules. 

Each Wikidata entry consists of a series of 'statements' which align with the Resource Description Framework (RDF). These statements take the form of triples, which is a method of describing relationships across entities in a way that is machine-readable.

To take one example, the Wikidata entry for Jan van Eyck's famous Arnolfini Portrait (Q127784950) contains the following statements:
instance of -> painting
inception -> 1434
location -> National Gallery
creator -> Jan van Eyck

Most of these represent links to other wikidata entries, making Wikidata a rich connected web of real-world entities and concepts. Unlike many controlled vocabularies and thesauruses which cultural heritage workers are familiar with, such as Getty's Art and Architecture Thesaurus (AAT), Wikidata does not have a way of representing hierarchies other than through the 'instance of' and 'subclass of' statements. For example, 'painting' is a subclass of 'two-dimensional visual work', which in turn is a subclass of 'visual artwork'. 'Painting' is thus connected (and hierarchically subsumed) to 'visual artwork', even while there is not a single statement or class that links the two directly. 

In order to begin contributing to Wikidata, you will need to [create a wikidata account](https://www.wikidata.org/w/index.php?title=Special:CreateAccount&returnto=Wikidata%3AMain+Page). 


# Wikidata or Wikibase?
Depending on the size, scale, and intended use of your project, you may wish to create a separate Wikibase instead of uploading items directly to Wikidata. Wikibase is essentially the 'software' that underpins Wikidata, enabling you to upload and display structured data easily. Most of the same tools that we discuss later in this tutorial, including QuickStatements and the Query Service, can be run on Wikibase as well as Wikidata. Once you become comfortable in one, you will be able to perform the same actions in the other. Previously starting your own Wikibase required a fair amount of prior knowledge and infrastructure, but today it is possible to quickly set up Wikibase instances via [Wikibase Cloud](https://www.wikibase.cloud/). 

There are advantages and disadvantages to using Wikibase over Wikidata, depending on your project. For instance, you may wish to use Wikibase if:
* You have a large volume of domain-specific data which might be too large for Wikidata
* You would like greater flexibility over data modelling, including creating customised fields
* You are working on a specific project whose data you would like to have a separate and distinct home

Wikibase can also offer a good opportunity to experiment with Wikidata's core functionalities, without interacting with or editing Wikidata's information in the process. 

On the other hand, one of the core attractions of Wikidata is its open nature and interoperability. The custom ontologies created by Wikibase instances can sometimes make it difficult to link records across instances, although facilitating precisely those links has been the concern of one recent project, [Wikibase World](https://wikibase.world/wiki/Project:Home).  

# Congruence Engine experiments 
Congruence Engine worked with

# Preparing your data

# Using QuickStatements



[https://www.wikidata.org/w/index.php?title=Special:CreateAccount&returnto=Wikidata%3AMain+Page]: https://www.wikidata.org/w/index.php?title=Special:CreateAccount&returnto=Wikidata%3AMain+Page