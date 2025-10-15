# Data Quality Committee Meeting - October 15, 2025

### Introductions

### Approval of Minutes
  + [June 18, 2025 Meeting Minutes (Word doc)](https://github.com/DataQualityCommittee/documentation/raw/master/meetings/oct_2025/DRAFTDQCMeetingNotes250618.docx?raw=true)

### Approve Version 28 DQC Rules
  - **See [Overview of Changes (Word doc)](https://github.com/DataQualityCommittee/documentation/raw/master/meetings/oct_2025/v28changes.docx?raw=true)** 

  - **[DQC_212 – Missing Shares Issued or Authorized Facts When Shares Outstanding Reported](https://github.com/DataQualityCommittee/dqc_us_rules/tree/v28/docs/DQC_US_0212/DQC_0212.md)** - This rule ensures that when a filer reports facts for shares outstanding (such as `CommonStockSharesOutstanding` or `SharesOutstanding`), they also report the corresponding facts for shares issued and shares authorized, as appropriate. This rule validates that filings do not omit required facts that provide a complete picture of a company's equity structure. If shares outstanding and shares issued (or authorized) are the same, both concepts should be tagged. If shares authorized are unlimited, the appropriate "unlimited" concept should be used. 
  - **[DQC_213 – Missing Calculation Children for Key Balance Sheet Items](https://github.com/DataQualityCommittee/dqc_us_rules/tree/v28/docs/DQC_US_0213/DQC_0213.md)** - This rule ensures that key balance sheet concepts, such as `Assets`, `AssetsCurrent`, `NoncurrentAssets`, `Liabilities`, `LiabilitiesCurrent`, `LiabilitiesNoncurrent`, and `StockholdersEquity` are not reported as leaf items (i.e., without calculation children) in the balance sheet calculation linkbase. 
  - **[DQC_214 – Missing Equity Concepts in Balance Sheet Calculation](https://github.com/DataQualityCommittee/dqc_us_rules/tree/v28/docs/DQC_US_0214/DQC_0214.md)** - This rule ensures that key equity related facts disclosed in the financial statements, such as Treasury Stock, Common Stock, Additional Paid-In Capital, Retained Earnings, Accumulated Other Comprehensive Income (Loss), Noncontrolling Interest, and Preferred Stock—are also included in the equity section of the balance sheet calculation relationships.  
  - **[DQC_215 – Extension Element Name Matches US GAAP Element](https://github.com/DataQualityCommittee/dqc_us_rules/tree/v28/docs/DQC_US_0215/DQC_0215.md)** - This rule ensures that when a filer reports an extensible enumeration fact value indicating the location of a face statement concept, the corresponding monetary fact value for that concept is also reported in the filing. 
  - **[DQC_216 – Improper Use of Extension Geography Members on StatementGeographicalAxis](https://github.com/DataQualityCommittee/dqc_us_rules/tree/v28/docs/DQC_US_0216/DQC_0216.md)** - This rule ensures that filers use the appropriate standard members for the `StatementGeographicalAxis`, specifically when only two members are present: one representing the United States and one representing non-US regions. 
  - **[DQC_217 – Improper Use of Notional Amount Concepts with InvestmentIdentifierAxis](https://github.com/DataQualityCommittee/dqc_us_rules/tree/v28/docs/DQC_US_0217/DQC_0217.md)** - This rule ensures that notional amount concepts, specifically `DerivativeLiabilityNotionalAmount` and `DerivativeAssetNotionalAmount`, are not reported with the `InvestmentIdentifierAxis`. This rule enforces correct dimensional tagging for derivative notional amounts, in accordance with SEC guidance, to promote accurate, complete, and consistent reporting in the Schedule of Investments (SOI). 
  - **[DQC_219 – Missing Value for NonInvestmentAssetsLessNonInvestmentLiabilities](https://github.com/DataQualityCommittee/dqc_us_rules/tree/v28/docs/DQC_US_0219/DQC_0219.md)** - This rule ensures that filers report a value for the element `NonInvestmentAssetsLessNonInvestmentLiabilities` when certain conditions are met in the filing. Specifically, if the filer has reported both `AssetsNet` and `InvestmentOwnedAtFairValue` in the same context, and `AssetsNet` has a calculation child of `InvestmentOwnedAtFairValue` as well as an extension item with a negative value, then the filer should also report a value for `NonInvestmentAssetsLessNonInvestmentLiabilities`. 
  - **[DQC_220 – Improper Use of StatementTable in Notes Disclosures](https://github.com/DataQualityCommittee/dqc_us_rules/tree/v28/docs/DQC_US_0220/DQC_0220.md)** - This rule ensures that filers do not use the `StatementTable` element in the notes disclosures section of their filings. The `StatementTable` is intended to be used only in the face financial statements, not in the notes. 
  - **[DQC_221 – Missing NumberOfReportableSegments When Segment Facts Are Reported](https://github.com/DataQualityCommittee/dqc_us_rules/tree/v28/docs/DQC_US_0221/DQC_0221.md)** - This rule ensures that filers report the `NumberOfReportableSegments` element whenever segment facts are disclosed in the filing. Even if a filer only has one segment, the number of reportable segments must be explicitly reported. 
  - **[DQC_222 – Scaling Error in EntityPublicFloat](https://github.com/DataQualityCommittee/dqc_us_rules/tree/v28/docs/DQC_US_0222/DQC_0222.md)** - This rule ensures the value reported for `dei:EntityPublicFloat` is correctly scaled and falls within a reasonable range for both standard and small business filers. 
  - **[DQC_223 – Extension Leaf Items on Statement of Operating Activities or Income Statement](https://github.com/DataQualityCommittee/dqc_us_rules/tree/v28/docs/DQC_IFRS_0223/DQC_0223.md)** - This rule ensures extension concepts used as leaf items (i.e., items with no calculation children) on the statement of operating activities or income statement are appropriately named.

### Introduction of Version 29 DQC Rules

### _Break_

### Executive Session
  - SEC Agenda Topics

### Wrap Up/Future Meetings
  - SEC meeting (TBD)
  - January 14, 2026 12 PM ET
______________________
