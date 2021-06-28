# Data Quality Committee Meeting - June 29, 2021

### Introductions 
  
### Approval of Minutes
  + [March 24, 2021 Meeting Minutes](DRAFTDQCMeetingNotes03242021.docx?raw=true)

### Chair Rotation

### Review and Approval of Version 15 DQC Rules
[Version 15 Rules Summary (.docx)](v15-approval.docx?raw=true) 
  + [DQC_0107 – General Text Block](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v15/docs/DQC_US_0107/DQC_0107.md)
  + [DQC_0108 – Fact Value Consistency Over Time](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v15/docs/DQC_US_0108/DQC_0108.md)
  + [DQC_0109 – Concentration Risk](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v15/docs/DQC_US_0109/DQC_0109.md)
  + [DQC_0110 – Missing Business Acquisition Axis (Short Period)](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v15/docs/DQC_US_0110/DQC_0110.md)
  + [DQC_0112 – Line Items Requiring the Business Acquisition Axis](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v15/docs/DQC_US_0112/DQC_0112.md)
  + [DQC_0113 – Gross Acquisition Less Than Net Acquisition](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v15/docs/DQC_US_0113/DQC_0113.md)
  + [DQC_0114 – Assets Acquired Net of Goodwill](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v15/docs/DQC_US_0114/DQC_0114.md)
  + [DQC_0115 – Fact Value Consistency Over Time](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v15/docs/DQC_US_0115/DQC_0115.md)
  + [DQC_0116 – Line Items Requiring the Asset Acquisition Axis](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v15/docs/DQC_US_0116/DQC_0116.md)

### Review and Approval of Version 16 DQC Rules For Public Review 
#### Summary of Rules ([.zip of rule submission forms](v16-public-review.zip) proposed for public review)
_Rules were run over a sample of 2,000 filings to detect errors._

**DQC_0117 - Financial Statement Tables Dimensional Cross Check _(714 errors)_** This rule identifies inconsistent calculations defined for the Financial Statements.  The rule covers the Cash Flow Statement, Statement of Financial Position and the Income Statement and excludes the Statement of Changes in Shareholders Equity.  The rule evaluates if the dimensional values reported in the financial statements are equal to the reported sum of these dimensional values. Both the dimensional values and the aggregate value need to be reported in the financial statement.  The rule checks a limited amount of axes. The axis aggregations checked by the rule are as follows:

*   StatementClassOfStockAxis
*   ProductOrServiceAxis'
*   PropertyPlantAndEquipmentByTypeAxis
*   LongtermDebtTypeAxis
*   RelatedPartyTransactionsByRelatedPartyAxis
*   StatementBusinessSegmentsAxis
*   FinancialInstrumentAxis
*   LimitedPartnersCapitalAccountByClassAxis
*   PartnerTypeOfPartnersCapitalAccountAxis
*   FiniteLivedIntangibleAssetsByMajorClassAxis
*   InformationByCategoryOfDebtSecurityAxis

**DQC_0118 - Financial Statement Tables Calculation Check of Required Context _(371 errors)_** This rule identifies inconsistent calculations defined for the Financial Statements.  The rule covers the Cash Flow Statement, Statement of Financial Position, the Income Statement and excludes the Statement of Changes in Shareholders Equity.  The rule evaluates each line in the financial statements representing an aggregation based on the elements defined in the calculation linkbase.  If the sum of the child elements does not equal the value reported for the aggregation then an error is reported.  The rule will only run for the period representing the required context.

**DQC_0119 - Income Before Tax Equity Method _(707 errors)_** This rule is intended to identify those cases where the company uses the element IncomeLossFromContinuingOperationsBeforeIncomeTaxesMinorityInterestAndIncomeLossFromEquityMethodInvestments in an inappropriate manner.  The rule has 2 parts:

1.  If the filer has used the element representing “Income before income tax, Non Controlling Interest and Equity Method Investments”, then the filer must also have disclosed Equity Method Investments.  To check if the company has reported equity method investments the rule checks if the filer has reported values for any of the following elements: (With dimensions and without dimensions)
        a. IncomeLossFromEquityMethodInvestments, 
        b. IncomeLossFromEquityMethodInvestmentsNetOfDividendsOrDistributions, 
        c. IncomeLossFromAffordableHousingProjectsEquityMethodInvestments
2. The rule identifies descendant calculation elements of the “Income before income tax, Non Controlling Interest and Equity Method Investments”. The rule determines if any of the components of the element include Equity Method investments using the element IncomeLossFromEquityMethodInvestments or IncomeLossFromEquityMethodInvestmentsNetOfDividendsOrDistributions.

**DQC_0120 - Incorrect Line Item Reference _(66 errors)_** This rule is intended to identify those cases where the company uses an extensible list item that refers to a balance sheet line item that does not exist on the balance sheet.  The rule checks that the values provided for the following extensible list items are legitimate balance sheet line items that appear in the calculation linkbase of the balance sheet:

