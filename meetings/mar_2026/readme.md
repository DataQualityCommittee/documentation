# Data Quality Committee Meeting - March 18, 2026

### Introductions

### Approval of Minutes
  + [October 15, 2025 Meeting Minutes](https://github.com/DataQualityCommittee/documentation/raw/master/meetings/mar_2026/DRAFTDQCMeetingNotes251015.docx?raw=true)

### Approval of Version 29 DQC Rules
**[Overview of Changes (Word doc)](https://github.com/DataQualityCommittee/documentation/raw/master/meetings/mar_2026/v29changes.docx?raw=true)** - rules dqc_0209, dqc_0218 and dqc_0229 were not approved by the DQC.

  - **[DQC_0208 - Subtotals match Extensible Enumerations in the Schedule of Investments](https://github.com/DataQualityCommittee/DQC_us_rules/blob/v29/docs/DQC_US_0208/DQC_0208.md)** - This rule validates that the values reported for InvestmentTypeExtensibleEnumeration and InvestmentIndustrySectorExtensibleEnumeration are consistent with the domain members defined for InvestmentTypeAxis and EquitySecuritiesByIndustryAxis. 

  - **[DQC_0224 - Management Defined Performance Measure Reconciliation Accuracy (IFRS)](https://github.com/dataqualitycommittee/dqc_us_rules/blob/v29/docs/DQC_IFRS_0224/DQC_0224.md)**]** - The rule validates that the sum of the IFRS base measure and all reconciling adjustments equals the reported management-defined performance measure value. This ensures that reconciliation tables are mathematically consistent and that users can rely on the accuracy of the reconciliation from IFRS measures to management-defined performance measures. 
 
  - **[DQC_0225 - Prohibited Recognition and Derecognition Items on Income Statement](https://github.com/dataqualitycommittee/dqc_us_rules/blob/v29/docs/DQC_US_0225/DQC_0225.md)** – The rule identifies presentation roles related to income statements and flags any concepts from predefined lists of recognition and derecognition items that should not appear in these statements. These items are more appropriately reported in reconciliation schedules or balance sheet presentations rather than as income statement line items.

  - **[DQC_0226 - US GAAP Elements Used in Employee Benefit Plan Filings](https://github.com/dataqualitycommittee/dqc_us_rules/blob/v29/docs/DQC_US_0226/DQC_0226.md)** –  EBP filings (forms 11-K, 11-K/A, and 11-KT) should use the specialized Employee Benefit Plan taxonomy elements rather than standard US GAAP elements. This rule identifies when US GAAP elements are used in EBP filings and flags them as errors, promoting the proper use of the appropriate taxonomy for employee benefit plan reporting.

  - **[DQC_0227 - Calculated Ratio Consistency Checks](https://github.com/dataqualitycommittee/dqc_us_rules/blob/v29/docs/DQC_US_0227/DQC_0227.md)** – The rule validates that the reported calculated fact lies within the numeric interval implied by dividing the numerator by the denominator, taking into account, decimals, and tolerance for rounding.

  - **[DQC_0228 - 'Other' Concept Should Not Exceed Aggregate](https://github.com/dataqualitycommittee/dqc_us_rules/blob/v29/docs/DQC_US_0228/DQC_0228.md)** -  In well-formed calculation networks, an "other" member (a partial grouping) should not exceed the value of the total aggregation concept. This rule detects cases where an "other" item's value is greater than the related parent aggregate and flags them for review.

  - **[DQC_0230 - Disallowed 'Other' Concepts in Calculation Networks](https://github.com/dataqualitycommittee/dqc_us_rules/blob/v29/docs/DQC_US_0230/DQC_0230.md)** – Some taxonomies define an "other" concept that aggregates items not explicitly listed as children of the total; this rule checks that only the expected "other" concepts are used in each calculation network.

  - **[DQC_0231 - Aggregate and 'Other' Concepts Appearing as Siblings in Calculation Networks](https://github.com/dataqualitycommittee/dqc_us_rules/blob/v29/docs/DQC_US_0231/DQC_0231.md)** – This rule detects cases where an aggregate concept and its designated "other" concept appear together as siblings in the same calculation (summation) network.

### Introduction of Version 30 DQC Rules
**[DQC Version 30 - Proposed New Rules (Word doc)](https://github.com/DataQualityCommittee/documentation/raw/master/meetings/mar_2026/v30proposed.docx?raw=true)**

### _Break_

### Executive Session
  - SEC Agenda Topics

### Wrap Up/Future Meetings
  - DQC meeting June 25 (virtual)
  - DQC and joint SEC meetings October 7 (Washington, DC)
______________________
