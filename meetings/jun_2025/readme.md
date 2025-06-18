# Data Quality Committee Meeting - June 18, 2025

### Introductions

### Approval of Minutes
  + [March 19, 2025 Meeting Minutes (Word doc)](https://github.com/DataQualityCommittee/documentation/raw/master/meetings/jun_2025/DRAFTDQCMeetingNotes250319.docx)

### Approve Version 27 DQC Rules 

  - **[DQC_203 – Income Tax Authority Axis with Invalid Members](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v27/docs/DQC_US_0203/DQC_0203.md)** - The rule checks that filers do not report values using the `DomesticCountryMember`, `ForeignCountryMember` with the `IncomeTaxAuthorityAxis`.
  - **[DQC_204 – Invalid Axis used for Tangible and Intangible Assets](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v27/docs/DQC_US_0204/DQC_0204.md)** - The rule checks that filers have used the `PropertyPlantAndEquipmentByTypeAxis` and the `FiniteLivedIntangibleAssetsByMajorClassAxis` with the appropriate members and concepts.
  - **[DQC_205 – Invalid Member used on Balance Sheet Location Axis](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v27/docs/DQC_US_0205/DQC_0205.md)** - The rule checks that filers have used an appropriate member on the balance sheet location axis. The rule identifies the line items used on the balance sheet and checks if the members on the balance sheet location axis corresponds to the items on the balance sheet.
  - **[DQC_206 – Invalid Member used on Disaggregation Of Income Statement Expense Caption Axis](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v27/docs/DQC_US_0206/DQC_0206.md)** - The rule checks that filers have used an appropriate member on the Disaggregation Of Income Statement Expense Caption Axis. The rule identifies the expense line items used on the Income Statement and checks if the typed members on the Disaggregation Of Income Statement Expense Caption Axis correspond to the expense items on the Income Statement.
  - **[DQC_207 – Invalid Subtotals in Schedule of Investments](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v27/docs/DQC_US_0207/DQC_0207.md)** - The purpose of this rule is to ensure that the fair value of investments reported for broader categories (e.g., by industry, geography, or security type) is greater than or equal to the fair value reported for more specific categories that include additional dimensions.
  - **[DQC_208 – Subtotals match Extensible Enumerations in the Schedule of Investments](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v27/docs/DQC_US_0208/DQC_0208.md)** - The purpose of Rule DQC_0208 is to ensure that any extensible enumeration value reported for the investment type and industry type is properly used as a member on the `InvestmentTypeAxis` and `EquitySecuritiesByIndustryAxis`.
  - **[DQC_209 – OCI Reconciliation of Before Tax and Net of Tax OCI](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v27/docs/DQC_US_0209/DQC_0209.md)** - The purpose of Rule DQC_0209 is to ensure that all required extensible enumeration elements, such as `InvestmentIndustrySectorExtensibleEnumeration`, are properly reported in the Schedule of Investments (SOI).
  - **[DQC_210 – Missing Investment Identifier Axis](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v27/docs/DQC_US_0210/DQC_0210.md)** - The purpose of Rule DQC_0210 is to ensure that all fact values related to individual investments are tagged with the axis `InvestmentIdentifierAxis`.
  - **[DQC_0211 - Missing Fact Value for Extensible Enumeration](https://github.com/DataQualityCommittee/dqc_us_rules/tree/v27/docs/DQC_US_0211/DQC_0211.md)** - The purpose of this rule is to ensure that when a filer reports an extensible enumeration fact value indicating the location of a face statement concept, the corresponding monetary fact value for that concept is also reported in the filing.

### Introduction of Version 28 DQC Rules 
  - **[DQC_0212 - Missing Shares Issued or Authorized Facts When Shares Outstanding Reported](https://github.com/campbellpryde/dqc_us_rules/tree/v28/docs/DQC_US_0212/DQC_0212.md)**
  - **[DQC_0213 - Missing Calculation Children for Key Balance Sheet Items](https://github.com/campbellpryde/dqc_us_rules/tree/v28/docs/DQC_US_0213/DQC_0213.md)**
  - **[DQC_0214 - Missing Equity Concepts in Balance Sheet Calculation](https://github.com/campbellpryde/dqc_us_rules/tree/v28/docs/DQC_US_0214/DQC_0214.md)**
  - **[DQC_0215 - Extension Element Name Matches US GAAP Element](https://github.com/campbellpryde/dqc_us_rules/tree/v28/docs/DQC_US_0215/DQC_0215.md)**
  - **[DQC_0216 - Improper Use of Extension Geography Members on StatementGeographicalAxis](https://github.com/campbellpryde/dqc_us_rules/tree/v28/docs/DQC_US_0216/DQC_0216.md)**

### Wrap Up/Future Meetings
  - October 15, 2025 (in-person Washington, DC)
    - 10 AM - Noon ET DQC (AICPA Office)
    - 1 - 3 PM ET SEC Staff (SEC Office) 
______________________
