---
title:  How to map a database, model, dictionary, etc. to NIEM
---

## Purpose of mapping

NIEM adopters generally do not start without pre-existing data requirements.
They often begin with existing legacy metadata associated with a database or data model.
This metadata usually contains most or all of their data requirements. 
NIEM is designed for sharing information with organizations and communities outside their sphere of influence.
So, the primary targets for mapping to NIEM are those data requirements that will be shared externally.
That said, depending upon user intent and scope of NIEM adoption, the user may map all metadata to NIEM.

Mapping is an important step to NIEM adoption because it:

1. Provides familiarity with the contents of NIEM.
2. Establishes a detailed record of the semantic and structural associations between existing legacy metadata and NIEM representations. 
3. Helps a NIEM adopter to consider and evaluate the scope of effort.
For example, it may only be necessary to identify data requirements for sharing information with external entities (and map associated metadata to NIEM).
4. Provides guidance to programmers who will code or modify code for implementing information exchanges with NIEM. 


## How to map to NIEM

A spreadsheet is one of the simplest tool for documenting a mapping between a source (database, model, etc.) and NIEM.
The basic concept of mapping is to match (and align) appropriate metadata components from the source to semantically equivalent or nearly equivalent components in NIEM.

### Map construction

Given a spreadsheet paradigm, a row identifies a semantic association between a source metadata component and a NIEM metadata component, and describes the nature of that association.

There are generally three possible outcomes for an association: exact, partial, or none.
An exact match means that the components are semantically equivalent (or close enough).
At the other extreme, no match (none) means that there are no NIEM components that can match or even partially match the source component.
In this case, there will be no NIEM component in this record.
This identifies a gap in the mapping for which a new NIEM component is required.
This component will be designed and proposed later as part of the NIEM adoption and on-boarding process.
And of course, somewhere between an exact semantic match and none lies a partial match.

Thus, a mapping requires three basic parts:

**Source model component**&nbsp;&nbsp;&nbsp;&nbsp; | **NIEM component**&nbsp;&nbsp;&nbsp;&nbsp; | **Description of mapping**
Name                 | Name         |  Nature of semantic match:
Definition           | Definition   |  - exact match
Datatype             | Datatype     |  - partial match
etc.                 | etc.         |  - none (missing in NIEM)
----

For convenience and completeness mappings usually incorporate any additional metadata associated with each source and NIEM component (such as definition, datatype, cardinality, etc.).
Also, a column for general comments/notes (not shown above) is incorporated into most mapping documents to ensure clarity and to record rationales for difficult associations.


### Handling partial matches

Partial semantic matches tend to be the norm.
Sometimes they can be resolved by breaking down complex types into constituent components and subsequently mapping to them.
However, most schemes and models for data representation have many dimensions that can complicate what would otherwise appear to be an exact or near exact match, including names, semantics, stucture, constraints, datatype, usage, and others.
For this reason, sometimes treating a partial match as "no match" (and subsequently designing new NIEM components) may be more practical and productive.

For evaluating a match, various kinds of information may be exploited, including:

- model or schema metadata such as element names, data types, structures, and constraints
- instance data and usage information
- information from dictionaries, thesauri, ontologies, previous matching decisions, and feedback from others

**[ More to follow, including examples, Change Request, Component Mapping Template ]**

----

## Return to:  [Table of Contents](./index.html)

