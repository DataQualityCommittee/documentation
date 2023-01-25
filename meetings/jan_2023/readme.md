# Data Quality Committee Meeting - January 25, 2023

### Introductions
  + New Committee Member Brian Bracey (CIGNA)
  
### Approval of Minutes
  + [September 21, 2022 Meeting Minutes](DRAFTDQCMeetingNotes220921.docx?raw=true)

### Review and Approval of Version 20 DQC Rules

- **[DQC_0142 - Typed Dimension Axis Restriction Restriction](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v20.0.0RC6/docs/DQC_US_0142/DQC_0142.md)** - This rule checks that the new typed dimensions to support Business Development Corporation (BDC) filings are defined correctly. The rule checks that each fact is associated with 1 typed dimension. Each fact should using a typed investment dimension, cannot use another explicit dimension.  The only exception to the rule is the use of the explicit axis InvestmentCompanyNonconsolidatedSubsidiaryAxis, which was added as part of the BDC taxonomy upgrade.
- **[DQC_0143 – Derivative Position Extensible Enumeration](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v20.0.0RC6/docs/DQC_US_0143/DQC_0143.md)** - This rule checks that the extensible enumeration element DerivativePositionExtensibleEnumeration can only use two values.  The two allows values are:
  - CallOptionMember 
  - PutOptionMember
- **[DQC_0144 – No Balance Attribute in Financial Statements](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v20.0.0RC6/docs/DQC_US_0144/DQC_0144.md)** - This rule checks that extension monetary elements included in the balance sheet, income statement, cash flow statements  and shareholders equity statements include a balance attribute.  This is important so that data users have some idea what type of element the extension element is.  If it is in the balance sheet then a credit is a liability or equity and if it is a debit then it is clear it is some kind of asset, thus allowing reasonable classification.
- **[DQC_0145 – Inappropriate Cash Flow Presentation Presentation](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v20.0.0RC6/docs/DQC_US_0145/DQC_0145.md)** - This rule looks at the presentation linkbase of the cash flow statement and income statement to determine that elements have been presented correctly.  The rule has three parts.
  - *Part 1*
  The first part of the rule determines the presentation children of the abstract concept representing financing items of  NetCashProvidedByUsedInFinancingActivitiesAbstract. These concepts are then compared to the concepts not in the financing section of the us-gaap taxonomy defined by the FASB.  If there is an intersection then these concepts are output as errors.  This misclassification is a problem when trying to determine the financing items from the presentation linkbase.
  - *Part 2*
  The second part of the rule determines the presentation children of the abstract concept representing investing items of  NetCashProvidedByUsedInInvestingActivitiesAbstract. These concepts are then compared to the concepts not in the investing section of the us-gaap taxonomy defined by the FASB.  If there is an intersection then these concepts are output as errors.  This misclassification is a problem when trying to determine the financing items from the presentation linkbase.
  - *Part 3*
  The third part of the rule identifies those elements defined as presentation descendants of IncreaseDecreaseInOperatingCapitalAbstract in the US-GAAP taxonomy defined by FASB.  It then determines if any of these concepts are used in the income statement.  In a number of instances filers are taking these elements and using them in the income statement incorrectly.
- **[DQC_0146 – Incorrect Period Reported](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v20.0.0RC6/docs/DQC_US_0146/DQC_0146.md)** - This rule identifies incorrect period durations used in the income statement of the 10-K. The rule identifies where a company has reported a 10K but the majority of the values reported on the Income Statement are for a period other than a year. Although uncommon, this rule is provided to allow filers to detect if this situation has occurred.
- **[DQC_0147 - Incorrect Sign of Elimination](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v20.0.0RC6/docs/DQC_US_0147/DQC_0147.md)** - This rule identifies when a filer enters a positive value for an element using the elimination member (on the consolidated items access) when it should be negative.  The rule uses the same logic as used for the non negative rule (DQC_0015).
- **[Rule DQC_0148 – OCI Items in Income](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v20.0.0RC6/docs/DQC_US_0148/DQC_0148.md)** - This rule identifies if OCI items have been included in the calculation of net income.
#### Changes to v20 rules
**Public review**
- **[DQC_0145 – Inappropriate Cash Flow Presentation](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v20.0.0RC6/docs/DQC_US_0145/DQC_0145.md)**
Updated rule to allow the following elements to be used in the investing section of the cash flow statement (Presentation):
  - PaymentsForProceedsFromOtherDeposits
  - IncreaseDecreaseOfRestrictedInvestments
  - ProceedsFromPaymentsForInSecuritiesSoldUnderAgreementsToRepurchase  
  