*   FinanceLeaseLiabilityCurrentStatementOfFinancialPositionExtensibleList
*   FinanceLeaseLiabilityNoncurrentStatementOfFinancialPositionExtensibleList
*   FinanceLeaseRightOfUseAssetStatementOfFinancialPositionExtensibleList 
*   OperatingLeaseLiabilityNoncurrentStatementOfFinancialPositionExtensibleList
*   OperatingLeaseLiabilityCurrentStatementOfFinancialPositionExtensibleList 
*   OperatingLeaseRightOfUseAssetStatementOfFinancialPositionExtensibleList

**DQC_0121 - Incorrect Transition Elements Used** This rule is intended to identify those cases where the company reports line items that have been transitioned because of changes in accounting standards. The rule identifies those elements that should no longer be used by the filer.  The taxonomy includes updated elements that reflect the new accounting standards and they should be used. In many cases the filer is unaware that an element has been transitioned and continues to use it until such time as it is deprecated and can no longer be used.  This rule helps identify these elements so that filers can replace the transition elements with elements that reflect current US-GAAP. The rule has 2 parts:

1.  _(4589 errors)_ Use of the following transition elements will trigger an error.  These are identified as descendants of the following abstract concepts in the US-GAAP 2020 and 2021 taxonomies:
    *   Asu201601TransitionAbstract
    *   Asu201618TransitionAbstract
1. _(2,636 errors)_ Use of the following transition elements (used by companies other than emerging growth companies) will trigger an error.  These are identified as descendants of the following abstract concepts in the US-GAAP 2020 and 2021 taxonomies:
    *   ASU201602TransitionAbstract
    *   Asu201712TransitionAbstract
    *   ASU201807TransitionAbstract

The following elements are excluded from the rule:

*   LongTermDebtAndCapitalLeaseObligationsMaturitiesRepaymentsOfPrincipalRemainderOfFiscalYear
*   LongTermDebtAndCapitalLeaseObligationsRepaymentsOfPrincipalInNextTwelveMonths
*   LongTermDebtAndCapitalLeaseObligationsMaturitiesRepaymentsOfPrincipalInYearTwo
*   LongTermDebtAndCapitalLeaseObligationsMaturitiesRepaymentsOfPrincipalInYearThree
*   LongTermDebtAndCapitalLeaseObligationsMaturitiesRepaymentsOfPrincipalInYearsTwoAndThree
*   LongTermDebtAndCapitalLeaseObligationsMaturitiesRepaymentsOfPrincipalInYearFour
*   LongTermDebtAndCapitalLeaseObligationsMaturitiesRepaymentsOfPrincipalInYearFive
*   LongtermDebtAndCapitalLeaseObligationsMaturitiesRepaymentsOfPrincipalInYearsFourAndFive
*   LongTermDebtAndCapitalLeaseObligationsMaturitiesRepaymentsOfPrincipalAfterYearFive

**DQC_0122 - Components of Equity on the Balance Sheet _(9 errors)_** This rule is intended to identify those cases where the company reports the components of equity or partners capital on the balance sheet. If one of these two dimensions are included as part of the balance sheet then the rule will return an error identifying the number of facts using the axis reported in the balance sheet.

*   StatementEquityComponentsAxis
*   PartnerCapitalComponentsAxis

**DQC_0123 - Missing Components of Equity Axis _(2,157 errors)_** The rule identifies where a company has reported classes of stock but has not indicated if they are common or preferred or treasury components of equity. The rule identifies facts reported using one of the following line items using the class of stock axis without any other dimensions:

*   StockholdersEquityIncludingPortionAttributableToNoncontrollingInterest or 
*   StockholdersEquity

**DQC_0124 - Breakdown of Lease Liabilities & Assets Across Financial Statement Lines Items _(77 errors)_** The rule flags an error when lease liabilities and assets are present but have not been included in the presentation linkbase of the financial statements. The intent of the rule is to allow filers to check that their filing is consistent with the FASB’s XBRL implementation guide and US-GAAP.  If the extensible list item or Balance Sheet Location Axis is not used then the rule will report an error.  The rule applies to the following items used to record lease liabilities and assets on the balance sheet:

*   FinanceLeaseLiability
*   FinanceLeaseLiabilityCurrent
*   FinanceLeaseLiabilityNoncurrent
*   FinanceLeaseRightOfUseAsset
*   OperatingLeaseRightOfUseAsset

The associated extensible list items required for each of these elements is as follows:

*   FinanceLeaseLiabilityStatementOfFinancialPositionExtensibleList
*   FinanceLeaseLiabilityCurrentStatementOfFinancialPositionExtensibleList
*   FinanceLeaseLiabilityNoncurrentStatementOfFinancialPositionExtensibleList
*   FinanceLeaseRightOfUseAssetStatementOfFinancialPositionExtensibleList
*   OperatingLeaseRightOfUseAssetStatementOfFinancialPositionExtensibleList

### Wrap Up/Future Meetings
  + September 29, 2021 (9AM EDT); with SEC Staff (1PM EDT)
______________________
