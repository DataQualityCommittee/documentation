# Data Quality Committee Meeting - June 27, 2024

### Introductions

### Approval of Minutes
  + [March 14, 2024 Meeting Minutes (Word doc)](https://github.com/DataQualityCommittee/documentation/raw/master/meetings/jun_2024/DRAFTDQCMeetingNotes240314.docx)

### Approve Version 24 DQC Rules and Guidance 

  - **UPDATED [Reporting US GAAP Dividend Disclosures in XBRL - FAQ (PDF)](https://github.com/DataQualityCommittee/documentation/raw/master/guidance/guid-dividend.pdf)**
    
  **CHANGES TO DIVIDEND GUIDANCE RULES**
  - **[DQC_178 - Dividend Disclosures in the Statement of Changes in Shareholders Equity](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v24/docs/DQC_US_0178/DQC_0178.md)** - The rule identifies where the filer has used inappropriate combinations of dividend elements in the Statement of Shareholders Equity. The rule is comprised of nine components that help filers to select the correct elements and to tag the values with the appropriate sign.
  - **[DQC_179 - Dividend Event Disclosures](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v24/docs/DQC_US_0179/DQC_0179.md)** - The rule identifies those cases where the filer has used the DividendsAxis inappropriately in the filing.  The rule has seven components that check that the filer complies with the _DQC Dividend guidance_.
  - **[DQC_180 - Dividend Financial Statement Disclosures](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v24/docs/DQC_US_0180/DQC_0180.md)** - The four components of this rule check dividend disclosures in the face of the financial statements. This rule supports the _DQC Dividend guidance_.
  - **[DQC_186 - Dividend Disclosures in the Components of Equity (IFRS)](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v24/docs/DQC_IFRS_0186/DQC_0186.md)** - The rule identifies where the filer has used inappropriate combinations of dividend elements in the Statement of Shareholders Equity.  Three components of the rule check that: 
     1) dividend elements used with the retained earnings member are reported with a positive value, 
     2) dividend line items have been used with the appropriate members of the `ComponentsOfEquityAxis`, and 
     3) the concepts `DividendsPaidOrdinarySharesPerShare` and `DividendsPaidOtherSharesPerShare` are not used with a redundant class of stock axis.
    
  **UPDATES**
  - **ADDED [DQC_188 - Proxy Statement](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v24/docs/DQC_US_0188/DQC_0188.md)** - This rule identifies the members used on this axis in the filing and compares the members used to the members defined in the SEC taxonomy.  If there are no common members the rule will report an error. It is expected that the filers will use the members defined in the SEC taxonomy and will not create all extension members. 
  - **MOVED [DQC_193 - Standard Dividend Member Name](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v24/docs/DQC_US_0193/DQC_0193.md)** - Isolated rule 10153 from initial placement in DQC_179 so this rule can have a later effective date. This rule supports the _DQC Dividend guidance_. 
    
  **UNCHANGED**  
  - **[DQC_181 - Interest Expense Operating and Nonoperating](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v24/docs/DQC_US_0181/DQC_0181.md)** - This rule checks that filers use the correct elements to record interest expense operating and interest expense nonoperating. In the 2024 US-GAAP taxonomy, the FASB added 2 new elements: `InterestExpenseNonoperating` and `InterestExpenseOperating`. The definition and label changed for the prior element `InterestExpense`.  Two components of this rule help ensure that filers review the usage of the element `InterestExpense`, and replace it with the more specific operating or non-operating element.  Applicable only to the 2024 Taxonomy.
  - **[DQC_182 - Dimensional Equivalents Using the Meta Taxonomy](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v24/docs/DQC_US_0182/DQC_0182.md)** - This rule overlaps with some of the rules implemented in DQC_0011. This rule will eventually supersede rule DQC_0011. The rule uses the dimensional equivalents defined in the Meta taxonomy and checks that the values reported in a filing are consistent. As the meta taxonomy is updated the rule will take advantage of new relationships to check.
The rule reads the relationship arc http://www.xbrl.org/2021/arcrole/concept-dimensional-equivalent to determine the axis, members and line items equivalent associated with a taxonomy line item.
  - **[DQC_183 - Face Financial Statement Location using the Accrual Axis](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v24/docs/DQC_US_0183/DQC_0183.md)** - The rule is intended to ensure that the `StatementOfFinancialPositionLocationActivityAccrualAxis` axis has been used correctly in filings and the BalanaceSheetLocation axis is not used to indicate the accounts where accruals are posted to.
  - **[DQC_184 - OCI Reconciliation of Before Tax and Net of Tax OCI](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v24/docs/DQC_US_0184/DQC_0184.md)** - The rule is intended to ensure that the OCI elements have been reported with the correct signage.
  - **[DQC_185 - Reconciliation in Schedule Of Unrecognized Tax Benefits Roll Forward Table Text](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v24/docs/DQC_US_0185/DQC_0185.md)** - The rule checks whether the reconciliation facts are contained within the `ScheduleOfUnrecognizedTaxBenefitsRollForwardTableTextBlock` in the inline XBRL filing. In 2024, the FASB updated the taxonomy to include Unrecognized Tax Benefit elements to be included in the text block element `ScheduleOfUnrecognizedTaxBenefitsRollForwardTableTextBlock`. Previously these reconciliation elements were descendants of `SummaryOfIncomeTaxContingenciesTextBlock`. This rule only applies to the 2024 taxonomy.
  - **[DQC_187 - Property Plant and Equipment Calculation](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v24/docs/DQC_US_0187/DQC_0187.md)** - This rule tests that the elements `PropertyPlantAndEquipmentGross` and  `PropertyPlantAndEquipmentAndFinanceLeaseRightOfUseAssetBeforeAccumulatedDepreciationAndAmortization` are recorded correctly.  Four components of the rule check calculations to determine these elements are recorded consistently.
  - **[DQC_0015 - NonNegative Rule (2024 update)](https://github.com/dataqualitycommittee/dqc_us_rules/tree/v24/docs/DQC_US_0015/DQC_0015.md)** - The non negative rules were updated for 2024 elements.  


Proposed Effective Date for Version 24 **August 31, 2024 (exclude DQC_0193 Standard Dividend Member Name)**  
Proposed Effective Date for DQC_0193 Standard Dividend Member Name **November 30, 2024** 

### Executive Session
  - Introduction of Version 25 DQC Rules - Rule forms to be distributed after meeting
### Wrap Up/Future Meetings
  - September 25, 2024 (Washington, DC)
    - 10 AM - Noon ET DQC (AICPA Office)
    - 1 - 3 PM ET SEC Staff (SEC Office) 
______________________
