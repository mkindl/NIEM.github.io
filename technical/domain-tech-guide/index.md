---
title: An Introduction to NIEM Domain Modeling
---

#### Feedback:
- x-reference some sections with [NIEM ConOps][1] to avoid duplication.
- move some sections to [NIEM ConOps][1] as a revision to that document. 
- Main thrust should be based on the implementation of the NIEM IEPD Life Cycle (LC) and conformance to the NDR and MPD specifications.

[1]: https://reference.niem.gov/niem/guidance/concept-of-operations/ 

#### Response:
- ConOps never made it past version 0.5, and now contains outdated material. 
- PMO proposed the ConOps be Web pages on niem.gov, instead of a document.
  - ConOps has changed many times.
  - Easier to maintain pages than document.
- If ConOps is resurrected, then agree, must balance content between DTG and ConOps. 
- Not sure why DTG should be based on implementation of the NIEM IEPD LC.
- However, domain modeling should be informed by IEPD LC; IEPD extensions should feed updates to core and domain models. 
- See the [Intro page](./intro.html) 
----

## 1. Introduction

### 1.1 Background

- Purpose of NIEM.  Why and why not use NIEM?  Common myths.
  - NIEM is too big for us to use. (you can use only what you need in NIEM, i.e., subset your requirements)
  - NIEM is too complex to use. 
  - NIEM does not contain the data we need. (establish and manage your own domain; or extend NIEM)
  - NIEM cannot use other XML standards. (false)
  - NIEM cannot be used by other XML standards. (false)

- What is a NIEM *Domain*?
  - Community of Interest (CoI), organization, or Line of Business (LoB)?

- Why domains are important in NIEM.
  - Almost every NIEM participant is a member of at least one domain. 
  - NIEM was designed with a core and domains that correspond to central (NBAC) and distributed (domain) governance to facilitate scaling. 
  - A domain at-large does not have to join NIEM or participate in its governance to use NIEM and share information with member domains.

- Purpose of this domain modeling guide
  - Primarily for the benefit of new or emerging domains.
  - Also a baseline reference for all domains and governance. 

- What topics or documents to be familiar with
  - XML and W3C XML Schema
  - NIEM High Level Version Architecture
  - NIEM Conformance
  - NIEM NDR

### 1.2 Scope

- Focus on technical aspects of domain model management.
- Where do you begin?  How to start a domain model
- Naming and definitions
- NIEM code lists
- Technical responsibilities of a domain.
  - Build your domain content for other domains to reuse.
  - Make your data component names and definitions as clear as possible to other domains. 
  - Participate in harmonization and issue resolution when your domain is involved.
  - Consider the impacts changes to your domain will have on other domains (or Core).  Notify them! 
- Maintaining a domain model (what to model, when to change it, etc.)
- What impacts my domain model?  What does my domain model impact?
- Participating in a release cycle, domain update, and other NIEM technical processes.
- Technical assistance, tools, templates, best practices, references, etc.

### 1.3 Audience

- Technical personnel who support NIEM domains, and particularly new domains. 
- NIEM working level governance; includes NBAC, NTAC, domain technical POCs, PMO staff, and lead developer. 


## 2. Terminology

### 2.1 Common NIEM terms
This section defines most basic, common NIEM terms that are easy to understand.
Examples include:

- data component
- W3C XML Schema
- XML schema document
- instance XML document
- ...

### 2.2 More specific terms

More specific definitions will be defined at first use in appropriate section.
Examples include:

- coherence
- funneling
- micro release
- domain reconciliation
- coordinated domain update
- core synchronization
- ...


## 3. NIEM technical basics

###   3.1 NIEM High-Level Version Architecture (HLVA)

