---
title:  Search for NIEM data components
---

## How to search for NIEM data components

Although this section does not address NIEM modeling specifically, given the volume of NIEM, most modeling efforts will require searching the NIEM model for duplication, examples of content models, points of extension, etc.  This section introduces ome basic methods of searching for NIEM content. 


### Schema Subset Generation Tool (SSGT)

The Schema Subset Generation Tool (SSGT) is one way to search for NIEM data components.  This tool was designed to build and generate NIEM schema subsets.  However, since the model is very large, SSGT contains a convenient search engine that can be used alone.    


#### Basic Search

The SSGT provides a full text search capability for a NIEM release.  You can enter a search string into the criteria box and view a list of all NIEM data components that contain a lexical match to that string.  The default is to search all data component text records in a single release, including names, definitions, and other metadata text fields.  Namespaces are not part of the standard search.  This is because namespace prefixes are extremely prevalent throughout the model and woutend to clutter most search results.

Search is case independent.  A search for <code>sonty</code> will return the data component <code>PersonType</cod>.

SSGT can only search a single release (Later, we discuss a technique for searching multiple releases).  The default is the most recent (current) operational release.  If you need to search a previous NIEM releasese you must select it from the "options" menu. 

SSGT always requires that you declare the class of the data component you are looking for, and only that class will be in the scope of the search.  This means you must declare one of the following in the dropdown box: 
- Property (the default class) - XSD data elements, attributes in a NIEM release.
- Type - XSD data types in a NIEM release; may be complex or simple.
- Namespace - namespaces used in a NIEM release
- Facet - code values in a  NIEM release.
- External - profiles of standards used in a NIEM release that are not NIEM conformant (e.g., GML). 
- Association - relationships among two or more objects.

Search results are displayed as a list of NIEM textual data components in XML qualified name format (i.e., QName; a namespace prefix, followed by a colon character, followed by the component name).  For example, <code>nc:PersonFullName</code>.

A search result will be a list of data component names sorted as follows:
1. All data names for which the search criteria matched a substring within the name (not including its namespace prefix),are sorted first, alphabetically by namespace prefix, and second, within each namespace prefix group alphabetically by data name.
2. All data names for which the search criteria matched a substring within the associated data definition, are sorted, first,  alphabetically by namespace prefix, and second, within each namespace prefix group alphabetically by data name. 

Each data name is hyperlinked to its associated metadata and relationships.  For an element this includes its definition, keywords (synonyms, if any), usage information (if any), usage examples (if any), its own type, and the types that use this element.  For a type this includes its definition, content style, elements it contains, elements that are of this type, and base types from which it is derived.  For convenience there are many features that help with identification of data components in the display.  Property names (XML element and attribute names) are displayed in blue, and XML type names are displayed in red.  XML element and attribute names are usually displayed with their associated XML type names.  Hovering over a data component name will reveal its definition.  A "details" link to the right of a property name and associated type name will reveal metadata about that property. 

NOTE:  The Microsoft Internet Explorer 11 browser must run in "compatibility mode" for SSGT to work correctly:
   (1)  Go to https://tools.niem.gov, and open Compatibility View (Tools / Compatibility View Settings).
   (2)  Add tools.niem.gov or niem.gov to Compatibility View, and SSGT Search will work normally.


#### Advanced Search

In general, the SSGT advanced search capability provides additional constraints that limit the scope of a search.  

Click on "Show Advanced" to open the SSGT advanced search capabilities.  Here you can constrain the search criteria:
1. with the exact phrase
2. with at least one of the words
3. without the words
or all of these constraints simultaneously. 

You can also constrain search to particular metadata fields that you select.  These are Names, Definitions, Keywords (synonyms), Usage (descriptions of how a data component is commonly used), and Example Content (samples of valid values for the element). 

You can limit a search to one or more domains by checking/unchecking the appropriate boxes.  If you want to search content outside of all domains (for example, NIEM Core and all code lists), then just check "other".  If you uncheck all boxes the tool will go back to searching the entire model (same as if all boxes are checked).

##### Multiple search criteria

You can enter multiple search terms separated by spaces in the search criteria box.  In this case, SSGT search will return data component records that contain ALL those terms in any order.  

##### Wildcard search

