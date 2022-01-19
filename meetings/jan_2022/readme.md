# Data Quality Committee Meeting - January 19, 2022

### Introductions
  
### Approval of Minutes
  + [September 29, 2021 Meeting Minutes](DRAFTDQCMeetingNotes09292021.docx?raw=true)

### Review and Approval of Version 17 DQC Rules

[**DQC_0125 - Lease Cost Cannot be Negative**](https://xbrl.us/dqc_0125) 
Lease costs can be negative in those cases where the lease is sub leased to another party and the sublease income exceeds the lease cost. This rule identifies those cases where the lease cost is negative and no Sublease Income is reported.

[**DQC_0126 - FS Calculation Check with Non Dimensional Data**](https://xbrl.us/dqc_0126) 
This rule identifies those cases where the calculations defined for the face financial statements (Statement of Changes in Shareholders Equity is not covered) in the company provided calculation linkbase do not match the actual values reported.  The rule works through every element in the statement and checks if it has any calculation children. If it does it takes the values of the children in the default and checks that they add to the parent value.

[**DQC_0127 - Incorrect Dimensional Item Used on Financial Statements**](https://xbrl.us/dqc_0127) 
This rule identifies those cases where the dimensional structures defined for the face financial statements (Statement of Changes in Shareholders Equity is not covered) in the company provided definition linkbase do not match the actual values reported.

<span style="color:red">_The rule was updated to exclude errors where fact values with a value of zero were being reported._</span>

[**DQC_0128 - Dimensional Values Larger than the Default**](https://xbrl.us/dqc_0128) 
The rule identifies a list of dimensions that should not have negative values and determines if any of the dimensionalized monetary values are greater than the default value.  This uses the same list of elements used by rule 15 for validating negative items.  The rule only checks dimensionalized values that appear on the following axes:

#### US GAAP
  - PropertyPlantAndEquipmentByTypeAxis, 
  - StatementClassOfStockAxis, 
  - LongtermDebtTypeAxis, 
  - srt:ProductOrServiceAxis, 
  - FiniteLivedIntangibleAssetsByMajorClassAxis, 
  - DebtInstrumentAxis
#### IFRS
  - ClassesOfPropertyPlantAndEquipmentAxis,
  - ClassesOfOrdinarySharesAxis, 
  - ProductsAndServicesAxis, 
  - ClassesOfIntangibleAssetsOtherThanGoodwillAxis
  - BorrowingsByNameAxis

[**DQC_0129 - Dimensional Equivalents IFRS**](https://xbrl.us/dqc_0129) 
This rule evaluates whether a fact expressed with no dimensions is equal to the same fact expressed in a table with dimensions. In addition, this rule determines if the dimensional value should be the inverse of the same value represented as a line item.

<span style="color:red">_The rule was amended to remove those cases where ContinuingAndDiscontinuedOperationsAxis is used with the ContinuingOperationsMember._</span>

[**DQC_0130 - Earnings Per Share Calculation IFRS**](https://xbrl.us/dqc_0130) 
This rule evaluates if the value reported for earnings per share metrics matches the value calculated from its components.

[**DQC_0131 - Lease Allocation in Balance Sheet**](https://xbrl.us/dqc_0131) 
This rule detects of the value of a lease reported in the footnotes is greater than the balance sheet line item.

[**DQC_0132 - Operating Lease Amortization**](https://xbrl.us/dqc_0132) 
This rule identifies when an extension element is used instead of the standard element for OperatingLeaseRightOfUseAssetAmortizationExpense which was added to the 2020 US GAAP taxonomy.

### Introduction of Investments
  - Guidance
  - Rules

### Future Meetings
  - March 23, 2022 (with SEC staff)
  - June 29, 2022
  - September 21, 2022 (with SEC staff)
______________________
