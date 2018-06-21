## XBRL US Center for Data Quality Committee Guidance
# Dimensional Modeling Guidance – Legal Entities & Consolidation Guidance
### Draft for Committee Review
### June 2018

## Overview
This document is intended to add additional explanation to the FASB implementation guide on Dimensional Modeling for Disclosures of Consolidated and Nonconsolidated Entities. In addition this document identifies DQC rules to ensure that that the practices defined in the FASB implementation guide are implemented.

## Legal Entity, Ownership & Consolidation Axis
A filer's financial report can include data of a company other than the consolidated entity. This occurs when an entity reports information about another company because it is a subsidiary, a spin off, an acquisition, the parent holding company, etc. The axis used to report values for a company other than the consolidated entity is often inconsistent. For example, filers often use axes, such as the Customer Axis or Related Party Axis, to report values for these companies.

The values for a legal entity other than the consolidated entity should be reported using the Legal Entity Axis and a member representing that legal entity as if it was a standalone entity. Values reported for the legal entity represent the amounts applicable to that legal entity. These values do not represent transactions between the legal entity and the reporting entity. For example, sales of $20 million for Company XYZ that is reported as a legal entity in the filing of registrant ABC Company are sales of XYZ Company and NOT sales of ABC Company to XYZ Company or sales of XYZ Company to ABC Company. 

This is an important distinction that is applicable to the Legal Entity Axis. In addition, if the amount is a balance sheet item such as inventory, the value reported for XYZ Company on the Legal Entity Axis is the inventory of XYZ Company. The Legal Entity Axis allows filers to report values for legal entities whether or not they are included in the consolidated totals. In a generic XBRL filing, values for a specific entity would normally be represented using the entity CIK identifier of the context. The SEC however, only allows a company to use a single CIK in its filing. The values reported for other entities included in the filing cannot use the entity CIK identifier for the other entity. The Legal Entity Axis is a mechanism to allow companies to report financial balances and transactions for legal entities other than the registrant.

In other cases, companies want to report the value of transactions with counterparties or the balance of an account owed to another party. For example, ABC Company wants to report that it had sales to XYZ Company of $5 million. In the filing of ABC Company, the Legal Entity Axis and XYZ Company Member should not be used to represent these sales. Using the Legal Entity Axis would mean that XYZ Company has $5 million in sales as discussed earlier. In order to reflect the nature of these related transactions between parties, a different axis must be used depending on the nature of the transaction. The axis used can depend on the nature of the relationship between the parties.

There are a number of axes that could be used depending on the relationship. For example, when reporting sales to customers, the Customer Axis *MajorCustomersAxis* is used to report sales broken down by customer. If the company is part of a disposal group that is held for sale, the Disposal Group Name Axis could be used if sales are included in the value of sales reported for registrant ABC Company. Either way, these axes are used when they show a disaggregation of the revenues value for registrant Company ABC by a different categorization, such as by customer, related party or disposal group. Sales can be broken down by legal entity as well, but the Legal Entity Axis does not require that the entity is included in the consolidated value.

The table shows what the different intersections of axes mean when combined with the revenue element of registrant ABC Company. For example, the intersection of the Legal Entity Axis and the member XYZ Company with the Customer Axis and member BUY Company is the aggregate sales of XYZ Company to BUY Company.

**Table: Dimension Combinations**

