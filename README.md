# Bharathi
Bharathi is a collection of linked data vocabularies for the Indian context linking the metadata of terms and inter-relationships across different entities within Government functions. In its current release, Bharathi contains information regarding Government Organizations at the Union Government & State Government level, the various Administrative Regions & its respective classifications, Sectors, Sub Sectors and common topics used frequently in the vocabulary of the Government functions.

# Introduction
This repository contains the extraction pipeline to populate Bharathi from the various sources of metadata existing in the public domain.

# Scope
The current version of Bharathi covers the following entities-
  1. 	Union Government Organizations
  2. 	Independent Departments
  3. Organizations of the Judiciary
  4. 	The legislatures and related organizations
  5. 	Organizations and Ministries
  6. 	Smart Cities
  7.	Organizations with in States and Union Territories
  8.	Census Codes for States and Districts
  9.	Sectors, Subsectors and Topics

Bharathi is generated as a conglomerate of the federated graphs of these data sources. Each of the graphs are generated using rdflib in python and the code to generate them can be found as individual jupyter-notebooks. 
# Build From Source
## Prerequisites
-	Python version 3.7
-	rdflib
-	pandas

## Build 
As the graphs are generated sequentially, the input to generate a federated graph are as follows: 
-	Raw data in csv format (<file>.csv)
-	Graph generated until the previous step (<graph>.nt)
Change the path to graph in cell number 2 for each jupyter notebook. The below code snippet is an example,
```
global g
g=rdflib.Graph()
g.parse('C:/MY PATH/Graph_union.nt', format='nt')
```
Change the path to raw file (csv) in cell number 3 for each jupyter notebook. The below code snippet is an example,
```
union_data=pd.read_csv("C:/MY PATH/unionupd.csv", header=None)
```
Change the path to serialize the graph in the below snippet, usually found at the end of the jupyter notebook. For example,
```
g.serialize(format='nt', destination='C:/MY PATH/Graph_Union_2.nt')
```
# Contributions
Bharathi aims to grow and enhance with crowd-sourced efforts. Contributions are welcome in following areas - 
-	Enhancing the Existing sources
-	Addition of new sources
-	Incorporating corrections

Please contact admin@semanticwebindia.com to contribute to Bharathi
