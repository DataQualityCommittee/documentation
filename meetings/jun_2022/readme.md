# Data Quality Committee Meeting - June 29, 2022

### Introductions
  
### Approval of Minutes
  + [March 23, 2022 Meeting Minutes](DRAFTDQCMeetingNotes220322.docx?raw=true)

### Review and Approval of Version 18 DQC Rules

**[DQC_0133 - Equity Method Investment Reporting](https://github.com/dataqualitycommittee/dqc_us_rules/blob/v18/docs/DQC_US_0133/DQC_0133.md)** - The purpose of the rule is to ensure that filers consistently report Equity Method Investment (EMI) data.  This rule has three components to help filers to ensure that they are consistent with the guidance issued by the FASB "Dimensional Modeling for Disclosures of Consolidated and Nonconsolidated Entities".

**[DQC_0134 - Investment Schedule - Financial Instrument Axis](https://github.com/dataqualitycommittee/dqc_us_rules/blob/v18/docs/DQC_US_0134/DQC_0134.md)** - The purpose of the rule is to ensure that filers report values associated with the element AvailableForSaleDebtSecuritiesAmortizedCostBasis with the correct dimensions.  The rule is intended to align filer disclosures with the guidance defined by the FASB in "Financial Instruments Debt Securities".

The following elements were **added as a result of Public Review** to determine that they were used with the financial instruments axis:

  - AvailableForSaleDebtSecuritiesAmortizedCostBasis
  - DebtSecuritiesAvailableForSaleAmortizedCostCurrent, 
  - DebtSecuritiesAvailableForSaleAmortizedCostNoncurrent,
  - DebtSecuritiesAvailableForSaleAmortizedCostExcludingAccruedInterestBeforeAllowanceForCreditLoss,
  - DebtSecuritiesAvailableForSaleAmortizedCostExcludingAccruedInterestBeforeAllowanceForCreditLossCurrent,
  - DebtSecuritiesAvailableForSaleAmortizedCostExcludingAccruedInterestBeforeAllowanceForCreditLossNoncurrent,
  - DebtSecuritiesAvailableForSaleAmortizedCostExcludingAccruedInterestAfterAllowanceForCreditLoss,
  - DebtSecuritiesAvailableForSaleAmortizedCostExcludingAccruedInterestAfterAllowanceForCreditLossCurrent,
  - DebtSecuritiesAvailableForSaleAmortizedCostExcludingAccruedInterestAfterAllowanceForCreditLossNoncurrent, 
  - DebtSecuritiesAvailableForSaleAmortizedCostAfterAllowanceForCreditLoss, 
  - DebtSecuritiesAvailableForSaleAmortizedCostAfterAllowanceForCreditLossCurrent,
  - DebtSecuritiesAvailableForSaleAmortizedCostAfterAllowanceForCreditLossNoncurrent,
  - AvailableForSaleSecuritiesDebtSecurities,
  - AvailableForSaleSecuritiesDebtSecuritiesCurrent,
  - AvailableForSaleSecuritiesDebtSecuritiesNoncurrent,
  - DebtSecuritiesAvailableForSaleExcludingAccruedInterest,
  - DebtSecuritiesAvailableForSaleExcludingAccruedInterestCurrent,
  - DebtSecuritiesAvailableForSaleExcludingAccruedInterestNoncurrent

**[DQC_0135 - Extensible Enumerations for Financial Statement Captions](https://github.com/dataqualitycommittee/dqc_us_rules/blob/v18/docs/DQC_US_0135/DQC_0135.md)** – The FASB has defined a number of elements that if reported and are not included in the face financial statements, filers need to indicate which financial statement caption the amounts appear (these elements have been identified in the US GAAP taxonomy as extensible enumeration elements). This rule has two components. The first component identifies an error if the company has made a disclosure and has not included the caption where the amount appears in the financial statements.  The second reports an error for a fact that includes the Balance Sheet and Income Statement Location axis and does not have an associated extensible enumeration using the same dimensions.

**[DQC_0136 - Caption Value Matches Financial Statements](https://github.com/dataqualitycommittee/dqc_us_rules/blob/v18/docs/DQC_US_0136/DQC_0136.md)** - This rule is intended to identify those cases where the company uses an extensible list item that refers to a Balance Sheet or  Income Statement  line item that does not exist on the referenced Statement. The rule checks that the values provided for the extensible list items defined in the taxonomy are legitimate financial statement line items that appear in the presentation linkbase.

**[DQC_0137 - Location Axis with a Single Member](https://github.com/dataqualitycommittee/dqc_us_rules/blob/v18/docs/DQC_US_0137/DQC_0137.md)** - This rule is intended to pick up those cases where the location axis is used instead of the extensible enumeration element.

**Existing rule updates**
  1. Added rule US.0001.83 for RetirementPlanSponsorLocationAxis based on FASB feedback.
  1. Added rule US.0055.9842 to ensure that either the Domestic Plan [Member] or Foreign Plan [Member] has been included in the path of the descendants of the Retirement Plan Sponsor Location [Axis].
  1. Added rule US.0055.9843 that checks  that the Domestic Plan [Member]  has been included as a descendant of the Retirement Plan Sponsor Location [Axis] in the presentation linkbase. The FASB requires that this member includes children elements representing the Domestic Geography. 
  1. Added rule US.0055.9844 that checks  that  the Foreign Plan [Member]  has been included as a descendant of the Retirement Plan Sponsor Location [Axis] in the presentation linkbase  {$network.uri}. The FASB requires this member includes children elements representing the Foreign Geography.  
  1. Updated rule 0127 to exclude facts using the  EquityMethodInvestmentNonconsolidatedInvesteeAxis instead of ScheduleOfEquityMethodInvestmentEquityMethodInvesteeNameAxis
  1. Updated rule 127 to handle large real estate schedules. Excluded schedules where they were defined as statements.

### Review and Approval of Version 19 DQC Rules for Public Review

**[DQC_0139 - Bank Ratios - Scale Issues](https://github.com/dataqualitycommittee/dqc_us_rules/blob/v19/docs/DQC_US_0139/DQC_0139.md)** - This rule resolves the issue where the capital adequacy ratios are reported with an incorrect scale. It also ensures that filers have used the appropriate elements to report their capital adequacy ratios.

**[DQC_0140 - Investment Schedule Cross Calc](https://github.com/dataqualitycommittee/dqc_us_rules/blob/v19/docs/DQC_US_0140/DQC_0140.md)** - This rule is intended to identify those cases where the company has misused elements in the investment schedule showing the difference in amortized cost and fair value. The rule checks that the investment schedule that shows the difference between amortized cost and fair value is calculated correctly.

**[DQC_0141 - Inconsistent Accrued Interest Elements](https://github.com/dataqualitycommittee/dqc_us_rules/blob/v19/docs/DQC_US_0141/DQC_0141.md)** - The rule ensures that the correct elements are used in the investment schedule. Specifically it ensures that consistent elements are used for including and excluding accrued interest elements in the investment disclosure.

### Future Meetings
  - September 21, 2022 (with SEC staff)
______________________