|**Revenues for  \ABC Company**|**Consolidated Entities [Axis]**|**Legal Entity [Axis]**|**Customer [Axis]**|**Disposal Group Name [Axis]**|**Consolidation Items [Axis]**|
|--------|--------|--------|--------|--------|--------|
|Aggregate revenues of ABC Company (Net of eliminations)   |*(Default)*|*(Default)*|*(Default)*|*(Default)*|*(Default)*|
|Aggregate revenues of XYZ Company (Net of eliminations of XYZ)   |*(Default)*|XYZ Company [Member]   |*(Default)*|*(Default)*|*(Default)*|
|Aggregate revenues of ABC Company that were eliminated upon consolidation   |*(Default)*|*(Default)*|*(Default)*|*(Default)*|Consolidation Eliminations [Member]   |
|Aggregate revenues of XYZ Company that were eliminated in the consolidation of XYZ Company   |*(Default)*|XYZ Company [Member]   |*(Default)*|*(Default)*|Consolidation Eliminations [Member]   |
|Sales of ABC Company to BUY Company   |*(Default)*|*(Default)*|BUY Company [Member]   |*(Default)*|*(Default)*|
|Sales of XYZ company to BUY Company   |*(Default)*|XYZ Company [Member]   |BUY Company [Member]   |*(Default)*|*(Default)*|
|Sales of ABC company made to BUY Company that were eliminated upon consolidation   |BUY Company [Member]   |*(Default)*|*(Default)*|*(Default)*|Consolidation Eliminations [Member]   |
|Revenues of ABC Company attributable to the disposal Group XYZ Company (Only if disposal group revenue is in revenue).  |*(Default)*|*(Default)*|*(Default)*|XYZ Company [Member]   |*(Default)*|
|Revenues of ABC Company attributable to the disposal Group XYZ Company eliminated on consolidation (*Intercompany sales of XYZ company*)   |XYZ Company [Member]   |*(Default)*|*(Default)*|*(Default)*|Consolidation Eliminations [Member]   |

### Using the Consolidation Axis with Legal Entities

When a fact value is reported in an XBRL filing using a member on the legal entity axis, the value reported for the line item represents the value for that legal entity. For example, if XYZ company, as the registrant, reports a value of $110 using the accounts receivable element, the legal entity axis and ABC Company member, the value is the accounts receivable for ABC Company. It does not represent the value of Accounts Receivable due to XYZ company from ABC company. If a legal entity member is used on the legal entity axis this represents the value applicable to the standalone entity regardless of whether it is consolidated or not. In fact, the value of $110 represents the value of accounts receivable before any consolidation eliminations are applied. As another example, the value of revenues for a value reported using the legal entity axis and company member is the aggregate revenue of the entity whether sold internally to a company that is part of the same consolidated group or to an external party. 

To tag the value of a legal entity's revenues from sales to other parties within the same consolidated group, the value of revenues is differentiated using the *ConsolidationItemsAxis* and the *ConsolidatedEntitiesAxis*. For example, company ABC has sales of $100, and $10 of those sales are to other companies in the same consolidated group.

Example of Intercompany Sales For Company A as part of XYZ Company Consolidated

|Line Item   |Company ABC   |Eliminations   |Company A's contribution to Consolidated XYZ (Registrant) Revenues   |
|--------|--------|--------|--------|
|Revenues   |100   |10   |90   |

The value of $100 represents the Revenues of ABC Company as a stand alone entity and would be tagged with the Revenues concept and the dimension *LegalEntityAxis* and member *ABCCompanyMember*.  This represents the revenue for ABC company as a standalone entity. The value of $10 represents the sales of ABC Company to XYZ Company when consolidated in the financial statements of XYZ Company.  At a minimum, the filing needs to reflect that this is an elimination of $10 of sales applicable to ABC Company relative to the XYZ consolidated financial statements. This means the legal entity axis cannot be used for the $10. In this case the *ConsolidatedEntitiesAxis* is used with the ABC Member. The value of $10 is tagged with the Revenues concept with two dimensions. The first is the *ConsolidatedEntitiesAxis* with the member *ABCCompanyMember* and the second axis  *ConsolidationItemsAxis* with the *ConsolidationEliminationsMember*. The value is entered as a negative amount of -$10. If the *ConsolidatedEntitiesAxis* and *ABCCompanyMember* were not added then the $10 would be the Revenues eliminated for all consolidated subsidiaries. The next example expands on this. Lastly the value of $90 is tagged with the Revenues tag and *ConsolidatedEntitiesAxis* with the member *ABCCompanyMember*. Once again, if the value of $90 is also Revenues for all of XYZ Company then the  *ConsolidatedEntitiesAxis* is not required.

