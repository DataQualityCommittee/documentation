## XBRL US Center for Data Quality Committee Guidance
# Dimensional Modeling Guidance – Legal Entities & Consolidation Guidance
### Draft for Committee Approval
### October 2018

## Overview
The FASB introduced two new axes in the 2017 taxonomy:  ConsolidatedEntitiesAxis and OwnershipAxis. These axes facilitate a more uniform approach to tagging values of entities other than the reporting entity. This document is intended to provide comprehensive guidance on how to tag values of the reporting entity and third parties in an XBRL document. 

The FASB has issued a Taxonomy Implementation Guide, Dimensional Modeling for Disclosures of Consolidated and Nonconsolidated Entities, to illustrate the intended modeling for the reporting requirements of that topic. This guidance issued by the DQC is intended as a supplement to the guidance provided by the FASB in the implementation guide, and provide explanation of the logic used in developing DQC quality rules.

A registrant's financial statements can include data of a company other than the consolidated reporting entity. For example, there may be information about a co-registrant, a spin-off, a related party, an acquired entity, the parent holding company. There may also be disclosures about transactions with other parties, such as customers. Often there are disclosures about the ownership relationship of these entities. The axes used to tag these disclosures conveys important information as to the meaning of the tagged value and can change its meaning, so it is necessary to establish consistent guidance on the use of axes to avoid confusion in their intended use.

