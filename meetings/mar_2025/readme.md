# Data Quality Committee Meeting - March 19, 2025

### Introductions

### Approval of Minutes
  + [September 25, 2024 Meeting Minutes (Word doc)](https://github.com/DataQualityCommittee/documentation/raw/master/meetings/mar_2025/DRAFTDQCMeetingNotes240925.docx)

### Introduction of Version 27 DQC Rules 

  - **[DQC_203 – Income Tax Authority Axis with Invalid Members](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v27/docs/DQC_US_0203/DQC_0203.md)** - The rule checks that filers do not report values using the DomesticCountryMember, ForeignCountryMember with the IncomeTaxAuthorityAxis.
  - **[DQC_204 – Invalid Axis used for Tangible and Intangible Assets](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v27/docs/DQC_US_0204/DQC_0204.md)** - The rule checks that filers have used the `PropertyPlantAndEquipmentByTypeAxis` and the `FiniteLivedIntangibleAssetsByMajorClassAxis` with the appropriate members and concepts.  The rule has four components.
  - **[DQC_205 – Invalid Member used on Balance Sheet Location Axis](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v27/docs/DQC_US_0205/DQC_0205.md)** - The rule checks that filers have used an appropriate member on the balance sheet location axis.
  - **[DQC_206 – Invalid Member used on Disaggregation Of Income Statement Expense Caption Axis](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v27/docs/DQC_US_0206/DQC_0206.md)** - The rule checks that filers have used an appropriate member on the Disaggregation Of Income Statement Expense Caption Axis.
  - **[DQC_207 – Invalid Subtotals in Schedule of Investments](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v27/docs/DQC_US_0207/DQC_0207.md)** - The purpose of this rule is to ensure that the fair value of investments reported for broader categories (e.g., by industry, geography, or security type) is greater than or equal to the fair value reported for more specific categories that include additional dimensions.
  - **[DQC_208 – Subtotals match Extensible Enumerations in the Schedule of Investments](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v27/docs/DQC_US_0208/DQC_0208.md)** - TThe purpose of Rule DQC_0208 is to ensure that any extensible enumeration value reported for the investment type and industry type is properly used as a member on the `InvestmentTypeAxis` and `EquitySecuritiesByIndustryAxis`.
  - **[DQC_209 – OCI Reconciliation of Before Tax and Net of Tax OCI](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v27/docs/DQC_US_0209/DQC_0209.md)** - The purpose of Rule DQC_0209 is to ensure that all required extensible enumeration elements, such as `InvestmentIndustrySectorExtensibleEnumeration`, are properly reported in the Schedule of Investments (SOI).

### Executive Session
  - Review Agenda for March 26 Meeting with SEC Staff (virtual)
### Wrap Up/Future Meetings
  - March 26, 2025 1 PM (Virtual) with SEC Staff
  - June 18, 2025 1 PM (Virtual)
  - FALL 2025 TBD IN PERSON, Washington, DC
    - 10 AM - Noon ET DQC
    - 1 - 3 PM ET SEC 
______________________
