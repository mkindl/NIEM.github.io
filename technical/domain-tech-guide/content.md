---
title:  Design and build initial NIEM domain content
---

## How to name, define, and structure data components
 
### 3.1 Identify data requirements

- NIEM was primarily designed to share information across domains; however, consider both internal and external information sharing requirements.
- Identify information you must share outside your domain or other communities of interest.
- Who do you share your information with outside your domain? 
- Who from outside your domain shares their information with you (that you need)?
- Identify information you share within your domain.
- Identify or develop simple scenarios, and within those scenarios identify common use cases for sharing information.
- Examine existing database schemes, data dictionaries, XML schemas, flat files, paper/electronic forms, workflows, etc. for data requirements.  How the data could be or is currently being shared using other formats can provide insights as to what data is shared.
- Data dictionaries, glossaries, and authoritative sources should be captured.  There are many variances in data definitions already existent in databases and data transmissions. Harmonization of this data BEFORE creating a domain is a critical step.  Otherwise the domain will be “yet another set of definitions”.  Mapping current data definitions to the domain is also important so developers can trace back to existing data sources.  Semantic harmonization should be used.  The meaning of the data and its variance interpretations is important to understand.

### 3.2 Do not _boil the ocean_

- Do not create NIEM data components for every possible contingency or likelihood.
- Only model known information requirements that exist now or that you already know are necessary.
- Do not build nice-to-have or likely future data components.
- Consider real scenarios for information sharing and exchanging that will identify both the existing and new requirements.  If possible, envision what the domain will look like in the (not too distant) future.  
- Scale back rather than create data components that may have to be deleted or changed in later release cycles.  This will confuse your domain community.
- Try to ensure the key domain classes are present.  It is easy add properties to a type in a domain update or release later.  Furthermore, NIEM types are easily extended with new elements in IEPDs using augmentation points.  IEPD extensions feed new requirements back to the reference model for future addition to NIEM. 

### 3.3 Start small scale

- Grow the domain model over time through experience with domain updates and release inputs. 
- Build a domain model that represents the future (to-be), not the past.  For example, include classes for privacy, data quality, traceability, and data tracking. 
- Do not overbuild data components.  Keep them simple:  A type represents a real world object or concept. Element describe the characteristics or parts of that object or concept. 

### 3.4 Map data requirements to NIEM

- Reuse existing data components where possible. 
- Identify missing requirements (gap analysis). 

### 3.5 Use gap analysis and create new NIEM data components:
- ONLY when needed. 
- Consistent with the NIEM NDR and releases (reference schemas). 
- Use elements for object properties; elements are far more flexible. 
- Use attributes only if absolutely necessary; e.g., very tightly coupled metadata on an element, as attribute `xml:lang` is to an element of type `TextType`.

### 3.6 Clearly identify data components that will require future harmonization 

with the Core (or with other domains if inputting a domain update).

### 3.7 Use reference materials to model various NIEM techniques 

- Simple examples exist as [Developer Network patterns](https://niem.github.io/developer-network/patterns/)
that illustrate NIEM techniques such as:  augmentation, association, role, references, metadata, abstract elements and substitution groups, type extension, type adapter, etc.
- Review existing [release reference schemas](https://release.niem.gov/).
- The [change request](https://reference.niem.gov/niem/resource/change-request/) contains examples.
- Use the [reference tools](https://tools.niem.gov), e.g.,Schema Subset Generator, ConTesA, Code List Schema Generator, Migration Assistant, etc. 

### 3.8 During release cycle, provide initial input in NIEM-conformant 
[XML Schema document](https://reference.niem.gov/niem/specification/nameing-and-design-rules/3.0/) (XSD) 
or [Change Request](https://reference.niem.gov/niem/resource/change-request/) (XLS) format. 

### 3.9 IEPDs vs. Domains
- Domains contain the reusable building blocks for creating IEPDs; IEPDs are definitions for information exchanges.
- An IEP (Information Exchange Package) is an instance XML document that conforms to an IEPD. 
- Differences in purpose, scope, reusability, NDR rules.
- IEPD extensions are candidates for domain content, but each should be evaluated and potentially remodeled.
- Use IEPD repositories to share IEPDs.
- Example IEPD:  Cursor-on-Target MilOps Future Namespace.
- [IEPD versioning](https://niem.github.io/technical/iepd-versions/)

### 3.10 The Lead NIEM Developer (GTRI) can and will help you
- Assists with conformance, quality, and modeling.
- Integrates inputs into the release or DU for your review.
- Can save you extra work and time if you make systemic errors. 
- Get preliminary inputs in early for review, feedback, and assistance.

----

## Return to:  [Table of Contents](./index)

