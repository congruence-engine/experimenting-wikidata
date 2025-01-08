# Wikidata Tutorial - Congruence Engine

## Overview
This brief tutorial outlines steps taken by the Congruence Engine team to upload batches of museum objects and related terms to Wikidata. It is intended for museum professionals and other researchers interested in making their collections more linkable and accessible, in line with the principles of Linked Open Data. 


## What is Wikidata?
Wikidata is a free and collaborative online knowledge base maintained by the Wikimedia Foundation. Unlike Wikipedia, which consists of text articles about notable objects, places, people etc, Wikidata contains structured data which is formatted according to strict rules. 

Each Wikidata entry consists of a series of 'statements' which align with the Resource Description Framework (RDF). These statements take the form of triples, which is a method of describing relationships across entities in a way that is machine-readable.

To take one example, the Wikidata entry for Jan van Eyck's famous Arnolfini Portrait (Q127784950) contains the following statements:
instance of -> painting
inception -> 1434
location -> National Gallery
creator -> Jan van Eyck

Most of these represent links to other wikidata entries, making Wikidata a rich connected web of real-world entities and concepts. Unlike many controlled vocabularies and thesauruses which cultural heritage workers are familiar with, such as Getty's Art and Architecture Thesaurus (AAT), Wikidata does not have a way of representing hierarchies other than through the 'instance of' and 'subclass of' statements. For example, 'painting' is a subclass of 'two-dimensional visual work', which in turn is a subclass of 'visual artwork'. 'Painting' is thus connected (and hierarchically subsumed) to 'visual artwork', even while there is not a single statement or class that links the two directly. 