A "Reader's Digest" (abridged) version of 
[NIEM HLVA 3.0](https://reference.niem.gov/niem/specification/high-level-version-architecture/3.0/)

- Domain independence
- Release optimization
- Types of reference content (major, minor, micro, domain update, core supplement)
- Repositories (release, publication)
- Collaboration
- Concepts

### 3.2 Schema document namespacing and versioning

- Important to domains who submit content in XSD.
- Describe the correlation of target namespaces and XML schema documents.
- Each schema document is assigned a unique target namespace.
- Namespace Syntax.
- URIs (Uniform Resource Identifiers), syntax, purpose, etc.

### 3.3 NIEM release cycle

- Release types:  major, minor, micro, core supplement
- Scheduling:  standard timeframes, milestones, reviews, stages 
(pre-alpha, alpha, beta, release candidate)
- Harmonization (who, what, how, the process, concepts, etc.)
- Issue resolution (who, what, how, the process, voting, tracking, etc.)
- Input formats
  - XSD (NIEM conformant XML Schema documents)
  - XLS (Microsoft Excel spreadsheet) 
[Change Request](https://reference.niem.gov/niem/resource/change-request/) 
(Christina's latest modifications)
  - Simple text explanations in email for very minor changes.
- Technical assistance (who, what, how)

### 3.4 Domain update

- Domain independence and self-serviced
- Types of domain updates: incremental vs. replacement
- Multi-domain coordinated domain update
- Change content preparation and model management
- Metadata, lineage, change log

### 3.5 Conformance and quality assurance

- General and specific confomance
- Verification (who, what, how, when, etc.)


## 4. Roles and responsibilities

- Domain Steward
- Domain Technical POC (or representative)
- Program Management Office (PMO) staff
- Lead developer (GTRI)
- NIEM Technical Architecture Committee (NTAC)
- NIEM Business Architecture Committee (NBAC)


## 5. Communications and workflow

This section is NOT a restatement of NIEM policies and procedures. 
It is a condensed list of key resources for communications, processes, committees, and collaboration. 

- Email lists for governance committees (who, what, purpose, how to enroll)
  - [NIEM Techncial Architecture Committee](mailto:ntac@lists.gatech.edu (NTAC); [request to be added](mailto:ntac-request@lists.gatech.edu) (requires PMO approval).
  - [NIEM Business Architecture Committee](mailto:nbac@lists.gatech.edu) (NBAC); [request to be added](mailto:nbac-request@lists.gatech.edu) (requires PMO approval).
- Tool accounts (who, what, purpose, how to obtain account) 
  - [NIEM Configuration Control Tool (NCCT)](https://niem.gtri.gatech.edu/ncct/); for PMO, governance, and domain staffs; [request account](mailto:pgmw-system@gtri.gatech.edu)
  - [Collaboration zones](https://www.niem.gov/myniem/Pages/myNIEM-features.aspx); for PMO, governance, and domain staffs; [register for account](https://www.niem.gov/Pages/Register.aspx)
  - [Conformance Testing Assistant](https://tools.niem.gov/contesa/) (ConTesA); public; [request account](https://tools.niem.gov/contesa/registration)
  - [NIEM GitHub](https://niem.github.io/); public; [sign-up for GitHub account](https://github.com/)
- Regular meetings (who, what, when, where, how, purpose)
  - NBAC meetings
  - NTAC meetings
  - PMO meetings
  - Joint NTAC/NBAC meetings
  - Reviews (of all kinds)
- Public questions, comments, recommendations on NIEM (purpose, process)
  - General technical comments and feedback:  <niem-comments@lists.gatech.edu>
  - NIEM SalesForce:  <information@niem.gov>
  - NIEM SalesForce:  <https://niem.gov/Pages/contact.aspx>
  - National Information Sharing Standards (NISS) Helpdesk:  <nisshelp@ijis.com>
  - National Information Sharing Standards (NISS) Helpdesk:  <https://niss.custhelp.com/>

----

## Appendix A - How to design and build domain model content

#### FEEDBACK: 
- This section should be at the beginning.  
- Suggestions here are the most critical factors that determine the value and benefits of a domain, and how to identify the shareable data. 

#### RESPONSE:
- Agree, this is an important section, and it is also generalized guidance.  There is other NIEM-specific technical material (above) that is equally important for a domain steward or technical representative to understand to be a good domain.

----

1. Identify data requirements.
- NIEM was primarily designed to share information across domains; however, consider both internal and external information sharing requirements.
- Identify information you must share outside your domain or other communities of interest.
- Who do you share your information with outside your domain? 
- Who from outside your domain shares their information with you (that you need)?
- Identify information you share within your domain.
- Identify or develop simple scenarios, and within those scenarios identify common use cases for sharing information.
- Examine existing database schemes, data dictionaries, XML schemas, flat files, paper/electronic forms, workflows, etc. for data requirements.  How the data could be or is currently being shared using other formats can provide insights as to what data is shared.
- Data dictionaries, glossaries, and authoritative sources should be captured.  There are many variances in data definitions already existent in databases and data transmissions. Harmonization of this data BEFORE creating a domain is a critical step.  Otherwise the domain will be “yet another set of definitions”.  Mapping current data definitions to the domain is also important so developers can trace back to existing data sources.  Semantic harmonization should be used.  The meaning of the data and its variance interpretations is important to understand.

2. Do not _boil the ocean_:
- Do not create NIEM data components for every possible contingency or likelihood.
- Only model known information requirements that exist now or that you already know are necessary.
- Do not build nice-to-have or likely future data components.
- Consider real scenarios for information sharing and exchanging that will identify both the existing and new requirements.  If possible, envision what the domain will look like in the (not too distant) future.  
- Scale back rather than create data components that may have to be deleted or changed in later release cycles.  This will confuse your domain community.
- Try to ensure the key domain classes are present.  It is easy add properties to a type in a domain update or release later.  Furthermore, NIEM types are easily extended with new elements in IEPDs using augmentation points.  IEPD extensions feed new requirements back to the reference model for future addition to NIEM. 

3. Start small scale; grow the domain model through experience with domain updates and release inputs. 
- Build a domain model that represents the future (to-be), not the past.  For example, include classes for privacy, data quality, traceability, and data tracking. 
- Do not overbuild data components.  Keep them simple:  A type represents a real world object or concept. Element describe the characteristics or parts of that object or concept. 

4. Map data requirements to NIEM.
- Reuse existing data components where possible. 
- Identify missing requirements (gap analysis). 

5. Use gap analysis and create new NIEM data components:
- ONLY when needed. 
- Consistent with the NIEM NDR and releases (reference schemas). 
- Use elements for object properties; elements are far more flexible. 
- Use attributes only if absolutely necessary; e.g., very tightly coupled metadata on an element, as attribute `xml:lang` is to an element of type `TextType`.

6. Clearly identify data components that will require future harmonization 
with the Core (or with other domains if inputting a domain update).

7. Use reference materials to model various NIEM techniques (i.e., augmentation, association, role, 
references, metadata, abstract elements and substitution groups, type extension, type adapter, etc.):
- Existing [release reference schemas](https://release.niem.gov/)
- [Change request](https://reference.niem.gov/niem/resource/change-request/) examples
- [Developer Network patterns](https://niem.github.io/developer-network/patterns/)
- [Refernce tools](https://tools.niem.gov), e.g.,Schema Subset Generator, ConTesA, Code List Schema Generator, Migration Assistant, etc. 

8. During release cycle, provide initial input in NIEM-conformant 
[XML Schema document](https://reference.niem.gov/niem/specification/nameing-and-design-rules/3.0/) (XSD) 
or [Change Request](https://reference.niem.gov/niem/resource/change-request/) (XLS) format. 

9. IEPDs vs. Domains
- Domains contain the reusable building blocks for creating IEPDs; IEPDs are definitions for information exchanges.
- An IEP (Information Exchange Package) is an instance XML document that conforms to an IEPD. 
- Differences in purpose, scope, reusability, NDR rules.
- IEPD extensions are candidates for domain content, but each should be evaluated and potentially remodeled.
- Use IEPD repositories to share IEPDs.
- Example IEPD:  Cursor-on-Target MilOps Future Namespace.
- [IEPD versioning](https://niem.github.io/technical/iepd-versions/)

10. GTRI:
- Assists with conformance, quality, and modeling.
- Integrates inputs into the release or DU for your review.
- Can save you extra work and time if you make systemic errors. 
- Get preliminary inputs in early for review, feedback, and assistance.


## Appendix B - Data modeling questions, considerations, and decisions

Questions to ask or consider about metadata, semantics, and structure while modeling NIEM content.  
These can help you decide what to model, how, and what NIEM structures to employ or consider. 

For each potential NIEM Core data component (type/property):

1. Is it a NIEM property or type? 
- Is it common enough to be part of NIEM Core?  (depth of NIEM Core)
- Or is it better used as a Domain extension to NIEM Core?
- Is it required in NIEM information exchanges (IEPD) or messages?  (scope)
- What kinds of data exchanges use it or would use it?
- Is it reusable in other messages?  
- Can it be used in composing IEPDs? 
- Does it overlap multiple requirement sources (models)? 
- What data models contain this component or one similar to it? (source/requirement)

2. Is it a characteristic property or subpart of the appropriate NIEM object (type)? 

3. Is it too specific (not reusable)?
- Should it be generalized to include in NIEM Core?
- Better used as a Domain extension to NIEM Core?

4. Does this property or type overlap with another?  Not distinct? 
- Should it be joined with another component?
- Should it be split into multiple components?  (too broad)
- Select one; remove the other(s)?

5. Is its name meaningful to NIEM?
- Is it properly named?
- Are the terms of its name meaningful?
- Are there meaningful definitions for each term?  Is the proper word sense identified?

6. Is its definition meaningful in NIEM?
- Is it defined distinctly from other NIEM Core data components?
- Is it distinct from other Domain components?

7. Is it modeled correctly (structurally correct; correspond to real-world)?  
- Does it have the right base-types and properties?  
- Is it missing common characteristic or subpart properties (simple/complex)?  
- Does it contain properties that should be deleted, replaced, or changed? 

8. How is it related to other objects (types)?
- Use NIEM associations?
- Use NIEM roles? 

9. How is it used?  (Primary context?  Multiple contexts?)


## Appendix C - Guide to NIEM technical resources:  references, releases, tools, templates, and other aids

**References** | **URL** | **Notes** 
-------------- | ------- | --------- 
NIEM technical references           | <https://reference.niem.gov/>                 | latest versions 
All NIEM technical references &nbsp;| <https://reference.niem.gov/niem/>            | includes older versions 
NDR Schematron rules | <https://reference.niem.gov/niem/specification/naming-and-design-rules/3.0/niem-ndr-3.0.zip> | use with Oxygen or XMLSpy |
NIEM 2.1 UML profile                | <http://www.omg.org/spec/NIEM-UML/1.0/>       | for NIEM 2.1 only 
NIEM 3.0 UML profile                | <http://www.omg.org/spec/NIEM-UML/3.0/Beta1/> | NIEM 3.0, 3.1 
**Releases** | **URL** | **Notes** 
------------ | ------- | --------- 
All NIEM release packages                   | <https://release.niem.gov/>                | 
All NIEM release raw files                  | <https://release.niem.gov/niem/>           | 
NIEM domain updates, core supplements &nbsp;| <https://publication.niem.gov/niem/>       | 
NIEM 3.1 release                            | <https://release.niem.gov/niem/3.1/> &nbsp;| replace 3.1 for other versions
**Tools** | **URL/Email** | **Notes**
--------- | ------------- | ---------
NIEM online reference tools                | <https://tools.niem.gov/>                              |
Schema Subset Generation Tool (SSGT) &nbsp;| <https://tools.niem.gov/niemtools/ssgt/index.iepd>     |
Conformance Testing Assistant (ConTesA)    | <https://tools.niem.gov/contesa/>                      |
Code List Schema Generator                 | <https://tools.niem.gov/niemtools/codelist/index.iepd> |
NIEM tool staging server                   | <https://niemstaging.ittl.gtri.org/niemtools> | available in beta stage of release cycles
NIEM GitHub                                | <https://niem.github.io/>                              | 
NIEM Config Control Tool (NCCT)            | <https://niem.gtri.gatech.edu/ncct/>                   |
Request access to online tool services     | <mailto:pgmw-system@gtri.gatech.edu> | SSGT search and subset, Code List Schema Generator
Report tool issues                         | <mailto:pgmw-system@gtri.gatech.edu>                   |
**Other Resources** | **URL** | **Notes**
------------------- | ------- | ---------
NIEM home                              | <https://niem.gov/>                                             |
Change request                         | <https://reference.niem.gov/niem/resource/change-request/>      |
NCCT User Guide                        | <https://reference.niem.gov/niem/guidance/ncct-user-guide/1.0/> |
Schemas that define a _Wantlist_ &nbsp;| <https://reference.niem.gov/niem/resource/wantlist/>            |
Code list metadata master              | <https://release.niem.gov/>                          | now in each release package 3.0+


## References

- High Level Version Architecture v3.0:  <https://reference.niem.gov/niem/specification/high-level-version-architecture/3.0/>
- NIEM 3.0 package with core supplements and domain updates:  <https://release.niem.gov/niem/3.0/du-cs-3.0.html>
- Conformance Specification v3.0:   <https://reference.niem.gov/niem/specification/conformance/3.0/>
- Naming and Design Rules (NDR) v3.0:  <https://reference.niem.gov/niem/specification/naming-and-design-rules/3.0/>
- Conformance Targets Attribute Specification v3.0:  <https://reference.niem.gov/niem/specification/conformance-targets-attribute/3.0/>
- Code Lists Specification v1.0beta1:  <https://reference.niem.gov/niem/specification/code-lists/>
- Model Package Description (MPD) Specification v3.0.1:  <https://reference.niem.gov/niem/specification/model-package-description/3.0.1/>
- UML profile for NIEM v3.0:  <http://www.omg.org/spec/NIEM-UML/3.0/Beta1/>
- Change request v1.0:  <https://reference.niem.gov/niem/resource/change-request/>
- Wantlist schemas (all versions):  <https://reference.niem.gov/niem/resource/wantlist/>
- Model schemas v1.1:  <https://reference.niem.gov/niem/resource/model/1.1/>
- NIEM Configuration Control Tool (NCCT) User Guide v1.0:  <https://reference.niem.gov/niem/guidance/ncct-user-guide/1.0/>

