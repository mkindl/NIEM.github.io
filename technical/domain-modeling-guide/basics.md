---
title:  Technical basics
---

## Technical fundamentals of NIEM

### NIEM High-Level Version Architecture (HLVA)

The [NIEM HLVA 3.0](https://reference.niem.gov/niem/specification/high-level-version-architecture/3.0/) identifies processes, artifacts, governance responsibilities and how they interact to produce new releases of and updates to the NIEM model. The HLVA discusses issues with inherently conflicting tradeoffs including (but not limited to):

- Timeliness vs. stability
- Domain autonomy vs. interoperability
- Ease for information exchange developers vs. ease for domain developers

Under PMO direction and with technical assistance from the lead developer, the NBAC, NTAC, and domains execute NIEM governance at the operational level through the HLVA. By practicing the HLVA:

- Reliable and consistent schedules for activities that produce a NIEM major or minor release ensure that activity participants know work timelines and when inputs are due, and NIEM users can plan for release dates.
- Between regular major and minor release cycles, any domain may independently publish an update on its own timeline and make it available for immediate use (with the knowledge that its changes may impact other domains that extend or reuse their data components). 
- Domain updates are incorporated into the next NIEM release. So, periodic releases remove negative impacts, inconsistencies, or incoherence resulting from independent domain updates. 
- Information exchange developers are provided with a NIEM release, which is an updated schema document set that is coherent (See [coherence]), for increased usability.
- A specific, concrete path exists for domains to feed input into NBAC's update, core synchronization, and harmonization processes, for inclusion in a future NIEM release. Domain, NBAC, and NTAC work on new content and changes is more evenly spread over time periods between release cycles instead of intensifying them. 
- All changes are visible. Each namespace URI is used for exactly one version of a schema document, and any changes to a schema result in a new namespace URI.
- Change logs identify and describe changes made to each namespace.


### Types of reference schema documents

NIEM reference schema documents define normative NIEM representations of information in the W3C XML Schema Definition (XSD) language.
Reference schema documents are used to build information exchanges in the form of Information Exchange Package Documentation (IEPD).

NIEM maintains two repositories with several types of reference schema documents:

- The [release area] at <https://release.niem.gov> contains:
  - [major release]s
  - [minor release]s
  - [Releases][NIEM release] coupled with [domain update]s and [core supplement]s (i.e., those updates and supplements published with or immediately after a given release)
- The [publication area] at <https://publication.niem.gov/niem> contains:
  - [domain update]s
  - [core supplement]s


### Domain Independence

The NIEM HLVA establishes controlled domain independence between major and minor release cycles. 
Any domain is allowed to publish changes in the form of a [domain update]
to its domain model for immediate use by information exchange developers.
Such changes must be NIEM conformant, and are published under a new [namespace][xml namespace].
Packaging under a new namespace ensures the changes are transparent and cannot impact another domain that references and reuses the older version (namespace) of the changed content.

That said, there is a downside to this versioning approach.
Other domain models (namespaces) are still referencing the old existing namespace in the release before the changes were published as a domain update.
Information exchange developers can use the new namespace, but this does not address the fact that existing domain namespaces do not yet reference or use the new namespace just published.
To use the new namespace (and its new content) with older domain schema documents requires that either:
- other domains publish domain updates that reference the new namespace (instead of the old); OR
- an IEPD import the new namespace, and under the NIEM NDR, extend existing or create new data components to use the new content.

The latter approach is generally easier than the former.
Furthermore, the former approach (publishing more domain updates) tends to multiply the number of dependencies that exist among schema documents associated with a given release.
This potentially increases the difficulty of using a given release with a set of one or more associated domain updates.

To help mitigate the impacts across domains due to independent updates, the HLVA allows multiple domains to intentionally collaborate on a [coordinated domain update] to ensure their collective changes are mutually coherent (See [coherence]).
Of course, the extreme case of a coordinated domain update in which all domains participate is called a minor release.
At this point, you should now understand the rationale for periodic releases (both major and minor) &mdash; to reestablish [coherence] among domain schema documents that have accumulated independent updates and associated dependencies and duplications.

In practice the expectation is that a small number of independent domain updates will not have significant impact on IEPDs because the majority of changes contained in them will not be on data components reused across the domain reference models.
Furthermore, even when changes introduce multiple versions of data components in domain models, subsetting can minimize semantic overlap and complexity if such components are not used in an IEPD.

### 5.2 XML schema document namespacing and versioning

XML schema [targetNamespaces][targetNamespace] are very important to NIEM's multi-domain organization and versioning.
Each domain schema document published with a [NIEM release] or [domain update] is assigned a unique [targetNamespace].
This ensures that even if two or more domains design components with the same name (even if the meaning is different), they will not conflict.
Later, a [harmonization] process will resolve any semantic overlap that exists in the model.

In fact, all [XML schema documents][xml schema document] within all NIEM releases, domain updates, and core supplements (i.e., [reference schema documents][reference schema document]) must have an assigned [targetNamespace] and that namespace must be unique.
The only exception to this rule is that a [subset schema document] MUST have the same [targetNamespace] as the [reference schema document] from which it was derived.
This is because a [subset schema document] is not considered a [reference schema document].

Since all schema document target namespaces are unique, they distinguish domains, versions within domains, and versions among the NIEM cores.


### targetNamespace syntax

To maintain order NIEM imposes a syntax on its target namespaces.

- Namespace Syntax
- URIs (Uniform Resource Identifiers), syntax, purpose, etc.


### 5.4 Domain updates

#### Types of domain updates
- Types of domain updates: 
  - incremental vs. replacement
  - Multi-domain coordinated domain update

#### Preparing a domain update

A domain prepares a domain update by adding, deleting, and/or modifying data components in a given release of its domain schema document (or documents). 
At anytime in the process the domain may request assistance from or review by the lead developer.
It is better to do this sooner than later. 
Often times the lead developer can identify and help fix issues with a content model that may save the domain significant wasted time and rework.   
Ultimately, the domain must submit the domain update draft to the lead developer for conformance validation and quality checks.
This is essential to ensure that the new update will work correctly with tools and other resources.

A domain may submit a domain update for review in one of the following formats: 

- [W3C XML Schema Definition (XSD) Language](https://www.w3.org/XML/Schema) &mdash; This format is preferred because it is the normative representation for NIEM. 
- [Change Request spreadsheet](https://reference.niem.gov/niem/resource/change-request/1.0/) (XLS) &mdash; This spreadsheet format is used by domains that have minimal experience with XSD.
- Plain text (in email) &mdash; This method can be used when a very minor and low volume update is needed that can be clearly described in a brief set of bullets or a short paragraph. This format should not exceed a half-page of text.   

Domains are free to maintain their own NIEM models in Universal Modeling Language (UML) or any other modeling language.
UML is a graph of relationships with text that can be serialized into XMI.
However, UML and other graph-oriented models are not processed by NIEM resources.
Domains that use UML are responsible to transform UML into NIEM conformant XSD before submitting a domain update or input for a new NIEM release.
[UML tools](https://en.wikipedia.org/wiki/List_of_Unified_Modeling_Language_tools) and [UML profiles](https://reference.niem.gov/niem/specification/uml-profile/omg/) for NIEM exist for doing so.
When using such UML resources, ensure they are consistent with the latest NIEM NDR.

#### Reuse of data components among domains

Domains cannot alter schema documents in namespaces that are not allocated to it by the NIEM PMO.
However, it is common for a [domain update] to import and reference data components in a schema document under the control of another domain to extend or augment it, as permitted by the NIEM NDR.
This is exactly like domains reuse NIEM Core.

For example, let's assume that within a given NIEM release domain A and domain B do not share any data components, and so their domain models are independent.
Domain B decides to publish a [domain update] to its current model. 
Domain B imports and references the Domain A schema document in order to reuse as-is, extend, or augment data components currently defined in domain A.
At this point in time, the domain A content referenced by domain B will remain independent of Domain B.
However, the domain B data components in its new update are now based on and depend on domain A content.

The [base release] for a NIEM [domain update] is the NIEM [major][major release] or [minor release] to which the [domain update] applies.
A [domain update] MUST be applicable to at least one [base release]. 
In general, each [domain update] applies to a single release. 
Exceptions are possible but rare.

On the other hand, multiple [domain update]s may apply to a given [NIEM release]. 
Multiple [domain update]s to a [base release] apply in date sequence (earliest to latest).
For a given domain, [incremental domain update]s accumulate until a [replacement domain update] is published.
For a given [NIEM release] all applicable [domain updates] are harmonized, synchronized, and integrated into the next major or minor release.


### 5.3 NIEM release cycle

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
- Release optimization


### 5.5 Conformance and quality assurance

- General and specific conformance
- Verification (who, what, how, when, etc.)

----

### <&mdash;&mdash; Return to:  [Table of Contents](./index.html)

----

[base release]: ./glossary.html#base_release
[targetNamespace]: ./glossary.html#targetNamespace
[XML namespace]: ./glossary.html#xml_namespace
[coordinated domain update]: ./glossary.html#coordinated_domain_update
[data component]: ./glossary.html#data_component
[funneling]: ./glossary.html#funneling
[incremental domain update]: ./glossary.html#incremental_domain_update
[intermediate release]: ./glossary.html#intermediate_release
[replacement domain update]: ./glossary.html#replacement_domain_update

[NIEM release]: https://reference.niem.gov/niem/specification/high-level-version-architecture/3.0/high-level-version-architecture-3.0.html#definition_NIEM_release
[major release]: https://reference.niem.gov/niem/specification/high-level-version-architecture/3.0/high-level-version-architecture-3.0.html#definition_major_release
[minor release]: https://reference.niem.gov/niem/specification/high-level-version-architecture/3.0/high-level-version-architecture-3.0.html#definition_minor_release
[micro release]: https://reference.niem.gov/niem/specification/high-level-version-architecture/3.0/high-level-version-architecture-3.0.html#definition_micro_release
[published update]: https://reference.niem.gov/niem/specification/high-level-version-architecture/3.0/high-level-version-architecture-3.0.html#definition_published_update
[domain update]: https://reference.niem.gov/niem/specification/high-level-version-architecture/3.0/high-level-version-architecture-3.0.html#definition_domain_update
[core supplement]: https://reference.niem.gov/niem/specification/high-level-version-architecture/3.0/high-level-version-architecture-3.0.html#definition_core_supplement
[release area]: https://reference.niem.gov/niem/specification/high-level-version-architecture/3.0/high-level-version-architecture-3.0.html#definition_release_area
[publication area]: https://reference.niem.gov/niem/specification/high-level-version-architecture/3.0/high-level-version-architecture-3.0.html#definition_publication_area
[issue tracking area]: https://reference.niem.gov/niem/specification/high-level-version-architecture/3.0/high-level-version-architecture-3.0.html#definition_issue_tracking_area
[coherence]: https://reference.niem.gov/niem/specification/high-level-version-architecture/3.0/high-level-version-architecture-3.0.html#definition_coherence
[XML schema document]: https://reference.niem.gov/niem/specification/model-package-description/3.0.1/model-package-description-3.0.1.html#definition_XML_schema_document
[reference schema document]: https://reference.niem.gov/niem/specification/model-package-description/3.0.1/model-package-description-3.0.1.html#definition_reference_schema_document
[subset schema document]: https://reference.niem.gov/niem/specification/model-package-description/3.0.1/model-package-description-3.0.1.html#definition_subset_schema_document
[harmonization]: https://reference.niem.gov/niem/specification/high-level-version-architecture/3.0/high-level-version-architecture-3.0.html#definition_harmonization

