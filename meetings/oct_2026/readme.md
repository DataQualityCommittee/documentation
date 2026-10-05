# Data Quality Committee Meeting - October 7, 2026

### Introductions

### Approval of Minutes
  + **[August 5, 2026 Meeting Minutes](https://github.com/DataQualityCommittee/documentation/raw/master/meetings/oct_2026/DRAFTDQCMeetingNotes260805.docx?raw=true)**

### Approval of Version 31 DQC Rules ([summary of changes](updates-v31.docx?raw=true))

  - **[DQC_0245 - Consolidated Entities Axis in Statement Section](https://github.com/DataQualityCommittee/DQC_us_rules/blob/v31/docs/DQC_US_0245/DQC_0245.md)** - The purpose of the rule is to ensure that the ConsolidatedEntitiesAxis is not used in the statement section of a filing.  Filers should use LegalEntityAxies for identifying legal entities in the statement section. 

  - **[DQC_0246 - Investment Identifier Axis Key Validation](https://github.com/DataQualityCommittee/DQC_us_rules/blob/v31/docs/DQC_US_0246/DQC_0246.md)** - The purpose of the rule is to validate the use of key-value pairs within the InvestmentIdentifierAxis dimension on a Schedule of Investments.  The rule checks the  
 
  - **[DQC_0248 - 11-K Filing Cover Page Tagging with Legal Entity Axis](https://github.com/DataQualityCommittee/DQC_us_rules/blob/v31/docs/DQC_US_0248/DQC_0248.md)** – The purpose of the rule is to check 11K filings use members on the LegalEntityAxis to tag the DocumentType and AmendmentFlag on the cover page. 

  - **[DQC_0249 - Single Member Extensible Enumeration Axis Used Without Aggregate Value](https://github.com/DataQualityCommittee/DQC_us_rules/blob/v31/docs/DQC_US_0249/DQC_0249.md)** –  The rule checks that when a filer uses an extensible enumeration axis with only a single member to disaggregate a line item, the filer also reports the aggregate value for that line item without the axis.

  - **[DQC_0250 - Members Used Across Incompatible Dimension Classes](https://github.com/DataQualityCommittee/DQC_us_rules/blob/v31/docs/DQC_US_0250/DQC_0250.md)** – The rule checks  that members are not used across dimensions that belong to different semantic classes.

### Introduction of Version 32 DQC Rules ([summary of proposed](proposed-v32.docx?raw=true))
 - **[DQC_US_0251 - Lease Not Yet Commenced Reported as an Unrecorded Unconditional Purchase Obligation](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v32/docs/DQC_US_0251/DQC_0251.md)** –  the purpose of the rule is to ensure that the amount of a lease that has not yet commenced is reported using `UnrecordedUnconditionalPurchaseObligationBalanceSheetAmount` (and the related maturity elements) with the correct axis and member.
 - **[DQC_US_0252 - Identifier Axis Required on Schedule of Investments Tables](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v32/docs/DQC_US_0252/DQC_0252.md)** –  the purpose of this rule is to ensure that each table used to tag the Schedule of Investments (SOI) of Business Development Companies (BDCs) and other investment companies includes the identifier axis defined for that table in the US GAAP taxonomy.
 - **[DQC_US_0253 - Unnecessary Custom Elements in Schedule III Real Estate and Accumulated Depreciation](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v32/docs/DQC_US_0253/DQC_0253.md)** –  the purpose of this rule is to ensure that property level information in Schedule III Real Estate and Accumulated Depreciation (SEC Regulation S-X 12-28) is tagged using the appropriate axes.
 - **[DQC_US_0254 - Inappropriate Axes Used in Schedule III Real Estate and Accumulated Depreciation](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v32/docs/DQC_US_0254/DQC_0254.md)** –  the purpose of this rule is to identify unnecessary custom (extension) elements and axes used to tag Schedule III Real Estate and Accumulated Depreciation (SEC Regulation S-X 12-28).
 - **[DQC_US_0255 - Common Roll Forwards Do Not Calculate](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v32/docs/DQC_US_0255/DQC_0255.md)** –  the purpose of this rule is to check that common roll forwards reported in a filing calculate, i.e. that the opening balance plus the movements in the period equals the closing balance.
 - **[DQC_US_0256 - BDC Investment Income Tagged with Nonoperating Interest and Dividend Elements](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v32/docs/DQC_US_0256/DQC_0256.md)** – the purpose of this rule to ensure that Business Development Companies (BDCs) tag investment income from interest and dividends with the operating income elements rather than the nonoperating investment income elements.
 - **[DQC_US_0257 - BDC Investment Income Totals Tagged with InvestmentIncomeNet](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v32/docs/DQC_US_0257/DQC_0257.md)** – the purpose of this rule is to ensure that Business Development Companies (BDCs) do not use `InvestmentIncomeNet` for Total investment income, Net investment income before tax or Net investment income after tax.
 - **[DQC_US_0258 - BDC Total Expenses Tagged with OperatingExpenses](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v32/docs/DQC_US_0258/DQC_0258.md)** – the purpose of this rule is to ensure that Business Development Companies (BDCs) do not use `OperatingExpenses` for Total expenses before fee waivers or deductions.

### Executive Session - Discuss SEC Agenda topics

### Wrap Up/Future Meetings
______________________