## Legal Entity Axis
The LegalEntityAxis allows filers to report values for legal entities whether or not they are included in the consolidated totals of the reporting entity.<sup>[1](#1)</sup>

The members on the LegalEntityAxis should only be extension members representing the name of the legal entity. Rule DQC.US.0001 tests whether filers use inappropriate members on certain axes in the US GAAP Financial Reporting Taxonomy (Taxonomy). The rule validates that members on the LegalEntityAxis should be extensions members, with possible exceptions for legal entities defined in the US GAAP taxonomy. These are listed in the documentation of rule DQC.US.0001.

The combination of LegalEntityAxis with a member in the context of a fact for a primary line item, such as "Revenues," is interpreted by users of the data to be the revenue of that particular entity.

Examples of legal entities that might be used to tag Revenues include:

|Meaning when reported in the Registrant's Filing:|Concept|Legal Entity [Axis]|
|---|---|---|
|Revenues of a co-registrant|Revenues|Co-registrant Name|
|Revenues of a potential acquiree before the date of acquisition|Revenues|Potential Acquiree Name|
|Revenues of the parent owner of the registrant that are not included in the consolidated revenues of the registrant.|Revenues|Parent Owner Name <br />(Note: Do not use the ParentCompanyMember as that member presents the parent company within the consolidated group of the registrant.)|
|Revenues of subsidiary reported as a stand-alone entity. <br />(Note: If the values are presented as part of the consolidating financial information or schedules of the registrant, the ConsolidatedEntitiesAxis is used)|Revenues|Subsidiary Name|

The Legal Entity Axis allows filers to report values for legal entities whether or not they are included in the consolidated totals of the reporting entity. The Legal Entity Axis is a mechanism that allows companies to report financial balances and transactions for legal entities other than the registrant.

## Consolidated Company Reporting 
To report the aggregate sales of  Subsidiary Inc. in the filing of  Holding Inc. the Legal Entity Axis is used with the Revenues line item and the Member 'Subsidiary Inc'. This reflects the actual revenues of Subsidiary Inc. as a stand alone entity. It does not communicate how much of that revenue was made to  the Holding Company, other subsidiaries in the group or external customers.

To report the disaggregated values between entities in a consolidated group a different axis must be used. To disaggregate values between companies in a consolidated group the ConsolidatedEntitiesAxis is used.

To tag the value of a legal entity's revenues from sales to other parties within the same consolidated group, the value of revenues is differentiated using the _ConsolidationItemsAxis_ and the _ConsolidatedEntitiesAxis_. 

The following example shows how Holding Inc. has reported the Revenues of two subsidiaries and the associated eliminations. 

**Example of Holding Inc. consolidated** 

|For the Year Ended 20XX|Sub1|Sub2|Eliminations|Consolidated|
|---|---|---|---|---|
|Revenues|24|830|-34|820|
|See Row below:|3|7|9|11|

The second row links to the table shown below. This table shows every possible breakdown that could be reported and the members that would be used.

**Example of Holding Inc. consolidated** 

|Row|Line Item|Legal Entity Axis|Consolidated Entities Axis|Consolidation Items Axis|Value|
|---|---|---|---|---|---|
|1|Revenues|none|Subsidiary Inc.|Consolidation Eliminations [Member]|-4|
|2|Revenues|none|Subsidiary Inc.|Reportable Legal Entities [Member]|24|
|3|Revenues|none|Subsidiary Inc.|none|20|
|4|Revenues|none|Subsidiary2 Inc.|Consolidation Eliminations [Member]|-30|
|5|Revenues|none|Subsidiary2 Inc.|Reportable Legal Entities [Member]|830|
|6|Revenues|none|Subsidiary2 Inc.|none|800|
|7|Revenues|none|none|Consolidation Eliminations [Member]|-34|
|8|Revenues|none|none|Reportable Legal Entities [Member]|854|
|9|Revenues|none|none|none|820|

The value of -$4 is tagged with the Revenues concept with two dimensions.  The first is the _ConsolidatedEntitiesAxis_ with the member _SubsidiaryIncExtensionMember_ and the second axis _ConsolidationItemsAxis_ with the _ConsolidationEliminationsMember_. The value is entered as a negative amount of -$4. 

The value of -$30 is tagged with the Revenues concept with two dimensions.  The first is the _ConsolidatedEntitiesAxis_ with the member _Sub2IncExtensionMember_ and the second axis _ConsolidationItemsAxis_ with the _ConsolidationEliminationsMember_. The value is entered as a negative amount of -$30 as it is an elimination.

The value of -$34 is tagged with the Revenues concept with one dimension.  The axis _ConsolidationItemsAxis_ with the _ConsolidationEliminationsMember_ is used to represent the sum of all eliminations. The value is entered as a negative amount of -$30.

The value of $854 represents the value or Revenues prior to consolidation eliminations. To record this the Revenues tag should be used with the dimension _ConsolidationItemsAxis_ and the member _ReportableLegalEntitiesMember_.

The inclusion of a legal entity axis and the associated members does not imply that these legal entities are consolidated.  The _ConsolidatedEntitiesAxis_ can be used however to show how the values of different entities are being consolidated. Unlike the Legal Entity Axis the _ConsolidatedEntitiesAxis_ is relative to the reporting entity.

If the filer wants to report the value for all legal entities net of eliminations then the default is used. If the filer wants to report a value for all legal entities owned by the company prior to elimination then the _ReportableLegalEntitiesMember_ should be used in conjunction with the axis _ConsolidationItemsAxis_ to tag the values of $854 shown below.

|Line Item|Subsidiary Inc.|Subsidiary 2 Inc.|Total Before Elimination|Elimination|Consolidated Holding Inc.|
|---|---|---|---|---|---|
|Revenues|24|830|854|34|820|

The value of $24 could be tagged either of the following ways:

||Line Item|Dimension 1|Dimension 2|Value|
|---|---|---|---|---|
|1|Revenues|ConsolidatedEntitiesAxis = SubsidiaryIncExtensionMember|ConsolidationItemsAxis = ReportableLegalEntitiesMember|24|
|2|Revenues|LegalEntityAxis = SubsidiaryIncExtensionMember||24|

The value of 24 is tagged with different members depending if the value is reported as a standalone legal entity versus part of a consolidated group. 

Case 1 should be used for any consolidated entities reported by a registrant.

Case 2 is used when tagging the details of a legal entity if it is consolidated or not. Case 2 can only be used on a specific named entity. This means a base US GAAP or SRT member like _ParentCompanyMember_ or _SubsidiariesMember_ should not be used with LegalEntityAxis.**

**The _ReportableLegalEntitiesMember_ member should never be used on the legal entity axis.**

**The _ConsolidatedEntitiesAxis_ can only be used with members that represent entities or groupings of entities that are consolidated.**

Figure 3 summarizes consolidated reporting situations and the appropriate tagging.

**Figure 3** 

||Concept|Legal Entity [Axis]|Consolidated Entities [Axis]|Consolidation Items [Axis]|
|---|---|---|---|---|
|Revenues for Registrant, net of eliminations|Revenues||||
|Revenues for Registrant before eliminations|Revenues|||Reportable Legal Entities [Member]|
|Revenues of non consolidated Subsidiary reported as a stand-alone|Revenues|Subsidiary Name|||
|Revenues of Subsidiary as part of consolidating schedule (before eliminations)|Revenues||Subsidiary Name|Reportable Legal Entities [Member]|
|Revenues of Subsidiary eliminated in consolidation|Revenues||Subsidiary Name|Consolidation, Eliminations [Member]|
|Total of all revenues eliminated in consolidation|Revenues|||Consolidation, Eliminations [Member]|
|Revenues of acquired entity for period prior to acquisition|Business Acquisition, Revenue Reported by Acquired Entity for Last Annual Period|Acquired Entity Name|||
|Revenues of acquired entity included in the consolidated results (After Eliminations)|Revenues||Acquired Entity Name||

**Groupings on the Consolidated Entities Axis**
The _ConsolidatedEntitiesAxis_ can have different hierarchies or trees associated with it depending on how the values are consolidated. For example, the company may group consolidated entities into groups such as guarantor and non guarantor subsidiaries and issuer subsidiaries. These are shown under the domain and can include child members if multiple guarantors and non guarantor members are reported. These relationships however do not represent how the legal structure of the subsidiaries are consolidated or which subsidiaries own each other. These trees just provide different aggregations of the consolidated entities. 

If the  _ConsolidatedEntitiesAxis_ is used, its members must be entities or groupings of entities that are actually consolidated. Any numbers used in conjunction with this axis must be a disaggregation of the consolidated total. 

## Transactions with Customers 
The values for transactions with customers are typically going to use the MajorCustomersAxis (standard label is Customer [Axis])

||Concept|Legal Entity [Axis]|Customer [Axis]|
|---|---|---|---|
|Revenues for Registrant from Customer|Revenues|None|Customer Name|
|Revenues for non consolidated Subsidiary from Customer|Revenues|Subsidiary Name|Customer Name|
|Revenues of Customer|Revenues|Customer Name|None|

## Transactions with Related Parties
The values for transactions with related parties are typically going to use the RelatedPartyTransactionsByRelatedPartyAxis (standard label is Related Party [Axis])

||Concept|Legal Entity [Axis]|Related Party [Axis]|
|---|---|---|---|
|Revenues for Registrant|Revenues|None|None|
|Revenues for Related Party|Revenues|Related Party Name|None|
|Revenues for Related Party from Registrant|RevenueFromRelatedParties|Related Party Name|Registrant Name|
|Revenues for Registrant from Related Party|RevenueFromRelatedParties|None|Related Party Name|
|Revenues for Parent Owner of Registrant <br />(This is an extension member for the parent entity and not ParentCompantMember)|Revenues|Parent Owner Name|None|

## Using the Ownership Axis
The ConsolidationItemsAxis and ConsolidatedEntitiesAxis should not be used to establish ownership relationships. Especially in the case of the Legal Entity [Axis] which may contain entities that are not included in the consolidated results, no inference can be made about the relationships among entities.

Instead, the OwnershipAxis is used in combination with the LegalEntityAxis to establish the percentage ownership among entities. It is not used for reporting line items such as revenues reported of the owned entity.

The FASB Taxonomy Implementation Guide, Dimensional Modeling for Disclosures of Consolidated and Nonconsolidated Entities, provides Example 5 of a complex ownership structure and the appropriate use of these axes.

Basically, the name of the entity that owns the other is reported on the Legal Entity [Axis] and the owned entity is reported on the Ownership [Axis]. If no member is reported on the Legal Entity [Axis], it is assumed the reporting entity or registrant is the owner.

DQC.US.0078 will identify when one of the standard taxonomy ownership elements is used without the Ownership axis and report an error:

1. ManagingMemberOrGeneralPartnerOwnershipInterest
1. MinorityInterestOwnershipPercentageByParent
1. MinorityInterestOwnershipPercentageByNoncontrollingOwners
1. LimitedLiabilityCompanyLLCOrLimitedPartnershipLPMembersOrLimitedPartnersOwnershipInterest
1. SubsidiaryOfLimitedLiabilityCompanyOrLimitedPartnershipOwnershipInterest

This axis should not be used for the ownership of equity method investments and security holdings or as a substitute for the consolidated entities axis on a consolidating schedule. There are specific axis and line items included in the taxonomy for reporting the equity method ownership percentage and the equity method investment.

_What happens when a company has a cross holding in 2 subsidiaries?_

The ownership axis is from the perspective of the reporting entity.

In the example below, the ownership of company B & C represents a cross holding. 
![Example 1](images/leiconsolidations01.png?raw=true)

To represent this in XBRL the links are represented in the instance document the values would be represented as follows:

|Element|Amount|Legal Entity Axis|Ownership Axis|
|---|---|---|---|
|Company A owns 65% of Company C|65%|none|CompanyCMember|
|Company A owns 75% of Company B|75%|none|CompanyBMember|
|Company C owns 25% of Company B|25%|CompanyCMember|CompanyBMember|
|Company B owns 35% of Company C|35%|CompanyBMember|CompanyCMember|

The consolidated entities axis should not be used to represent ownership. (See rule 70)

The ownership axis should not be used to represent the ownership structure of the consolidated group. 

## Co Registrants
It is expected that co-registrants will use the legal entity axis to identify each legal entity.

## Summary
There are a number of axes that could be used to represent the relationships between different reporting entities.

The table below summarizes these relationships and what the different intersections of axes mean when combined with the revenue element of a holding company. 

**Table: Dimension Combinations** 

|Meaning when reported in the Registrant Company Filing.|Revenue Value|Consolidated Entities [Axis]|Legal Entity [Axis]|Major Customer [Axis]|Disposal Group Name [Axis]|Consolidation Items [Axis]|
|---|---|---|---|---|---|---|
|Aggregate Revenues of Registrant Inc. (Net of eliminations)|820M|none|none|none|none|none|
|Revenues of Subsidiary Inc. as a portion of Registrant Inc. Revenue (After eliminations)|20M|Subsidiary Inc. [Member]|none|none|none|none|
|Aggregate Revenues of Non Consolidated Subsidiary Inc. as a stand alone entity|24M|none|Subsidiary Inc. [Member]|none|none|none|
|Revenues of Registrant Inc. applicable  to consolidated entity Subsidiary Inc. (prior to  eliminations)|24M|Subsidiary Inc. [Member]|none|none|none|Reportable Legal Entities [Member]|
|Revenues of Registrant Inc. attributable to the Subsidiary Inc. Company eliminated on consolidation (Intercompany sales of Subsidiary Inc.)|-4M|Subsidiary Inc. [Member]|none|none|none|Consolidation Eliminations [Member]|
|Aggregate Revenues of Registrant Inc. that was eliminated upon consolidation|-34M|none|none|none|none|Consolidation Eliminations [Member]|
|Revenues of Registrant Inc. from sales to Major Customer Company.|35M|none|none|Major Customer Company [Member]|none|none|
|Revenues of Subsidiary Inc. from sales to Major Customer Company|12M|none|Subsidiary Inc. [Member]|Major Customer Company [Member]|none|none|

### Summary of when to use an axis
The following table summarizes when an axis should be used:

|Axis|Constraints|
|---|---|
|Legal Entity Axis|Use to report detailed data about an entity that is not the consolidated reporting entity or is a co-registrant. Any member on this axis must be a named specific legal entity|
|Consolidation Items Axis|Use to disaggregate consolidated totals between values before eliminations and after eliminations|
|Consolidated Entities Axis|Use this axis to represent the values in a consolidating schedule. Non consolidated entities cannot be included on this axis.|
|Ownership Axis|Used to represent the ownership of the company and to report values that exist between the reporting entity and the entity actually owned. If the holding company does not own the company or plan to hold the company then it should not be used with this axis. This axis does not have to aggregate to a valid total. This axis should only be used to report data that represents a relationship between the reporting entity and the owned company. It should not be used to report information about the owned company such as revenues. Revenues would use either the legal entity axis or Consolidated Entities axis. This axis is used to report data like ownership percentage, date holding acquired, date holding sold, change in ownership percentage etc.|
|Major Customers Axis|Used to represent a relationship with a customer. This axis could be used for example to report sales to a customer, receivables from a specific customer etc. It is always used to report amounts relative to the reporting entity.|
|Related Party Axis|Used to represent a relationship with a related party. This axis could be used for example to report sales to a related party, receivables from a specific related party etc. It is always used to report amounts relative to the reporting entity.|

## Appendix 1 - Complex Consolidation Example
The example shows the financials for the parent company prior to consolidation. A consolidated group can have multiple holding companies depending on which level of consolidation is being referenced.

In the example below the company should use the _ConsolidatedEntitiesAxis_ with the _ParentCompanyMember_. The _ParentCompanyMember_ should only be used on this axis. However given that this represents a consolidated amount the _ConsolidationItemsAxis_ also needs to be used with the _ReportableLegalEntitiesMember_ to indicate a pre-consolidation amount. The values should be tagged using the _ConsolidatedEntitiesAxis_ with the member _ParentCompanyMember_  (post consolidation amount) and the _ConsolidationItemsAxis_ with the member  _ReportableLegalEntitiesMember_ (pre consolidation amount).
![Example 2](images/leiconsolidations02.png?raw=true)

### Condensed Consolidated Statements
When reporting condensed consolidated statements, companies will break down consolidated numbers showing the Parent company, Guarantors and non guarantor Subsidiaries. (See figure  below) In these cases the entities values are reported pre consolidation and should therefore use the _ConsolidatedEntitiesAxis_ and _ConsolidationItemsAxis_ as defined above.
![Example 3](images/leiconsolidations03.png?raw=true)

The _ConsolidatedEntitiesAxis_ with the reportable entities member allows grouping of legal entities to be defined as single members such as subsidiaries and guarantors. The consolidated values should be the default value for the line item.

In this case, the pre-consolidation entities are tagged with the _ConsolidatedEntitiesAxis_ and respective members _ParentCompanyMember_, _GuarantorSubsidiariesMember_, and _NonGuarantorSubsidiariesMember_. It is important to note that the _ParentCompanyMember_ should be used for the parent and not the legal Entity Name of the company as this would represent the consolidated values of the entity. When reporting numbers for the Parent company the _ParentCompanyMember_ should always be used. 

The following examples describe the financials of  "Verso Corporation" aka "Verso" and "Verso Paper Holdings LLC" aka  "Verso (Paper) Holdings". "Verso" is the ultimate parent, but the examples also show the consolidation of "Verso (Paper) Holdings".  

The following figure shows the balance sheets for both "Verso" and "Verso Paper Holdings". "Verso" is the registrant reporting entity.  All the numbers reported for "Verso Paper Holdings" use the _ConsolidatedEntitiesAxis _and a member for Verso Paper Holdings (_VersoPaperHoldingsMember_) to distinguish the second column of values.
![Example 4](images/leiconsolidations04.png?raw=true)

Note that this data is the consolidated data for "Verso Paper Holdings" and as such only needs the legal entity dimension.  The figure below shows a further breakdown of "Verso Paper Holdings". The value of 900,941 for total Assets on the figure above is the same value representing the aggregate assets in the figure below.

The consolidating schedule below represents the values for the consolidated entity of "Verso Paper Holdings".  All of the values in the disclosure will use the _LegalEntityAxis_ and the member _VersoPaperHoldingsMember_.  This disclosure shows values for the Parent Company but ParentCompanyMember cannot be used on the legal Entity axis as discussed earlier.
![Example 5](images/leiconsolidations05.png?raw=true)

To tag these balance sheet elements the _ConsolidatedEntitiesAxis_ should be used with the _ParentCompanyMember_ because it is a consolidating schedule which includes all the components of the aggregation. Just using this axis by itself represents the value post consolidation. To represent the elements pre-consolidation, the _ConsolidationItemsAxis_ and _ReportableLegalEntitiesMember_ should be added to the values. 

The value of the assets of the Parent of "Verso Paper Holdings" in the filing of "Verso"  uses the following line items and dimensions to tag the value of the 1,396,872.

|Line Item|Dimension 1|Dimension 2|Dimension 3|
|---|---|---|---|
|Assets|ConsolidatedEntitiesAxis = ParentCompanyMember|ConsolidationItemsAxis = ReportableLegalEntitiesMember|LegalEntityAxis = VersoPaperHoldingsMember|

In addition all the other members representing groups of companies such as for guarantor subsidiary, non-guarantor subsidiary, etc. would also appear on the _ConsolidatedEntitiesAxis_ with the dimension for _ConsolidationItemsAxis=ReportableLegalEntitiesMember_ and the _LegalEntityAxis=VersoPaperHoldingsMember_.

The following diagram illustrates the tagging for reporting data for consolidated Financials for multiple parent companies.
![Example 6](images/leiconsolidations06.png?raw=true)

## Notes
<a name="#1"></a><sup>1</sup>:
     In a generic XBRL filing, values for a specific entity would normally be represented using the entity CIK identifier. The SEC however, only allows a company to use a single CIK identifier in its filing. The values reported for other legal entities included in the filing cannot use the entity CIK identifier. The Legal Entity Axis is a mechanism that allows companies to report financial balances and transactions for legal entities other than the filer.