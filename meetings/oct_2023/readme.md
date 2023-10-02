# Data Quality Committee Meeting - October 5, 2023

### Approval of Minutes
  + [July 6, 2023 Meeting Minutes](https://github.com/DataQualityCommittee/documentation/raw/master/meetings/oct_2023/DRAFTDQCMeetingNotes230706.docx)

### Review and Approval of Version 22 DQC Rules 

- **[DQC_0088 – Operating Lease Cost and Expense](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v22/docs/DQC_US_0088/DQC_0088.md)** - This rule identifies filings where the filer has reported the operating lease expense and variable lease expense but not the operating lease cost. A second component of the rule checks that operating lease expense is not included in the calculation of LeaseCost. The intent of the rule is to allow filers to check that their filing is consistent with the FASB's XBRL implementation guide.
- **[DQC_0159 – Financial Statement Abstract Concepts](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v22/docs/DQC_US_0159/DQC_0159.md)** - This rule identifies when the filer has not used all three financial statement abstract concepts in a filing.
- **[DQC_0160 – Descendants of NonrelatedPartyMember](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v22/docs/DQC_US_0160/DQC_0160.md)** - This rule identifies when the filer has defined a member descendant of the element NonrelatedPartyMember and when the RelatedPartyMember is not included as a sibling to NonrelatedPartyMember.
- **[DQC_0161 – Single Member Disaggregation](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v22/docs/DQC_US_0161/DQC_0161.md)** - This rule identifies when the filer has used a single dimension member on one of the following axis:  
  - VariableRateAxis, 
  - RetirementPlanFundingStatusAxis, 
  - InvestmentTypeAxis, 
  - RetirementPlanTaxStatusAxis.  
The rule is intended to ensure that filers use the extensible enumeration element rather than creating dimensions
- **[DQC_0162 – Trading Symbol](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v22/docs/DQC_US_0162/DQC_0162.md)** - This rule identifies where the filer has used an invalid or inconsistent trading symbol.  The rule checks that the trading symbol does not include invalid characters, identifies if the symbol is not applicable, and the symbol is upper case.
- **[DQC_0163 – Segment Expenditure Addition To Long Lived Assets](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v22/docs/DQC_US_0163/DQC_0163.md)** - The rule is intended to ensure that filers use the element SegmentExpenditureAdditionToLongLivedAssets in the segment rather than the cash flow element or PPE additions element.  This rule identifies where the filer has used the elements PaymentsToAcquirePropertyPlantAndEquipment or PropertyPlantAndEquipmentAdditions in the segment tables ScheduleOfSegmentReportingInformationBySegmentTable, or ScheduleOfRevenuesFromExternalCustomersAndLongLivedAssetsTable and has not included the element SegmentExpenditureAdditionToLongLivedAssets in the table.
- **[DQC_0164 – Use of Location Axis](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v22/docs/DQC_US_0164/DQC_0164.md)** - The rule is intended to identify inappropriate use of the Location Axis in the taxonomy. The rule has 3 different checks on the following axes: 
  - BalanceSheetLocationAxis, 
  - IncomeStatementLocationAxis, 
  - OtherComprehensiveIncomeLocationAxis
The rule does not identify the following line items used with the BalanceSheetLocationAxis in order to prevent false positive results:
  - FairValueAssetsMeasuredOnRecurringBasisUnobservableInputReconciliationLineItems 
  - FairValueLiabilitiesMeasuredOnRecurringBasisUnobservableInputReconciliationLineItems
- **[DQC_0165 – Useful Life of Leasehold Improvements](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v22/docs/DQC_US_0165/DQC_0165.md)** - This rule supports FASB guidance for the reporting of the useful life of term leases. If the element PropertyPlantAndEquipmentUsefulLifeDescriptionOfTermExtensibleEnumeration is used with a value of UsefulLifeTermOfLeaseMember, then this implies that no value would be provided for the concept PropertyPlantAndEquipmentUsefulLife. If the useful life is the actual term of the lease then the extensible enumeration does not have to be provided. This rule identifies where the filer has used the extensible enumeration element PropertyPlantAndEquipmentUsefulLifeDescriptionOfTermExtensibleEnumeration with LeaseholdImprovementsMember on the PropertyPlantAndEquipmentByTypeAxis with a value of 'UsefulLifeTermOfLeaseMember'.
- **[DQC_0174 - Conditional NonNegs](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v22/docs/DQC_US_0174/DQC_0174.md)** - This rule identifies where filers have reported a negative value for the concept FinancingReceivableAllowanceForCreditLossesIndividuallyEvaluatedForImpairment1. This value however can be negative if the negative value does not exceed the values of FinancingReceivableAllowanceForCreditLossesCollectivelyEvaluatedForImpairment or FinancingReceivableAllowanceForCreditLossExcludingAccruedInterest.

### Review and Approval of Version 23 DQC Rules for Public Review [Word files in .zip](https://github.com/DataQualityCommittee/documentation/raw/master/meetings/oct_2023/v23RuleForms.zip) 
- **DQC_0166 – Facts without Hypercubes** - This rule identifies where the filer has created facts with dimensions that do not fit into a hypercube defined in the extension taxonomy.
- **DQC_0167 – Inconsistent Calculation Roots** - The rule is intended to detect those filings where filers have not defined the calculation linkbase correctly for the Balance Sheet, Income Statement and Statement of Comprehensive Income.
- **DQC_0168 – Tax Reconciliation Calculation** - This rule identifies where the filer has not reported a calculation linkbase for the monetary and rate based tax reconciliation in a 10-K or 20-F filing.
- **DQC_0169 – Calculation in the Parenthetical Disclosure** - This rule identifies where the filer has defined a calculation in the parenthetical disclosure network of a Statement.
- **DQC_0170 – ECD Rule 10b51 Flag Disclosures** - This rule identifies where the filer has not reported the ECD Rule 10b51 Flag Disclosures that should be reported with a value of false if they had no such disclosures to make. The rule identifies if this flag is not reported in 10-K and 20-F filings with a document period end date after 2023-12-31. The rule checks if the following 4 flags defined in the ECD taxonomy are missing:
  - Rule10b51ArrAdoptedFlag,
  - NonRule10b51ArrAdoptedFlag,
  - Rule10b51ArrTrmntdFlag,
  - NonRule10b51ArrTrmntdFlag  
The SEC ECD taxonomy requires that these 4 flags are tagged even if the values are false.
- **DQC_0171 – ASU 201613 Transition Elements** - This rule identifies where the filer has reported ASU 201613 Transition elements in the filing. The rule will flag fact values with an end date greater than 2023-09-30 using one of these elements.  Exceptions include:
  - FinancingReceivableAllowanceForCreditLossesIndividuallyEvaluatedForImpairment1,
  - FinancingReceivableAllowanceForCreditLossesCollectivelyEvaluatedForImpairment, 
  - ImpairedFinancingReceivableAverageRecordedInvestment,
  - ImpairedFinancingReceivableWithNoRelatedAllowanceAverageRecordedInvestment,
  - HeldToMaturitySecuritiesInUnrealizedLossPositionsQualitativeDisclosureNumberOfPositions
- **DQC_0172 – Reporting Right of use Assets** - The rule detects where filers have reported RightofuseAssets but not included it on the Statements and have used the element PropertyPlantAndEquipment instead of the correct element PropertyPlantAndEquipmentIncludingRightofuseAssets.
- **DQC_0173 – IFRS Transition Elements** - This rule identifies concepts in the IFRS taxonomy that are being transitioned and that should not be used in filings after 2023-01-01.
### Executive Session
  - Review Agenda for Meeting with SEC Staff
### Wrap Up/Future Meetings
______________________
