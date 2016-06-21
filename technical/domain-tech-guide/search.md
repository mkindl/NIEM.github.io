---
title:  Search for NIEM data components
---

## How to search for NIEM data components

Although this section does not address NIEM modeling specifically, given the volume of NIEM, most modeling efforts will require searching the NIEM model for duplication, examples of content models, points of extension, etc.  This section introduces ome basic methods of searching for NIEM content. 


### Schema Subset Generation Tool (SSGT)

The Schema Subset Generation Tool (SSGT) is one way to search for NIEM data components.  This tool was designed to generate NIEM schema subsets, however, since the model is large, SSGT also contains a convenient search engine that can be used alone.   

#### Basic Search

In SSGT you can enter a search string and view a list of all NIEM data components that contain a lexical match to that string.  The default is to search a release in all its component names, definitions, and other metadata that match the string.  Note the namespaces are not part of the standard search.  This is because namespaces are extremely prevalent throughout the model and would therefore clutter most search results.  

SSGT will search a single release only.  The default is the most recent (current) operational release.  If you need to search a previous NIEM releasese you must select it from the "options" menu. 

SSGT requires that you declare the class of the data component you are searching for.  This means that you must declare you are searching for one of the following: 

- Property (the default class) - XSD data elements, attributes in a NIEM release.
- Type - XSD data types in a NIEM release; may be complex or simple.
- Namespace - namespaces used in a NIEM release
- Facet - class of code values in a  NIEM release.
- External - class of standards or profile of standards used in a NIEM release that are not NIEM conformant (e.g., GML). 
- Association - relationships among two or more objects.

Search results are displayed as a list of textual data component as qualified names (QNames; i.e., namespace prefix, colon, component name). 

A resulting list of data component names is sorted as follows:
1. All data names for which the search criteria matched a substring within the name (not including its namespace prefix),
are sorted first, alphabetically by namespace prefix, and second, within each namespace prefix group alphabetically by data name.
2. All data names for which the search criteria matched a substring within the associated data definition, are sorted, first,  alphabetically by namespace prefix, and second, within each namespace prefix group alphabetically by data name. 

Each data name is hyperlinked to its associated relationships and metadata.  For elements this includes its definition, keywords (synonyms, if any), usage information (if any), and usage examples (if any), and type.  For types this includes elements it contains, elements that are of this type, base types from which it is derived.  For convenience there are many features that help with identification of data components in the display.  Property names (XML element and attribute names) are displayed in blue, and XML type names are displayed in red.  XML element and attribute names are usually displayed with their associated XML type names.  Hovering over a data component name will reveal its definition.  A "details" link to the right of a property name and associated type name will reveal metadata about that property. 

NOTE:  The Microsoft Internet Explorer 11 browser must run in "compatibility mode" for SSGT to work correctly:
   (1)  Go to https://tools.niem.gov, and open Compatibility View (Tools / Compatibility View Settings).
   (2)  Add tools.niem.gov or niem.gov to Compatibility View, and SSGT Search will work normally.


#### Advanced Search

with the exact phrase
with at least one of the words
without the words

search context definitions

component attributes (metatdata associated with eacch data component

search within one or more domains


##### Multiple search criteria


##### Wildcard search


### NIEM Model Spreadsheet

use Excel search
spreadsheet is better for exploring the model if you are a beginner



### Other methods to search NIEM content

A way to search through multiple release simultaneously
text search on schemas (name and definition) (e.g., Unix/Linux grep)
Google site search in onlne NIEM documentation pages
tools that export XSD and search XSD (xmlSpy, oXygen, etc.)



----

## Return to:  [Table of Contents](./index)