In order to begin contributing to Wikidata, you will need to [create a wikidata account](https://www.wikidata.org/w/index.php?title=Special:CreateAccount&returnto=Wikidata%3AMain+Page). 

## Wikidata's potential for cultural heritage organisations

## Wikidata or Wikibase?
Depending on the size, scale, and intended use of your project, you may wish to create a separate Wikibase instead of uploading items directly to Wikidata. Wikibase is essentially the 'software' that underpins Wikidata, enabling you to upload and display structured data easily. Most of the same tools that we discuss later in this tutorial, including QuickStatements and the Query Service, can be run on Wikibase as well as Wikidata. Once you become comfortable in one, you will be able to perform the same actions in the other. Previously starting your own Wikibase required a fair amount of prior knowledge and infrastructure, but today it is possible to quickly set up Wikibase instances via [Wikibase Cloud](https://www.wikibase.cloud/). 

There are advantages and disadvantages to using Wikibase over Wikidata, depending on your project. For instance, you may wish to use Wikibase if:
* You have a large volume of domain-specific data which might be too large for Wikidata
* You would like greater flexibility over data modelling, including creating customised fields
* You are working on a specific project whose data you would like to have a separate and distinct home

Wikibase can also offer a good opportunity to experiment with Wikidata's core functionalities, without interacting with or editing Wikidata's information in the process. 

On the other hand, one of the core attractions of Wikidata is its open nature and interoperability. The custom ontologies created by Wikibase instances, meanwhile, can sometimes make it difficult to link records across instances. Facilitating precisely those links has been the concern of one recent project, [Wikibase World](https://wikibase.world/wiki/Project:Home).

## Congruence Engine 
Congruence Engine worked with Wikidata and Wikibase at several points in time and across multiple investigations. The present tutorial emerged out of experiments conducted by the team which sought to understand how museum professionals and other interested individuals might use Wikidata as a way to facilitate links across museum collections. For this work, we experimented with a sample of objects drawn from three museum collections:
* Bradford Industrial Museum
* National Wool Museum, Wales
* Science Museum, London

We collected a dataset which combined records relating to textile machinery holdings in each museum, which served as the basis for our experiments. 

The key research questions of our experiment were as follows:
* What potential does Wikidata hold for linking museum objects across institutions?
* How can museum curators and researchers enhance Wikidata in order to better facilitate linkage?
* What technical barriers exist currently which might prevent curators from contributing to Wikidata?


## Preparing your data
You may be reading this tutorial simply to get to grips with the basics, but you may also wish to try out some of the steps below on data of your own. All you will need is an excel spreadsheet with a list of terms - in our case we worked with the catalogue names of museum objects, but you could use a list of businesses, people, places etc. depending on your project. You will need to prepare these as an excel spreadsheet or CSV file, and it is good practice to assign unique identifiers to each term at this stage.  

## Reconciling with OpenRefine
The first step for establishing the relationship between your data and that which already exists on Wikidata is via a software tool called OpenRefine. OpenRefine is a powerful tool with multiple different uses, but here we will focus principally on the 'reconciliation' feature. If you want to learn more about the general functionality of OpenRefine, please read [the documentation](https://openrefine.org/docs). 

'Reconciling' data means checking for matches between the text in your own data and that of a knowledge base such as Wikidata. OpenRefine enables users to reconcile data with Wikidata as well as custom Wikibases and certain thesauri. 

In the context of uploading material to Wikidata, reconciling is a particularly important step because it minimises the risk of a user adding terms that already exist into the knowledge base. 

### Steps
1. Load your file into OpenRefine. If you want to test with an example file, you can use [this one](general_items_QuickStatements).
2. Identify the column containing the terms which you wish to reconcile. In our case, this is the one titled 'object_label'. Click on the blue triangle beside the column label, and select 'Reconcile' > 'Start reconciling...'. 
3. You will now be asked to select a service to reconcile against. Select 'Wikidata reconci.link' (usually the first option). Click next. 
4. You will be prompted to select an entity 'type' to reconcile your terms against. This can help to ensure that you don't get as many false positives, but it is not always necessary. For this test we will select 'Reconcile against no particular type'. Make sure also that the 'Auto-match candidates with high confidence' box is selected.
5. You can now click 'Start reconciling...', and the reconciliation will start to work its magic. A yellow box at the top of the page will show progress as a percentage.  
6. Once the reconciliation is finished, you can view your results.
7. For those instances where there is a clear match, the term will now be viewable as a blue link. You can peek at the matched Wikidata item by hovering over these links, or you can investigate the full Wikidata item by clicking on them. For entries where a match was not obvious, you will be presented with a list of potentials.
8. Beside each potential candidate, you will see two icons: one is a single tick, and the other is a double tick. Clicking on the single tick will match the cell's value to the item identified in Wikidata; clicking on the double tick will match *all* instances of that value to the Wikidata item. 

Once you have reconciled all the available terms in your dataset, you can start creating new items for those items where no match was found. Please note that if you were using the sample spreadsheet discussed above, you will not be able to use this to create new items, as this includes only examples for which we have already created Wikidata items. 

In order to export only the unmatched items, you can choose 'Reconcile' > 'Facets' > 'By judgement'. A box will appear to the left of the screen, enabling you to filter the data based on 'matched' and unmatched ('none') entities. Click on 'none' to show only the unmatched entities. Now, when you export a file type of your choice, you will be left with a new file with only the unmatched entities. You can use this new file to start preparing new Wikidata items. 

**Note:** If you are using the reconciliation service simply to identify matches between your collections data and Wikidata, there are a few things that you can do with the post-reconciliation data in OpenRefine. The 'Reconcile' menu includes options to 'Copy reconciliation data' to a different column, or to add new columns with either the corresponding Qcodes ('add entity identifiers column...') or the URL to the matched Wikidata items ('add column with URLs of matched entities...'). 


## Creating New Wikidata items
Now that you have your list of new items to add to Wikidata, it's time to prepare your data. New Wikidata items can be [created manually](https://www.wikidata.org/wiki/Special:NewItem), but when working with batches of data it is better to use an online tool called QuickStatements. 

QuickStatements allows you to add or edit new items to Wikidata in batches, with as much or as little detail as you wish. One of the great advantages of QuickStatements is the ability to subsequently edit batches or parts of batches: this means that while you may only wish to add a select number of statements in your first upload, you (or another user) can add further detail later on. 


### Generating descriptions automatically
The minimum requirements to add a new item to Wikidata are as follows:
1. Language: the input language you are using to create the item
2. Label: the name of the item
3. Description: a brief definition of the item

One of the biggest bottleknecks to adding large amounts of terms to Wikidata is the need to provide a description. In most cases, this needs to be created manually, unless you are working with data which features an existing definition. 

In our experiments, we tested the possibility of using a Large Language Model (LMM) to automatically generate the description fields for new items, thus substantially speeding up the process. We used Chat GPT to create around 50 definitions of specialised textile machinery terms, which were subsequently checked by a domain expert, who was satisfied with the results in all but a couple of cases. 

### Preparing your data for QuickStatements
The easiest way to prepare your data for QuickStatements is using a spreadhseet. 

### Using QuickStatements
