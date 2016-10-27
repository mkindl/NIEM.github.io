---
title:  Technical basics
---

## Technical fundamentals of NIEM

### 5.1 NIEM High-Level Version Architecture (HLVA)

The [NIEM HLVA 3.0](https://reference.niem.gov/niem/specification/high-level-version-architecture/3.0/) identifies processes, artifacts, governance responsibilities and how they interact to produce new releases of and updates to the NIEM model. The HLVA discusses issues with inherently conflicting tradeoffs including (but not limited to):

- Timeliness vs. stability
- Domain autonomy vs. interoperability
- Ease for information exchange developers vs. ease for domain developers

Under PMO direction and with technical assistance from the lead developer, the NBAC, NTAC, and domains execute NIEM governance at the operational level through the HLVA. By practicing the HLVA:

- Reliable and consistent schedules for activities that produce a NIEM major or minor release ensure that activity participants know work timelines and when inputs are due, and NIEM users can plan for release dates.
- Between regular major and minor release cycles, any domain may independently publish an update on its own timeline and make it available for immediate use (with the knowledge that its changes may impact other domains that extend or reuse their data components). 
- Domain updates are incorporated into the next NIEM release. So, periodic releases remove negative impacts, inconsistencies, or incoherence resulting from independent domain updates. 
- Information exchange developers are provided with a NIEM release, which is an updated schema document set that is coherent, for increased usability.
- A specific, concrete path exists for domains to feed input into NBAC's update, core synchronization, and harmonization processes, for inclusion in a future NIEM release. Domain, NBAC, and NTAC work on new content and changes is more evenly spread over time periods between release cycles instead of intensifying them. 
- All changes are visible. Each namespace URI is used for exactly one version of a schema document, and any changes to a schema result in a new namespace URI.
- Change logs identify and describe changes made to each namespace.


#### Types of reference content (major, minor, micro, domain update, core supplement)



#### Domain Independence

The NIEM HLVA establishes controlled domain independence between major and minor release cycles. 
Any domain is allowed to publish changes in the form of a <i>domain update</i>
to its domain model for immediate use by information exchange developers.
Such changes must be NIEM conformant, and are published under a new namespace.
Packaging under a new namespace ensures the changes are transparent and cannot impact another domain that references and reuses the older namespace (i.e., version) for the changed content.

That said, there are downsides to this versioning approach.
First, other domain models (namespaces) are still referencing the old existing namespace in the release before the changes were publish as a domain update.
Information exchange developers can use the new namespace, but this does not automatically change the old domain namespaces to use the new namespace just published.
To use the new namespace (and its new content) with older domain schema documents that refer to the older unchanged data components requires that either:
- other domains publish domain updates that reference the new namespace (instead of the old); OR
- an IEPD must import the new namespace and extend existing or create new (under the NIEM NDR) data components to use the new content.

The latter approach is generally easier than the former.
Furthermore, the former approach (publishing more domain updates) can potentially increase the difficulty of using a given release with a set of one or more associated domain updates whose changes may have created an increased number of dependencies.

To help mitigate the potential impacts among domains due to independent updates, the HLVA also allows coordinated domain updates among two or more domains who wish to ensure their changes are mutually coherent.
Of course, the extreme case of a coordinated domain update in which all domains participate is called a minor release.
At this point, you should now understand the rationale for periodic releases (both major and minor) &mdash; to reestablish coherency among domain schema documents that have accumulated a few independent updates.

In practice the expectation is that a small number of independent domain updates will not have significant impact on IEPDs because the majority of changes contained in them will not be on data components shared (i.e. reused) across the domain models.



 

#### Repositories (release, publication)

#### Release optimization


- Collaboration

### 5.2 Schema document namespacing and versioning

- Important to domains who submit content in XSD.
- Describe the correlation of target namespaces and XML schema documents.
- Each schema document is assigned a unique target namespace.
- Namespace Syntax.
- URIs (Uniform Resource Identifiers), syntax, purpose, etc.

### 5.3 NIEM release cycle

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

### 5.4 Domain update

- Domain independence and self-serviced
- Types of domain updates: incremental vs. replacement
- Multi-domain coordinated domain update
- Change content preparation and model management
- Metadata, lineage, change log

### 5.5 Conformance and quality assurance

- General and specific conformance
- Verification (who, what, how, when, etc.)

----

### <&mdash;&mdash; Return to:  [Table of Contents](./index.html)

----

