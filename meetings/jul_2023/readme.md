# Data Quality Committee Meeting - July 6, 2023

### Approval of Minutes
  + [March 21, 2023 Meeting Minutes](DRAFTDQCMeetingNotes230321.docx?raw=true)

### Review and Approval of Version 21 DQC Rules 

- **[DQC_0148 – OCI Items in Income, Income in OCI](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v21/docs/DQC_US_0148/DQC_0148.md)** - This rule identifies if OCI items have been included in the calculation of net income. The rule is being updated in version 21 to also identify if net income items are included in OCI.
- **[DQC_0149 – Use of Noncurent Assets](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v21/docs/DQC_US_0149/DQC_0149.md)** - This rule is intended to ensure that filers use the NoncurrentAssets element appropriately. The element should be used for long-lived assets reported as part of the geographical segment (not a component of the balance sheet).  The rule checks that the element is included in the ScheduleOfRevenuesFromExternalCustomersAndLongLivedAssetsTable.
- **[DQC_0150 – Segment Reporting Inconsistencies](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v21/docs/DQC_US_0150/DQC_0150.md)** - This rule checks for inconsistencies in segment reporting disclosure by identifying where filers have used inappropriate members or have excluded members on the consolidation items or segment axes. There are four components to this rule:
  1. Members of the consolidation items axis aggregate correctly
  1. Members of the statement business segments axis aggregate correctly
  1. Business segment has been used with a line item without the operating segment member 
  1. Number of segments are less than the number of segment members on the segment axis

- **[DQC_0153 – Financial Statement Table Placement](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v21/docs/DQC_US_0153/DQC_0153.md)** - This rule identifies monetary items not included as primary items of the financial statement disclosure tables.
- **[DQC_0154 – Tax Reconciliation Items](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v21/docs/DQC_US_0154/DQC_0154.md)** - This rule checks the tax reconciliation disclosure and flags whether the following elements have been used correctly:
  * Foreign-derived intangible income
  * Global intangible low-taxed income
  * Base erosion and anti abuse tax
  * Foreign Income Tax Rate Differentials
- **[DQC_0155 – Exchange Rate Effect Inconsistency](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v21/docs/DQC_US_0155/DQC_0155.md)** - This rule checks that the exchange rate impact on the cash flow statement is calculated correctly. The rule flags when the element CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsPeriodIncreaseDecreaseIncludingExchangeRateEffect excludes an effect of exchange rate element in its calculation.
- **[DQC_0156 – Basic and Diluted Extension Elements](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v21/docs/DQC_US_0156/DQC_0156.md)** - This rule identifies when filers create extensions to report basic and diluted amounts as a single element.  Basic and diluted amounts are required to be tagged separately.
- **[DQC_0157 – Bank Measures Less than One Percent Elements](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v21/docs/DQC_US_0157/DQC_0157.md)** - This rule identifies when filers have reported values for capital adequacy ratios defined in the US GAAP taxonomy that are less than 1 percent.
- **[DQC_0158 – Related and Nonrelated Party Axis and Extensible Enumerations Elements](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v21/docs/DQC_US_0158/DQC_0158.md)** - This rule identifies when filers have defined facts using the RelatedAndNonrelatedPartyStatusAxis and the extensible enumerations associated with this axis.  This axis will be deprecated in the 2024 taxonomy.

### Review and Approval of Version 22 DQC Rules for Public Review [Word files in .zip](v22RuleForms.zip) 

### Wrap Up/Future Meetings
  - **REVISED DATE** October 5, 2023, 10:00 am ET (w/SEC Staff 1-3pm) __IN PERSON, Washington D.C.__
______________________