SSGT also has one simple wildcard character, an asterisk.  It can be used as many times as desired within the search criteria box.  For example, the following search criteria:
	<code>son\*nor\*sim\*yp</code>
will return:
	<code>aamva\_d20:PersonOrganDonorCodeSimpleType</code> 
because this criteria matches this element name.  A single asterisk in the search criteria box will return all data components in the release.  (NOTE:  After a wildcard search SSGT replaces each asterisk in the criteria with a percent character.)


### NIEM Model Spreadsheet

For anyone relatively new to NIEM, the Model Spreadsheet is an easier way to search, navigate, and explore the model.  It's a good tool to familiarize with NIEM content and structure relatively quickly.

Each NIEM release package contains a Model Spreadsheet that can be opened with Microsoft Excel.  If you download and unzip a NIEM release package at https://release.niem.gov/ the spreadsheet will be <code>niem-m.n.xlsx</code> where <code>m</code> is the major (series) version integer, and <code>n</code>" is the minor version integer.

The model spreadsheet is organized into tabs corresponding to 
	NIEM Core components, followed by ...
	Each domain component set (in alphabetical order), followed by ...
	Type Description (a list of all XML types and their definitions)
	Elts sorted by type (a list of all XML elements)
	Elts sorted by name (a list of all XML elements)
	Attributes (a list of all XML attributes)
	Namespaces (a list of all namespaces used in the release)
	Class Tree (a list of all XML types arranged in a derivation tree)

Each tab contains a list that also includes various metadata about the data components listed.  Each type is hyperlinked to the location of its definition and.  The model spreadsheet is designed to explore types and their associated properties (sub-elements). 

Excel menu find and search functions also take wildcards.  Asterisk and question mark characters are used for multi- and single-character wildcards respectively.  To find asterisks and question marks in the text, you can escape these characters with a tilde (<code>~</code>).  So, <code>~\*</code> and <code>~?</code> will find asterisks and question marks.  To excape the tilde character itself, enter <code>~~</code>.


### Other methods to search NIEM content

#### Offline

Because NIEM is XML-based, most methods of searching NIEM are text oriented. 
Almost any good XML tool can be useful.  
Common XML editors that can do this are [Altova XMLSpy](http://www.altova.com/xmlspy.html) and [oXygen](https://www.oxygenxml.com/). 

Other methods of searching NIEM use full text search capabilities that can quickly scan through large file sets.  NIEM schemas contain an entire textual data dictionary.  Multiple NIEM releases can be searched simultaneously using some version of grep (originally a Unix utility and available natively on an Apple MacIntosh; there are also version that run under Microsoft Windows).  Grep is simple, fast, and facilitates user customization.  By downloading all the NIEM release packages and placing their XML schemas into a single directory, grep can be customized to find and extract any text that can be described by a grep expression.

#### Online

Another method of searching NIEM schemas is through a Google site search.  
All NIEM component names and definitions are online in open text, both in their XSD form as well as XHTML. 
For example, (https://release.niem.gov/niem/3.2/) is a Web page that indexes all the NIEM 3.2 schema documents.
Furthermore, at (https://release.niem.gov/) are all the NIEM release products since 2006.
Each release is documented in HTML pages rooted at these links:
- [NIEM 3.2 Namespaces Documentation](https://release.niem/gov/niem/NIEM-3.2-namespaces)
- [NIEM 3.1 Namespaces Documentation](https://release.niem/gov/niem/NIEM-3.1-namespaces)
- [NIEM 3.0 Namespaces Documentation](https://release.niem/gov/niem/NIEM-3.0-namespaces)	
- [NIEM 2.1 Namespaces Documentation](https://release.niem/gov/niem/NIEM-2.1-namespaces)
- [NIEM 2.0 Namespaces Documentation](https://release.niem/gov/niem/NIEM-2.0-namespaces)
- [NIEM 1.0 Namespaces Documentation](https://release.niem/gov/niem/NIEM-1.0-namespaces)

In both the release schemas and HTML documentation pages, it is possible to run a Google site search on data component names and definitions in the release schemas (XSD) or the namespace documentation pages (XHTML). 

Google only indexes full words, not full text. 

----

## Return to:  [Table of Contents](./index)