**Example of XYZ consolidated**

|Line Item   |Company ABC   |Company BCD   |Company ABC Eliminations   |Company BCD Eliminations   |Elimination   |Consolidated XYZ (registrant)   |
|--------|--------|--------|--------|--------|--------|--------|
|Revenues   |100   |830   |10   |20   |30   |900   |

In this case XYZ Company has reported the Revenues of two subsidiaries and the associated eliminations. 

The value of $100 represents the Revenues of ABC Company as a stand alone entity and is tagged with the Revenues concept and the dimension *LegalEntityAxis* and member *ABCCompanyMember*.

The value of $830 represents the Revenues of BCD Company as a stand alone entity and is tagged with the Revenues concept and the dimension *LegalEntityAxis* and member *BCDCompanyMember.*

The value of $10 is tagged with the Revenues concept with two dimensions. The first is the *ConsolidatedEntitiesAxis* with the member *ABCCompanyMember* and the second axis *ConsolidationItemsAxis* with the*ConsolidationEliminationsMember*. The value is entered as a negative amount of -$10. 

The value of $20 is tagged with the Revenues concept with two dimensions. The first is the *ConsolidatedEntitiesAxis* with the member *BCDCompanyMember* and the second axis *ConsolidationItemsAxis* with the*ConsolidationEliminationsMember.*The value is entered as a negative amount of -$20.

The value of $30 is tagged with the Revenues concept with one dimension. The axis *ConsolidationItemsAxis* with the *ConsolidationEliminationsMember* is used to represent the sum of all eliminations. The value is entered as a negative amount of -$30.

If the company reports a value of $930 that represents the value or Revenues prior to consolidation eliminations then the Revenues tag should be used with the dimension *ConsolidationItemsAxis* and the member *ReportableLegalEntitiesMember*.

It is important to remember that the Legal entity axis is **not** relative to the reporting entity. In fact the legal entity axis is used to report values as if the member on the legal entity axis replaced the CIK reported in the entity context of the filing. This was a deliberate decision by the SEC to ensure that multiple CIK's would not be reported in the entity context of the instant.

The inclusion of a legal entity axis and the associated members does not imply that these legal entities are consolidated. The *ConsolidatedEntitiesAxis* can be used however to show how the values of different entities are being consolidated. Unlike the Legal Entity Axis the *ConsolidatedEntitiesAxis* is relative to the reporting entity.

If the filer wants to report the value for all legal entities net of eliminations then the default is used. If the filer wants to report a value for all legal entities owned by the company prior to elimination then the *ReportableLegalEntitiesMember* should be used in conjunction with the axis *ConsolidationItemsAxis* to tag the values of $930 shown below.

|Line Item   |Company ABC   |Company BCD   |Total Before Elimination   |Elimination   |Consolidated XYZ   |
|--------|--------|--------|--------|--------|--------|
|*Revenues*|100   |830   |930   |30   |900   |

The value of $100 could be tagged either of the following ways:

||Line Item   |Dimension 1   |Dimension 2   |Value   |
|--------|--------|--------|--------|--------|
|1   |*Revenues*|*LegalEntityAxis = ABCCompanyMember*||100|
|2   |*Revenues*|*ConsolidatedEntitiesAxis = ABCCompanyMember*|*ConsolidationItemsAxis = ReportableLegalEntitiesMember*|100|

Tagging using  1 and 2 are equivalent. However the tagging using these different methods depends on the circumstances. Method 1 is used when tagging the details of a legal entity if it is consolidated or not. Second, method 1 can only be used on a specific named entity. This means a generic member like *ParentCompanyMember* or subsidiary member cannot be used with LegalEntityAxis. The second method should be used for consolidated entities that are disclosed in a consolidating schedule. So this axis will typically be used when grouping various types of legal entities together like the parent company, subsidiaries etc. 

