## XBRL US Center for Data Quality Committee Guidance
# Guidance on Tagging Axis and Members Using the IFRS Taxonomy
### Approved January 20, 2021
### Updated February 9, 2021

The XBRL US Data Quality Committee (DQC) has developed prescriptive guidance for issuers submitting XBRL files that contain financial statements to the Securities Exchange Commission (SEC).  This guidance provides for uniform, consistent tagging of financial data using the IFRS taxonomy to improve the usability of such data.  The DQC has also developed rules that test XBRL files for conformity with the guidance.  The guidance in this document provides links and references, where applicable, to the associated rules developed by the DQC.  It is expected that issuers will comply with the guidance presented in this document when tagging their IFRS financial statements for submission to the SEC.  

## Appropriate Modeling of Axis and Members
Certain axes in the IFRS taxonomy should only have certain members, otherwise consumption of the data is adversely impacted because the resulting axis and member combinations are nonsensical.  The following guidance provides limitations on the use of certain axis and member combinations that should be adhered to when tagging financial information using the IFRS Taxonomy.   

### Default Member of Axes
The default member of an Axis should not be changed from that defined in the IFRS taxonomy. Users of XBRL data expect that the default member of an axis will be the same across filings.  For example, if a company reports a value of Revenues with no explicit members for any axes it is assumed that this represents revenues of the consolidated entity. This is because for Consolidated and separate financial statements axis the default member is Consolidated. However, if the company changed the default member of this axis to the Separate member then reporting revenues without an explicit member for this axis would represent that of the parent company, not the consolidated entity.  ([DQC_0041.73](https://xbrl.us/dqc_0041/)).


### Assets and liabilities classified as held for sale [axis]  
(_AssetsAndLiabilitiesClassifiedAsHeldForSaleAxis_)   
This axis is used to categorize assets and liabilities in the face of financial statements as held for sale. Because an entity must present a non-current asset classified as held for sale and the assets of a disposal group classified as held for sale separately from other assets in the statement of financial position, this axis is used to make that dis-aggregation. The liabilities of a disposal group classified as held for sale shall be presented separately from other liabilities in the statement of financial position. Those assets and liabilities shall not be offset and presented as a single amount. The major classes of assets and liabilities classified as held for sale shall be separately disclosed either in the statement of financial position or in the notes. This axis is used to identify those specific line items in these categories. Filers should not generally create extension elements under this axis unless they are further sub categorizing the disposal group.  The rule for this axis checks that the axis does not use extension members, but allows extension members to be defined if they are children of AssetsAndLiabilitiesClassifiedAsHeldForSaleMember, NoncurrentAssetsHeldForSaleMember or DisposalGroupsClassifiedAsHeldForSaleMember [(DQC_0104.9551)](https://xbrl.us/dqc_104/).

When a company reports a value for Assets, NonCurrent Assets and Current Assets, it is assumed that these values are always inclusive of held for sale assets [(DQC_0102.9540)](https://xbrl.us/dqc_102/).

### Continuing and discontinued operations [axis] 
(_ContinuingAndDiscontinuedOperationsAxis_)  
This axis is used to indicate that a line item is continuing, discontinued or both. The default represents those components of the entity that are not discontinued operations. For amounts that represent discontinued operations the DiscontinuedOperationsMember is used.  For those amounts that represent the sum of both continuing and discontinued the AggregateContinuingAndDiscontinuedOperationsMember is used. Generally this axis should not include any extension members. However in some cases extensions do arise when discontinued operations are disaggregated into distinct categories. If these members are created they should be reported as a child of the members DiscontinuedOperationsMember or DisposalGroupsClassifiedAsHeldForSaleMember.  Otherwise do not create extension members on this axis. The rule [DQC_0104.9552](https://xbrl.us/dqc_104/) checks if extensions have been used with this axis. 

### Consolidated and separate financial statements [axis]  
(_ConsolidatedAndSeparateFinancialStatementsAxis_)
This axis is used to report the stand alone financials of the parent company.  This axis only allows the SeparateMember to be used. The default represents the consolidated financial statements of a group (in which the assets, liabilities, equity, income, expenses and cash flows of the parent and its subsidiaries are presented as those of a single economic entity). This axis only allows the SeparateMember to be used. If any other member is used, either as an extension or a base IFRS member, then an error will be reported. [(DQC_0104.9553)](https://xbrl.us/dqc_104/)

 Filers should use the axis ConsolidatedEntitiesAxis in the srt taxonomy to report the financial information associated with a subsidiary entity. This can be used in combination with the ConsolidationItemsAxis when the amounts are reported gross, and or elimination values are reported.

### Segment consolidation items [axis]  
(_SegmentConsolidationItemsAxis_)
This axis is used to define the breakdown of the consolidated balance between those segments that are operating segments and those items that are not, such as intercompany and other reconciling amounts that add back to the consolidated total. The following members are permitted to be used on this axis:

*   OperatingSegmentsMember, 
*   MaterialReconcilingItemsMember,
*   EliminationOfIntersegmentAmountsMember,
*   UnallocatedAmountsMember

Extension members can be used as long as they are defined as children of the following members and are a further specification of these members:

*   MaterialReconcilingItemsMember,
*   EliminationOfIntersegmentAmountsMember,
*   UnallocatedAmountsMember 

The following extension members can also be used as long as they are descendants of the OperatingSegmentsMember:

*   ReportableSubsegmentsMember
*   IntersubsegmentEliminationsMember

In addition, the rule allows the filers to define the following common extension members that capture other totals that are commonly reported:

*   CorporateReconcilingItemsAndEliminationsMember,
*   CorporateAndReconcilingItemsMember,
*   CorporateAndEliminationsMember, 
*   EliminationsAndReconcilingItemsMember,
*   OperatingSegmentsAndCorporateNonSegmentMember,
*   OperatingSegmentsExcludingIntersegmentEliminationMember,
*   CorporateNonSegmentMember,
*   GeographyEliminationsMember, and
*   OtherNonSegmentMember.

The rule DQC_0104.9554 checks if inappropriate extensions have been used with this axis. 

|Element Label|Element Name|Documentation|  
|--------|--------|--------|  
|Eliminations, Corporate and Reconciling items|CorporateReconcilingItemsAndEliminationsMember|Represents the aggregate total of adjustments for non operating corporate items, reconciling items and eliminations.|  
|Corporate and Reconciling Items|CorporateAndReconcilingItemsMember|Represents the aggregate total of non operating corporate items and reconciling items|  
|Corporate and Eliminations|CorporateAndEliminationsMember|Represents the aggregate total of non operating corporate items and elimination items|  
|Eliminations and Reconciling Items|EliminationsAndReconcilingItemsMember|Represents the aggregate total of reconciling items and  elimination items|  
|Operating Segments and Corporate Non-segment|OperatingSegmentsAndCorporateNonSegmentMember|Represents the aggregate total of operating segments and non operating corporate items.|  
|Operating Segments Excluding Intersegment Elimination|OperatingSegmentsExcludingIntersegmentEliminationMember|Represents the aggregate total of operating segments.|  
|Operating Segments and Unallocated Member|OperatingSegmentsAndUnallocatedMember|The total of operating segments and unallocated items, before elimination|  
|Corporate Non-segment|CorporateNonSegmentMember|Represents the aggregate total of non operating corporate items|  
|Geography Eliminations|GeographyEliminationsMember|Represents the aggregate total of geographical elimination items|  
|Other Non-segment|OtherNonSegmentMember|Represents the aggregate total of non operating other items|   
|Operating Segments And Unallocated|OperatingSegmentsAndUnallocatedMember|Represents the aggregate total of operating segments and unallocated items|

### Segment [Axis]
(_SegmentAxis_) 
This axis is used to define the specific segments of the filer. This axis will generally always use members that are extensions and should not use members defined in the IFRS taxonomy.  Unlike filings made under US-GAAP, the filer can use the country members defined in the country taxonomy and the regions defined in the srt taxonomy.

The rule [DQC_0104.9555](https://xbrl.us/dqc_104/) checks if inappropriate base members have been used with this axis.