**Existing Rules**
- **[DQC_0043 Incorrect Weights in Operating Cash Flows](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v20.0.0RC6/docs/DQC_US_0043/DQC_0043.md)**  
This rule was expanded with an added suffix of .9875.  The rule also checks that the sign of discontinued operations on the cashflow statement is the same as the sign on the income statement. In many cases companies were flipping the sign between the statements and using IncomeLossFromDiscontinuedOperationsNetOfTaxAttributableToReportingEntity for one value and IncomeLossFromDiscontinuedOperationsNetOfTax for the other value.  The sign of these two elements should be the same if there is no noncontrolling interest.
This rule was expanded with an added suffix of .9873 that checks for a negative calculation between Net Income and Cash Flows from Operating Activities. Net Income should always make a positive contribution to cash from operations. In some cases companies were flipping the sign and the weight of Net Income.

- **[DQC_0049 Single Calculation Tree for Changes in Cash Flows](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v20.0.0RC6/docs/DQC_US_0049/DQC_0049.md)**  
Updated rule for the 2022 taxonomy to correctly identify root elements used inappropriately in the filers extension taxonomy. In 2022 the element CashAndCashEquivalentsPeriodIncreaseDecreaseExcludingExchangeRateEffect was deprecated. This deprecated element in the rule was updated with the element CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsPeriodIncreaseDecreaseExcludingExchangeRateEffect

- **[DQC_0118 Financial Statement Tables Calculation Check of Required Context](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v20.0.0RC6/docs/DQC_US_0118/DQC_0118.md)**  
Updated the rule so that it would not run if the company had used the axis PledgedStatusAxis. The values for this axis should not be added together to get a balance sheet total.

- **[DQC_0121 Incorrect Transition Elements Used](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v20.0.0RC6/docs/DQC_US_0121/DQC_0121.md)**  
Updated the rule not to run for an 8-K or a 6-K.

- **[DQC_0135 Extensible Enumeration for Financial Statement Captions](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v20.0.0RC6/docs/DQC_US_0135/DQC_0135.md)**  
Updated rule to not run when broken down using the following axis:
  - EnvironmentalRemediationSiteAxis
  - DerivativeInstrumentRiskAxis
  - DerivativeInstrumentsGainLossByHedgingRelationshipAxis

  Updated the message on the rule to indicate that the not disclosed flag can be used to clear an error. See update to the message below.
  
  __"If the filing does not disclose the financial statement captions where the amounts appear, an extension element {$NotDisclosedAsImmaterial} can be used. If this element is used, the rule will not produce an error."__
  
  The extension element must use the extensible enumeration value as a prefix.

- **[DQC_0141 Inconsistent Accrued Interest Elements](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v20.0.0RC6/docs/DQC_US_0141/DQC_0141.md)**  
Updated the rule to match accrued interest and excluding accrued interest to match by class.  This means one class can include interest and another class can exclude interest as long as they are consistent between the classes of:
  - AccountsRec
  - DebtSecuritiesHeldToMaturity
  - AvailableForSaleSecuritiesDebtSecurities
  - DirectFinancingLeaseNet
  - FinancingReceivable
  - NetInvestmentInLease
  - SalesTypeLeaseNet

### Introduction of Version 21 DQC Rules
  - Segment Reporting
  - NonCurrent Assets Element Check
  - Hypercube Check
  - FDII and GILTI Rules

### Wrap Up/Future Meetings
  - March 22, 2023, 9:00 am ET (w/SEC Staff 1-3pm)
  - June 14, 2023 (PROPOSED)
  - September 20, 2023, 9:00 am ET (w/SEC Staff 1-3pm) __IN PERSON, Washington D.C.__
______________________
