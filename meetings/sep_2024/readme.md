# Data Quality Committee Meeting - September 25, 2024

### Introductions/New Members 

  - Kathleen Shelton, Donnelley Financial Solutions
  - Sonny Jablonski, Workiva

### Approval of Minutes
  + [June 27, 2024 Meeting Minutes (Word doc)](DRAFTDQCMeetingNotes240627.docx)

### Approve Version 25 DQC Rules
- **[DQC_190 - Employee Benefit Reporting](https://github.com/DataQualityCommittee/dqc_us_rules/tree/v25/docs/DQC_US_0190/DQC_0190.md)** - This rule contains a number of checks to ensure that the form 11-K (EBP) is completed in compliance with the FASB implementation guide. 
  > During the public review the following issues were identified in the rules and corrected.
  > - Rule 10600 detected where EBP elements were used in a US GAAP filing.  The rule was revised to reduce the scope of elements classified as EBP elements.  As written the dts resolution pulled in US-GAAP elements into items classified as EBP elements.  The rule was revised only to include elements that were in the EBP namespace. ('us-gaap-ebp')
  > - Rules checking the validity of hypercubes were updated to only include facts that were present within that cube.

- **[DQC_191 - Proxy - PEO Concepts Recorded with NEO Member](https://github.com/DataQualityCommittee/dqc_us_rules/tree/v25/docs/DQC_US_0191/DQC_0191.md)** - This rule checks proxy filings to ensure that the PEO elements ecd:PeoName, ecd:PeoTotalCompAmt, ecd:PeoActuallyPaidCompAmt are not used with the axis ExecutiveCategoryAxis and member NonPeoNeoMember.
  > The rule was updated to operate correctly on the following PEO elements:
  > - ecd:PeoName, 
  > - ecd:PeoTotalCompAmt, 
  > - ecd:PeoActuallyPaidCompAmt

- **[DQC_192 - Balance Sheet Numerical Scaling](https://github.com/DataQualityCommittee/dqc_us_rules/tree/v25/docs/DQC_US_0192/DQC_0192.md)** - This rule checks if the scale used on monetary amounts reported on the balance sheet is correct. 
  > The rule was updated to correct typos in the message.

### Introduction of Version 26 DQC Rules
Rule forms to be distributed after meeting for approval via email.

**DQC_0194 - This rule is designed to address the tagging errors and inconsistencies in the statement of changes in shareholders equity.**
 - Rule 10621 - US-GAAP  
 Checks that the Common stock member and associated line items have the appropriate sign. Non neg rules are currently not run on the Statement of Shareholders equity. This rule checks if the concepts used with the common stock member have the appropriate sign.
 - Rule 10622 - US-GAAP  
 This rule checks that the Common stock member is not used with an inappropriate line item. The rule looks at those line items in the statement of shareholders equity that cannot be used with the member CommonStockMember.
 - Rule  10623  - US-GAAP  
 This rule determines if the concept StockholdersEquity has been used with a Non controlling interest member. This element should not have a value when used with a non controlling interest [Member] as the element does not include a non controlling interest component. Filers should change the element to StockholdersEquityIncludingPortionAttributableToNoncontrollingInterest.
 - Rule  10624  - US-GAAP  
 This rule checks if the concepts SharesOutstanding, CommonStockSharesOutstanding, PreferredStockSharesOutstanding, SharesIssued, CommonStockSharesIssued, or PreferredStockSharesIssued has a value that has been used with Treasury Stock Member on the StatementEquityComponentsAxis. These concepts should not have a value when used with Treasury Stock Member.  FASB FAQ guidance (https://xbrl.fasb.org/resources/taxonomyfaq.pdf) 2.16 requires that specific line item elements are used for treasury shares such as TreasuryStockCommonShares and TreasuryStockPreferredShares rather than SharesOutstanding, CommonStockSharesOutstanding, PreferredStockSharesOutstanding, SharesIssued, CommonStockSharesIssued, or PreferredStockSharesIssued
 - Rule  10626  - US-GAAP  
 The rule checks if the filer has used the concept SharesIssued and has also used the value SharesOutstanding with both using the common stock member. The filer should report one or the other but not both when using the common stock member. If the column representing shares in the Changes in equity represents issued shares then the SharesOutstanding concept should not be used with the common stock member. If the column representing shares in the Changes in equity represents outstanding shares then the SharesIssued element should not be used with the common stock member.
 - Rule  10627  - US-GAAP  
 This rule identifies those concepts in the changes in shareholders equity that cannot be used with the retained earnings member, and checks if the filer has used them with a retained earnings member. This concept should not have a value when used with a retained earnings member.
 - Rule 10628  - US-GAAP  
 The rule checks if an instant value that is not equity or shares issued or outstanding has been used with the StatementEquityComponentsAxis and CommonStockMember. The identified instance concepts should not be used to represent an opening or closing balance in the changes of equity.  
 - Rule 10629  - US-GAAP  
 The rule checks if an instant value that is not equity or shares issued or outstanding has been used with the StatementEquityComponentsAxis and PreferredStockMember. The identified instance concepts should not be used to represent an opening or closing balance in the changes of equity.
 - Rule 10630  - US-GAAP  
 The rule checks if an instant value that is not equity has been used with the StatementEquityComponentsAxis and a Retained Earnings Member. The identified instance concepts should not be used to represent an opening or closing balance in the changes of equity.
 - Rule 10631  - US-GAAP  
 The rule checks if an instant value that is not equity has been used with the StatementEquityComponentsAxis and a Treasury Stock Member. The identified instance concepts should not be used to represent an opening or closing balance in the changes of equity. 
 - Rule 10632  - US-GAAP  
 The rule checks if an instant value that is not equity has been used with the StatementEquityComponentsAxis and an AOCI Member. The identified instance concepts should not be used to represent an opening or closing balance in the changes of equity. 
 - Rule 10634  - US-GAAP  
 This rule checks that no income statement items are used with the Equity component axis except for the retained earnings members.
 - Rule 10640  - IFRS  
 The rule checks if an instant value that is not equity or shares issued or outstanding has been used with the ComponentsOfEquityAxis and IssuedCapitalMember. The identified instance concepts should not be used to represent an opening or closing balance in the changes of equity.  
 
**DQC_0195** - This rule is intended to ensure correct tagging of the new tax disclosures required in 2025.  
 - Rule 10650  - US-GAAP  
 This rule checks that if the filer has reported a tax reconciliation item as a percentage that they have also reported the equivalent monetary amount.
 - Rule 10651  - US-GAAP  
 This rule checks that if the filer has reported a tax reconciliation item as a monetary amount that they have also reported the equivalent percentage amount.
 - Rule 10652  - US-GAAP  
 This rule checks that the tax percentage calculation has used a consistent denominator.
 - Rule 10653  - US-GAAP  
 This rule checks that if the filer has used the domestic and foreign member to classify taxes that they have not tagged values for either the domestic member or the foreign member.

### Executive Session - Review Agenda for Meeting with SEC Staff
 - DQC Analysis of trends by rule
 - Meta Taxonomy 
 - IFRS Taxonomy
 - FDTA Response Status/SEC Comment
 - Letters on XBRL-tagging

### Wrap Up/Future Meetings
  - March 26, 2025
    - 10 AM ET DQC
    - 1 - 3 PM ET SEC Staff (SEC Office)
  - June 2025 TBD
  - October 8, 2025 IN PERSON, Washington, DC 
    - 10 AM ET DQC
    - 1 - 3 PM ET SEC Staff
______________________