To highlight the difference between these two methods, If the value of $100 only had used dimension1 when reporting for XYZ company the $100 would mean 2 different things. Under Option 1 the $100 is all Revenue for ABC Company. Under option 2 the $100 would be the Revenue of ABC Company after eliminations with other companies comprising the XYZ Company group. The *ConsolidatedEntitiesAxis* is relative to the reporting entity.

The *ReportableLegalEntitiesMember* member should never be used on the legal entity axis. 

In summary, the following elements and members are used to report each of the following scenarios:

|Reporting Assertion   |Value   |Line Item   |Axis/Member   |
|--------|--------|--------|--------|
|External and Intercompany Sales of Consolidated Legal Entity A   |$100   |Revenues   |*LegalEntityAxis/Co*A*Member **OR****ConsolidationItemsAxis/ReportableLegalEntitiesMember AND ConsolidatedEntitiesAxis/Co*A*Member*|
|Intercompany Sales of Consolidated Legal Entity A    |($10)   |Revenues   |*ConsolidatedEntitiesAxis/Co*A*Member**ConsolidationItemsAxis/ConsolidationEliminationsMember*|
|External Sales of Consolidated Legal Entity A    |$90   |Revenues   |*ConsolidatedEntitiesAxis/Co*A*Member*|
|External Sales of all Consolidated Entities    |$900   |Revenues   |*DEFAULT*|
|External & Intercompany Sales of all Consolidated Legal Entities    |$930   |Revenues   |*ConsolidationItemsAxis/ReportableLegalEntitiesMember*|
|Intercompany Sales of all Consolidated Legal Entities    |($30)   |Revenues   |*ConsolidationItemsAxis/ConsolidationEliminationsMember*|

**Consolidated Entities Axis**

The consolidated Entities Axis can have different hierarchies or trees associated with it depending on how the values are being shown to be consolidated. For example, the company may group consolidated entities into groups such as guarantor and non guarantor subsidiaries and issuer subsidiaries. These should be shown as a flat list under the domain. These do not represent how the legal structure of the subsidiaries are consolidated or which subsidiaries own each other. These trees just provide different aggregations of the consolidated entities. 

If the  *ConsolidatedEntitiesAxis* is used, its members must be entities or groupings of entities that are actually consolidated. Any numbers represented on this axis must be a disaggregation of the consolidated total. 

### Representing Legal Ownership

To represent the actual legal ownership structure of the company the *OwnershipAxis* should be used. This axis is used to represent the ownership of one company by another company. This axis should not be used; however, for the ownership of equity method investments and security holdings.

This axis should not be used as a substitute for the consolidated entities axis on a consolidating schedule. 

This axis allows the company to unambiguously report information such as ownership percentages in companies that the holding company wholly or partly owns. This axis should only have one hierarchical tree defined on the ownership axis in a filing and that should mirror the current ownership structure of the group. The data associated with the ownership relationship is represented in the instance document. The reason for this is that the data associated with the relationship changes regularly and there may be multiple ownership percentages between two companies during a reporting period. 

To represent the ownership percentage between two entities other than the reporting entity, the reporting company must use the element representing ownership percentage plus the legal entity axis with the member name of the company that owns the subsidiary and the ownership axis with the member name of the company owned. If the ownership axis is used and no legal entity axis is defined then this means the reporting company is the owner.

*What happens when a company is owned by 2 companies in the group?*

This is permitted on the axis and the same member would appear twice in the ownership tree. Once as a child of one company and again as a child of another company. 

*What happens when a company has a cross holding in 2 subsidiaries?*

This cannot be represented in a tree but can be represented in the instance. The ownership axis is from the perspective of the reporting entity and the cross holding of 2 subsidiaries should not be represented as one entity owning the other. In fact, this is disallowed in XBRL. 

In the example below, the ownership of company B & C cannot be shown in a tree as it is a cross holding. 

![Example 1](images/leiconsolidations01.png?raw=true)

To represent this in XBRL the links between B and C would not be shown. However in the instance document the values would be represented as follows:

|Element   |Amount   |Legal Entity Axis   |*Ownership Axis*|
|--------|--------|--------|--------|
|PercentageOwnership   |65%   |CompanyAMember   |*CompanyCMember*|
|PercentageOwnership   |75%   |CompanyAMember   |*CompanyBMember*|
|PercentageOwnership   |25%   |CompanyBMember   |*CompanyCMember*|
|PercentageOwnership   |35%   |CompanyCMember   |*CompanyBMember*|

Effectively any cross holding between companies in the group either directly or indirectly should be shown in the instance but the structure of the tree should follow the hierarchy represented in Exhibit 21 [(Example)](https://www.sec.gov/Archives/edgar/data/895421/000119312516473553/d48186dex21.htm) of the 10-K filing.

The consolidated entities axis should not be used to represent ownership. (See rule 70)

An example of an ownership percentage is shown below. This is a common disclosure and the ownership axis provides a mechanism to report these percentages. In the disclosure below, the reporting entity owns 85% of URL Harborside.

On May 21, 2014, the Company entered into a joint venture agreement with Ironstate Harborside-A LLC ("ISA") to form Harborside Unit A Urban Renewal, L.L.C. ("URL-Harborside"), a newly-formed joint venture that will develop, own and operate a high-rise tower of approximately 763 multi-family apartment units above a parking pedestal to be located on land contributed by the Company at its Harborside complex in Jersey City, New Jersey (the "URL Project"). The Company owns an **85 percent interest** in URL-Harborside and the remaining interest is owned by ISA, with shared control over major decisions such as approval of budgets, property financings and leasing guidelines. The construction of the URL Project is estimated to cost a total of approximately $320 million (of which development costs of $210.2 million have been incurred by URL-Harborside through December 31, 2015). The URL Project is projected to be ready for occupancy by the fourth quarter of 2016. The venture has a construction/permanent loan with a maximum borrowing amount of $192 million (with **$63.9** million outstanding as of December 31, 2015), which bears interest at a rate of 5.197 percent and matures in August 2029. The Company does not expect to fund any future development costs of the project, as future development costs will be funded by using the loan financing.

The remaining details about URL Harborside would use the Legal Entity axis. For example the Loan amount of $63.9.

**Tagging Examples**

So let's look at some real life examples that go beyond the simple basics

Parent Company Reporting

When a company reports the  financial statements of the parent company in a filing, the values reported represent the standalone financials of the parent company. To record these values in an XBRL filing the values could be tagged with the *LegalEntyityAxis* and the name of the parent company. The figure below shows an example disclosure of Parent Company's statement of Income.

When tagging the values for the holding company using the  *ConsolidatedEntitiesAxis* with the *ParentCompanyMember* requires that the *ConsolidationItemsAxis* is also used with the *ReportableLegalEntitiesMember* to ensure that the values reported in a consolidation schedule are tagged the same way for the same facts. In the disclosure below the values should be tagged using the *ConsolidatedEntitiesAxis* with the member *ParentCompanyMember*  and the *ConsolidationItemsAxis* with the member  *ReportableLegalEntitiesMember*.

![Example 2](images/leiconsolidations02.png?raw=true)

### Condensed Consolidated Statements

When reporting condensed consolidated statements, companies will break down consolidated numbers showing the Parent company, Guarantors and non guarantor Subsidiaries. (See figure  below) In these cases the entities values are reported pre consolidation and should therefore use the *ConsolidatedEntitiesAxis* as defined in option 2 above.
![Example 3](images/leiconsolidations03.png?raw=true)

The *ConsolidatedEntitiesAxis* with the reportable entities member allows grouping of legal entities to be defined as single members such as subsidiaries and guarantors. The consolidated values should be the default value for the line item.

In this case, the pre-consolidation entities are tagged with the *ConsolidatedEntitiesAxis* and respective members *ParentCompanyMember*, *GuarantorSubsidiariesMember*, and *NonGuarantorSubsidiariesMember*. It is important to note that the *ParentCompanyMember* should be used for the parent and not the legal Entity Name of the company as this would represent the consolidated values of the entity. When reporting numbers for the Parent company the *ParentCompanyMember* should always be used. 

The following example shows Verso Corporation which is the ultimate parent. This parent company also owns an entity called Verso Holdings which is referred to also as Verso Paper Holdings. In the following disclosure the company shows the condensed Consolidated balance sheet for Verso Paper Holdings and the balance sheet for Verso and Verso Paper Holdings. 

The following figure shows the balance sheets for both Verso and Verso Holdings. Verso is the registrant reporting entity and does not need to use the Legal Entity Axis. All the numbers reported for Verso Holdings need to use the *LegalEntityAxis* and a member for Verso Paper Holdings (*VersoPaperHoldingsMember)* to distinguish the second column of values. 

![Example 4](images/leiconsolidations04.png?raw=true)

Note that this data is the consolidated data for Verso Paper Holdings and as such only needs the legal entity dimension. The figure below shows a further breakdown of Verso Paper Holdings. The value of 900,941 for total Assets on the figure above is the same value representing the aggregate assets in the figure below. \

The consolidating schedule below represents the values for the consolidated entity of Verso Holdings LLC. All of the values in the disclosure will use the *LegalEntityAxis* and the member *VersoPaperHoldingsMember*.  This disclosure shows values for the Parent Company but the parent company member cannot be on the legal Entity axis especially in this case as it is already in use even though this is just a partial disaggregation.

![Example 5](images/leiconsolidations05.png?raw=true)

To tag these balance sheet elements the *ConsolidatedEntitiesAxis* should be used with the *ParentCompanyMember* because it is a consolidating schedule which includes all the components of the aggregation. Just using this axis by itself represents the value post consolidation. To represent the elements pre-consolidation, the *ConsolidationItemsAxis* and *ReportableLegalEntitiesMember* should be added to the values. This is the use of option 2 discussed earlier in the document. The *ParentCompanyMember* cannot use the *LegalEntityAxis*.

The value of the assets of the Parent of Verso Paper Holdings in the filing of Verso Corporation would use the following line items and dimensions to tag the value of the 1,396,872.

|**Line Item**|**Dimension 1**|**Dimension 2**|**Dimension 3**|
|--------|--------|--------|--------|
|Assets    |*ConsolidatedEntitiesAxis = ParentCompanyMember*|*ConsolidationItemsAxis = ReportableLegalEntitiesMember*|*LegalEntityAxis = VersoPaperHoldingsMember*|

 \
In addition all the other members representing groups of companies would also appear on the *ConsolidatedEntitiesAxis* with the dimension for *ConsolidationItemsAxis=ReportableLegalEntitiesMember* and the*LegalEntityAxis=VersoPaperHoldingsMember*.

### Co Registrants

It is expected that co-registrants common in the utility industry will use the legal entity axis to identify each legal entity.

### Summary of when to use an axis

|**Axis**|**Constraints**|
|--------|--------|
|Legal Entity Axis   |Use to report detailed data about an entity that is not the consolidated reporting entity. Any member on this axis must be a named specific legal entity   |
|Consolidation Items Axis   |Use to disaggregate consolidated totals between values before eliminations and after eliminations   |
|Consolidated Entities Axis   |Use this axis to represent the values in a consolidating schedule. Non consolidated entities cannot be included on this axis.  |
|Entity Ownership Axis   |Used to represent the hierarchical tree ownership of the company and to report values that exist between the reporting entity and the entity actually owned. If the holding company does not own the company or plan to hold the company then it should not be used with this axis. This axis does not have to aggregate to a valid total. This axis should only be used to report data that represents a relationship between the reporting entity and the owned company. It should not be used to report information about the owned company such as revenues. Revenues would use either the legal entity axis or Consolidated Entities axis. This axis is used to report data like ownership percentage, date holding acquired, date holding sold, change in ownership percentage etc.