# 230 Statement of Cash Flows

## <a name="toc"></a>Table of Contents

[230-10 Overview](#1)
[230-10-45 - Cash, Cash Equivalents, Restricted Cash and Restricted Cash Equivalents](#2)
[230-10-45 - Gross and Net Cash Flows](#3)
[230-10-45 - Cash Flows from Investing Activities](#4)
[230-10-45 - Cash Flows from Financing Activities](#5)
[230-10-45 – Distributions Received from Equity Method Investees](#6)
[230-10-45 - Reporting Operating, Investing, and Financing Activities](#7)
[230-10-45 - Reconciliation of Net Income and Net Cash Flow from Operating Activities](#8)
[230-10-50 - Noncash Investing and Financing Activities](#9)
[205-20-50 - Disclosures Required for a Discontinued Operation Comprising a Component or Group of Components of an Entity](#10)
[Dimensions used on the Cash Flow Statement](#11)
[830-230-45 Foreign Currency Matters](#12)

### 

<div class="inset-right" style="background:#cccccc;border 1px solid #444444;float:right;margin-left:10px;padding:6px;text-align:center;font-size:small;line-height:105%;">[Return to
Table of Contents](#toc)</div>

<a name="1"></a>230-10 Overview

This document is intended to provide guidance on structuring and tagging the cash flow statement using the US GAAP Financial Reporting Taxonomy. The cash flow statement in the US GAAP taxonomy is structured as a cash T account. All elements that represent cash receipts and cash inflows, are defined as debit items to mirror inflows into a cash T account. All elements that represent cash outflows are represented as credits. The US GAAP taxonomy is structured so that elements that represent cash inflows and outflows are clearly distinguished from accrual items, with label names that indicate that the element represents a cash flow. Terms such as _"payments to"_ or _"proceeds from"_ are examples of words that would be included in the label names of elements to be used in the statement of cash flows.

#### Identification of the Cash Flow Statement

Because standard disclosure groups (roles) defined in the US GAAP taxonomy cannot be used by filers, the cash flow statement cannot be identified by using a standard role. In order for users to identify roles in a filing that represent the cash flow statement, the following conventions should be followed by filers.

First, the definition of the extended link role must contain the string "- Statement -". For example " **1006000 - Statement - Consolidated Statements of Cash Flows** ". Second, the abstract element _StatementOfCashFlowsAbstract_ **MUST** be included as the top or root element in the presentation linkbase for the Cash Flow Statement. In addition, this abstract should not be used in any other disclosure group that does not represent a cash flow statement. The figure below shows the definition of the extended link roles and the placement of the abstract element.

**Figure 1: Extended Link Roles**

[![Screen Shot 2017-04-04 at 10.33.00 AM.png](images/cashflows02.png?raw=true)](http://test.xbrl.us/php/dispatch.php?Task=xbrlChildrenGraph&Accession=0001064728-17-000026&Linkbase=Presentation&GroupURI=http://www.peabodyenergy.com/role/ConsolidatedStatementsOfCashFlows&API_Key=40d3c007-9e02-49ed-bc4b-83e379360ef2) 

To distinguish the cash flow statement from a parenthetical disclosure associated with the cash flow statement, the string "parenthetical" must be included in the extended link role URI name as well as in the description of the extended link role, for example _"http:/abc.com/role/ConsolidatedStatementsOfCashFlowsParenthetical_".

### 

<div class="inset-right" style="background:#cccccc;border 1px solid #444444;float:right;margin-left:10px;padding:6px;text-align:center;font-size:small;line-height:105%;">[Return to
Table of Contents](#toc)</div>

<a name="2"></a>230-10-45 - Cash, Cash Equivalents, Restricted Cash and Restricted Cash Equivalents

For companies that have not yet adopted ASU-2016-18, the cash flow statement should use a starting and ending balance that uses one of the following elements.

*   _CashAndCashEquivalentsAtCarryingValueIncludingDiscontinuedOperations_
*   _CashAndCashEquivalentsAtCarryingValue_
*   _CashCashEquivalentsAndFederalFundsSold (See note below)_
*   _Cash_
*   _CashEquivalentsAtCarryingValue_
*   _CashAndDueFromBanks_

Companies that have already adopted ASU-2016-18, should use the broadest element when possible.

For companies that have already adopted ASU-2016-18 and that are using US GAAP Taxonomy Release 2017, or for companies with fiscal years beginning after December 15, 2017, the cash flow should start and end with one of the following elements regardless whether restricted cash is included in the total or not:

*   _CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalents_
*   _CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsIncludingDisposalGroupAndDiscontinuedOperations_

For companies that have already adopted ASU-2016-18 and that are using the 2016 taxonomy or an earlier taxonomy, the filer should create an extension element with exactly the same name (including the same case) as the elements defined above that apply to ASU-2016-18.

The opening and closing balances in the cash flow statement **MUST** use the same element for all periods in a given filing.

The opening and closing balances of cash and cash equivalents in the cash flow statement **MUST** always use the element that includes discontinued operations, when cash flows related to discontinued operations is included in the statement. This opening balance includes the portion of cash that is attributable to the discontinued operation. This element can also be used if the company has no discontinued operations in a given period. The cash and cash equivalent balance, inclusive of discontinued operations, should not be used when the cash flow statement specifically excludes discontinued operations and the discontinued operations are disclosed separately in the notes. See [205-20-50-5B-C-1](https://asc.fasb.org/viewpage?ovcmd=goto&codification_text=205-20-50-5B-C-1) .

The following example shows a situation where the element " _CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsIncludingDisposalGroupAndDiscontinuedOperations_ " is used to identify the opening and closing balances on all three periods.

[Cash Reconciliation](https://test.xbrl.us/ca/inlineCA/ix?doc=/ca/inlineCA/cf/CashRec/CF_disc_ops-open_close_part.htm)

The cash flow statement should always use the same element to represent the opening and closing cash balances for all periods, irrespective of the cash element(s) used on the balance sheet.

The updated FASB standards, related to restricted cash, results in all movements in restricted cash during the period being included in the cash flow statement. Thus, the aggregate movement in restricted cash during the period should be included in the element "Cash, Cash Equivalents, Restricted Cash and Restricted Cash Equivalents, Period Increase (Decrease), Including Exchange Rate Effect". The requirements in this section of the codification means that individual movements in restricted cash should not appear in the cash flow statement for companies that have adopted ASU-2016-18\. The elements _IncreaseDecreaseInRestrictedCash_ , _DecreaseInRestrictedCash_, and _IncreaseInRestrictedCash_ should not appear in the movement of cash flows as they include the movements from restricted cash into cash and cash equivalents.

#### Cash, Cash Equivalents and Federal Funds Sold

Prior to the adoption of ASU-2016-18, financial institutions could include the values of federal funds sold in the opening and closing balance on the cash flow statement. Where these are incorporated in the opening and closing cash balances, the financial institution should use the element _CashCashEquivalentsAndFederalFundsSold_ to represent the opening and closing balances in the cash flow statement. The element_CashCashEquivalentsAndFederalFundsSold_ should **not** be used on the cash flow statement if the cash flow statement includes transactions representing the movement of these funds in the financing section of the cash flow statement such as:

*   _IncreaseDecreaseInFederalFundsPurchasedAndSecuritiesSoldUnderAgreementsToRepurchaseNet_
*   _IncreaseDecreaseInFederalFundsPurchased_
*   _ProceedsFromPaymentsForInSecuritiesSoldUnderAgreementsToRepurchase_

After the adoption of ASU-2016-18, companies should include the element _CashCashEquivalentsAndFederalFundsSold_ used on the balance sheet in the reconciliation between the balance sheet and the cash flow statement, and not as the opening and closing balance for the cash flow statement. The reconciliation will require a calculation linkbase that will indicate that federal funds sold are included in the opening balance of cash and cash equivalents on the cash flow statement.

#### Cash, Cash Equivalents and Short-Term Investments

Companies have used the element _CashCashEquivalentsAndShortTermInvestments_to represent the cash and cash equivalents on the balance sheet, and as the opening and closing element on the cash flow statement. In the example below, the company used this element to represent the total of short term investments and cash and due from banks.

**Figure 2: Short Term Investments**

![Screen Shot 2017-06-12 at 4.50.53 PM.png](images/cashflows03.png?raw=true)

This element _CashCashEquivalentsAndShortTermInvestments__,_ defined in the US GAAP taxonomy, represents cash and and short term investments with a maturity of a year or less. In the example above, the short term investments represents securities which fall due in 90 days and were purchased within 90 days of maturity. In this example, the company should have used the element _CashAndCashEquivalentsAtCarryingValue_on the balance sheet and the element _CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalents_ on the cash flow statement if they had adopted ASU-2016-18.

#### Reconciliation of Cash Flow Statement to the Balance Sheet

The elements included in the reconciliation of the cash flow statement to the balance sheet must be included in a calculation linkbase. The total balance of the reconciliation shown below must be one of the following elements and should also appear in the cash flow statement:

*   _CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalents_
*   _CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsIncludingDisposalGroupAndDiscontinuedOperations_

**Figure 3: Reconciliation of Balance Sheet to Cash Flow Statement**

![Screen Shot 2017-06-12 at 8.46.04 PM.png](images/cashflows04.png?raw=true)

##### Rules

DQC rule [DQC_0057](https://xbrl.us/dqc_0057) identifies when at least one of the following elements is not used in the cash flow statement to represent the opening and closing balances for each period reported:

1\. Filings that have adopted ASU-2016-18

_a._ _CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalents_

b. _CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsIncludingDisposalGroupAndDiscontinuedOperations_

2\. Filings that have **not** yet adopted ASU-2016-18

a. _CashAndCashEquivalentsAtCarryingValueIncludingDiscontinuedOperations_

_b._ _CashAndCashEquivalentsAtCarryingValue_

_c._ _CashCashEquivalentsAndFederalFundsSold_

_d._ _Cash_

_e._ _CashEquivalentsAtCarryingValue_

_f._ _CashAndDueFromBanks_

### 

<div class="inset-right" style="background:#cccccc;border 1px solid #444444;float:right;margin-left:10px;padding:6px;text-align:center;font-size:small;line-height:105%;">[Return to
Table of Contents](#toc)</div>

<a name="3"></a>230-10-45 - Gross and Net Cash Flows

**Reporting Gross Items in the Cash Flow Statement**

The US GAAP taxonomy provides for a number of net items in the cash flow statement such as _PaymentsForProceedsFromInvestments__,_ which mature in greater than 90 days. Under US GAAP, these items should generally not be used, as cash flows should be reported gross if the maturity is longer than 90 days. Instead of using these items, the filer should use the gross cash flow amount when available. Where the amount is a gross proceed and a gross payment in consecutive years, two separate elements should be used for the values. A single net element should not be used in these cases. When a filer splits a single line item into two components, the values will stay the same. It is not required that the filer report a value of zero for one line item. For example, Net Proceeds from issuance of long term debt has a value of 3,000 in period one and a value of -2,000 in period two. This is split into Gross Proceeds with a value of 3,000 in period one and Gross Repayments of Debt with a value of 2,000 in period two. There is no requirement to enter Gross Repayments of Debt with a value of 0 in period one and to enter Gross Proceeds with a value 0 in period two.

### 

<div class="inset-right" style="background:#cccccc;border 1px solid #444444;float:right;margin-left:10px;padding:6px;text-align:center;font-size:small;line-height:105%;">[Return to
Table of Contents](#toc)</div>

<a name="4"></a>230-10-45 - Cash Flows from Investing Activities

#### Movement Between Classes of Cash Flow Activity

Elements defined in the cash flow statement of the US GAAP taxonomy, are specifically tied to a given activity such as investing, financing or operating. Filers should not move these elements from one activity classification in the cash flow to another section of the cash flow statement. In general, the taxonomy defines additional industry-specific elements that in one industry may be considered investing, but in another industry are classified as operating.

##### Rules

DQC rule [DQC_0045](https://xbrl.us/dqc_0045) identifies where operating items are used as investing or financing items by identifying where these elements have been reclassified as investing or financing activities in the cash flow statement. The rule also identifies investing items reclassified as financing items and vice versa.

### 

<div class="inset-right" style="background:#cccccc;border 1px solid #444444;float:right;margin-left:10px;padding:6px;text-align:center;font-size:small;line-height:105%;">[Return to
Table of Contents](#toc)</div>

<a name="5"></a>230-10-45 - Cash Flows from Financing Activities

#### Proceeds From Issuance of Equity

The element _ProceedsFromIssuanceOfCommonStock_ is a financing cash flow element. As such, it represents the cash inflow from issuing equity. Many companies, when reporting this value however, report the value net of the issuance costs paid to third parties. Because companies report the value net of costs, the value can be negative when the proceeds are received in one period and the costs are paid in a later period. In the event of this occurrence, the negative amount should use the element _PaymentsOfStockIssuanceCosts__,_ recorded with a positive value.

If in one period the value is positive, representing the receipt of financing proceeds, and in an adjacent year it is negative, representing the issuance costs, then separate elements should be used to report the positive and negative values.

In the following case, the company reported net proceeds and separately reported the issuance costs as a parenthetical amount. In these cases, the company should use the US GAAP Taxonomy net element if one exists or create an extension element to report the net proceeds of 98,872 and 175,989.

**Figure Showing Net Proceeds With Parenthetical**

![Screen Shot 2017-04-11 at 8.22.19 PM.png](images/cashflows05.png?raw=true)

[230-10-45](https://asc.fasb.org/section&trid=2134463&para=SL94080555-108585) - Distributions Received from Equity Method Investees

When reporting distributions from equity method investments, any distributions reported as operating cash flows should use the element _EquityMethodInvestmentDividendsOrDistributions_. Any distributions represented as an investment activity, because the cash flow distribution represents a return of capital, as opposed to a distribution of a dividend, should use the element _ProceedsFromEquityMethodInvestmentDividendsOrDistributionsReturnOfCapital_ .

#### Noncontrolling Interests

Many companies have used the wrong standard element or have created extension elements to reflect proceeds from the sale of subsidiary stock. In those cases where a company sells subsidiary stock, it should use the element _ProceedsFromMinorityShareholders_. This element should be used to capture the cash received from the proceeds from the sale of subsidiary stock or the purchase of subsidiary stock by non controlling interests. Companies should not create extension elements like:

*   _ProceedsFromSaleOfSubsidiaryStockOwnership_
*   _CashContributionsReceivedFromSaleOfPortionOfSubsidiary_

More specific extensions should be linked via the extension linking mechanism [[1]](#_ftn1) to the parent element _ProceedsFromMinorityShareholders_. One example from an actual filing is _ProceedsFromStockOptionsExercisedOfSubsidiary__._

In addition, the element _PaymentsToMinorityShareholders_ should be used when a company increases its holdings in a subsidiary. Companies should not create extension elements like:

*   _PaymentsToPurchaseSharesOfSubsidiary_
*   _PurchaseOfSubsidiaryStock_

More specific extensions should be linked via the extension linking mechanism to the parent element _PaymentsToMinorityShareholders_. One example from an actual filing is _SharesofSubsidiaryRepurchasedforShareAwardPlan._

The amounts reported in the statement of cash flows are aggregate amounts for the reporting entity. If the amounts are specific to a subsidiary, but the amount is the same as the amount for the consolidated entity, then use the broad cash flow element. If the amount for all subsidiaries and a specific subsidiary are different, then this should be distinguished using a dimension.

### 

<div class="inset-right" style="background:#cccccc;border 1px solid #444444;float:right;margin-left:10px;padding:6px;text-align:center;font-size:small;line-height:105%;">[Return to
Table of Contents](#toc)</div>

<a name="6"></a>[230-10-45](https://asc.fasb.org/extlink&oid=99402803&loc=d3e3521-108585) - Reporting Operating, Investing, and Financing Activities

Paragraph 45-24 of the FASB codification requires that cash flows in investing, financing and operating are reported. These may be comprised of cash from discontinued operations in the cash flow statement. For the purposes of this guidance, filers should always report movements in cash flows using the cash flow elements reflecting the reporting requirement. Those elements are as follows:

*   [_Net Cash Provided by (Used in) Financing Activities_](https://asc.fasb.org/xbrllinks&trid=2134478#SL141515)
*   [_Net Cash Provided by (Used in) Investing Activities_](https://asc.fasb.org/xbrllinks&trid=2134478#SL141519)
*   [_Net Cash Provided by (Used in) Operating Activities_](https://asc.fasb.org/xbrllinks&trid=2134478#SL141523)

The following continuing operations elements should be used when the company reports amounts for both continuing and discontinued amounts:

*   [_Net Cash Provided by (Used in) Financing Activities, Continuing Operations_](https://asc.fasb.org/xbrllinks&trid=2134478#SL153480)
*   [_Net Cash Provided by (Used in) Investing Activities, Continuing Operations_](https://asc.fasb.org/xbrllinks&trid=2134478#SL153478)
*   [_Net Cash Provided by (Used in) Operating Activities, Continuing Operations_](https://asc.fasb.org/xbrllinks&trid=2134478#SL141507)

In the following example, the company has split the cash flows into continuing operations and discontinued operations. The line item "Net cash provided by (used in) financing activities" with values of 1,034 and 433 respectively would use the element for continuing operations of_NetCashProvidedByUsedInFinancingActivitiesContinuingOperations_ _._

**Figure 4:** [**Net Cash Provided by (Used in) Financing Activities, Continuing Operations**](https://asc.fasb.org/xbrllinks&trid=2134478#SL153480)

[![Screen Shot 2017-06-19 at 11.58.21 AM.png](images/cashflows06.png?raw=true)](https://www.sec.gov/Archives/edgar/data/1657853/000165785316000057/hghq32016form10-q.htm) 

##### Rules

If the cash flow continuing operations elements are used (i.e. [Net Cash Provided by (Used in) Financing Activities, Continuing Operations](https://asc.fasb.org/xbrllinks&trid=2134478#SL153480) ) in a filing, then the corresponding discontinued operations elements should also be present in the instance. Rule [DQC_0060](https://xbrl.us/dqc_0060) identifies those instances where the continuing operations element is used and no associated discontinued value is reported for a given period.

#### Net Period Increase Decrease Cash flows

The codification also requires that companies report the aggregate change in cash, restricted cash, and cash and restricted cash equivalents for the period:

_"…net effect of those flows on the total of cash, cash equivalents, and amounts generally described as restricted cash or restricted cash equivalents during the period. The statement of cash flows shall report that information in a manner that reconciles beginning and ending totals of cash, cash equivalents, and amounts generally described as restricted cash or restricted cash equivalents."_

The elements representing the change in total cash and cash equivalents, restricted cash or restricted cash equivalents during the period are:

###### Prior to ASU-2016-18

[_CashAndCashEquivalentsPeriodIncreaseDecrease_](https://asc.fasb.org/xbrllinks&trid=2134478#SL141689)

###### After ASU-2016-18

[_CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsPeriodIncreaseDecreaseIncludingExchangeRateEffect_](https://asc.fasb.org/xbrllinks&trid=2134478#SL215055)

These elements should be used in the cash flow statement to reconcile the opening and closing balances in the cash flow statement. The following more specific elements defined in the US GAAP taxonomy should be used if the subtotal is reported in the cash flow statement rolling up to the elements defined above:

1\. [_CashAndCashEquivalentsPeriodIncreaseDecreaseExcludingExchangeRateEffect_ ](https://asc.fasb.org/xbrllinks&trid=2134478#SL194600)(prior to ASU-2016-18)

2\. [_CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsPeriodIncreaseDecreaseExcludingExchangeRateEffect_ ](https://asc.fasb.org/xbrllinks&trid=2134478#SL215053)(After adoption of ASU-2016-18)

In some cases, companies do not report an aggregate total for the change in cash including the effect of the exchange rate. In the figure below, the company reports the change in cash net of exchange rate changes and the effect of the exchange rate but not the aggregation of the two.

**Figure 5: No subtotal presented that includes the effect of the exchange rate**

![Screen Shot 2017-04-19 at 2.02.40 PM.png](images/cashflows07.png?raw=true)

In these cases the company should use the element: [_CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsPeriodIncreaseDecreaseExcludingExchangeRateEffect_ ](https://asc.fasb.org/xbrllinks&trid=2134478#SL215053)(After adoption of ASU-2016-18)

Filers should use the element [_CashAndCashEquivalentsPeriodIncreaseDecrease_](https://asc.fasb.org/xbrllinks&trid=2134478#SL141689) or the element [_CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsPeriodIncreaseDecreaseIncludingExchangeRateEffect_ ](https://asc.fasb.org/xbrllinks&trid=2134478#SL215055)to report the aggregate change in cash flows for the period, irrespective if they have no discontinued operations and no exchange rate effect on cash reported. The element _NetCashProvidedByUsedInContinuingOperations_ should not be used to represent the aggregate increase or decrease in cash for the period. It is expected that the element _NetCashProvidedByUsedInContinuingOperations_ would only be used as a subtotal, or where the company shows the movement in cash for continuing operations and discontinued operations as separate items in the reconciliation of opening and closing cash balances. See figure below:

**Figure 6: Net Cash provided from Continuing and Discontinued Operations**

[**![Screen Shot 2017-05-11 at 6.09.07 PM.png](images/cashflows08.png?raw=true) **](https://www.sec.gov/Archives/edgar/data/1111711/000111171117000037/ni-20161231x10ka.htm) 

At a minimum, in any cash flow statement, one of the following elements must be included as the ultimate parent (root node) in the calculation linkbase prior to adoption of ASU 2016-18.

_1\._ [_CashAndCashEquivalentsPeriodIncreaseDecrease_](https://asc.fasb.org/xbrllinks&trid=2134478#SL141689)

_2\._ [_CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsPeriodIncreaseDecreaseIncludingExchangeRateEffect_](https://asc.fasb.org/xbrllinks&trid=2134478#SL215055)

_3\._ [_CashAndCashEquivalentsPeriodIncreaseDecreaseExcludingExchangeRateEffect_](https://asc.fasb.org/xbrllinks&trid=2134478#SL194600)

4\. [_CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsPeriodIncreaseDecreaseExcludingExchangeRateEffect_](https://asc.fasb.org/xbrllinks&trid=2134478#SL215053)

_5\._ _NetCashProvidedByUsedInContinuingOperations_ (Only if the element _NetCashProvidedByUsedInDiscontinuedOperations_ is also included the reconciliation)

The element [_CashPeriodIncreaseDecrease_](https://asc.fasb.org/xbrllinks&trid=2134478#SL141689) has been used by many filers to indicate the change in cash during the period. This guidance recommends using the broader elements that includes cash equivalents and restricted cash. Companies that have adopted ASU-2016-18, should use [_CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsPeriodIncreaseDecreaseIncludingExchangeRateEffect_ ](https://asc.fasb.org/xbrllinks&trid=2134478#SL215055)instead. If a filer has not yet adopted ASU-2016-18, the element [_CashAndCashEquivalentsPeriodIncreaseDecrease_](https://asc.fasb.org/xbrllinks&trid=2134478#SL141689) should be used but [_CashPeriodIncreaseDecrease_](https://asc.fasb.org/xbrllinks&trid=2134478#SL141689) can be used if the opening and closing cash balances for all periods in the cash flow statement use the element _Cash_. After adopting ASU-2016-18, these elements would no longer be used on the cash flow statement.

In some cases companies break out the cash flows from continuing and discontinued operations that include the effect of exchange rate changes on cash. The taxonomy has no elements representing the change in cash including the exchange rate impact for continuing and discontinued operations. In these cases, the companies should create an extension element.

**Figure 7: Effect of Foreign Exchange Impact for Continuing and Discontinued Operations**

[![Screen Shot 2017-06-06 at 4.29.54 PM.png](images/cashflows01.png?raw=true)](https://www.sec.gov/Archives/edgar/data/1657853/000165785316000057/hghq32016form10-q.htm) 

In those cases, where there is no increase or decrease in cash for the period either because there were no transactions for the period or the value inflows and outflows were the same, then a value of zero should be reported for the period.

##### Rules

_DQC_0046_

The element _NetCashProvidedByUsedInContinuingOperations_ should not include the exchange rate impact on cash balances. In addition, the element _NetCashProvidedByUsedInDiscontinuedOperations_ should not include the exchange rate impact from discontinued operations. The element [_CashAndCashEquivalentsPeriodIncreaseDecrease_](https://asc.fasb.org/xbrllinks&trid=2134478#SL141689) or the element [_CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsPeriodIncreaseDecreaseIncludingExchangeRateEffect_ ](https://asc.fasb.org/xbrllinks&trid=2134478#SL215055)should be used to reflect the net change in cash.

Rule [DQC_0046](https://xbrl.us/dqc_0046) flags those instances where the exchange rate impact is included in_NetCashProvidedByUsedInContinuingOperations_and _NetCashProvidedByUsedInDiscontinuedOperations_ to identify where these elements have been used as a surrogate for the increase (decrease) in cash for the period.

_DQC_0048_

At a minimum, in any cash flow statement, one of the following change in cash elements must appear as the ultimate parent (root node) in the calculation linkbase.

1\. [_CashAndCashEquivalentsPeriodIncreaseDecrease_](https://asc.fasb.org/xbrllinks&trid=2134478#SL141689)

_2\._ [_CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsPeriodIncreaseDecreaseIncludingExchangeRateEffect_](https://asc.fasb.org/xbrllinks&trid=2134478#SL215055)

3\. [_CashAndCashEquivalentsPeriodIncreaseDecreaseExcludingExchangeRateEffect_](https://asc.fasb.org/xbrllinks&trid=2134478#SL194600)

4\. [_CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsPeriodIncreaseDecreaseExcludingExchangeRateEffect_](https://asc.fasb.org/xbrllinks&trid=2134478#SL215053)

_5\._ _NetCashProvidedByUsedInContinuingOperations_ (Only if the element _NetCashProvidedByUsedInDiscontinuedOperations_ is also included the reconciliation between opening and closing cash)

6\. [_CashPeriodIncreaseDecrease_](https://asc.fasb.org/xbrllinks&trid=2134478#SL141689)

_7\._ _CashPeriodIncreaseDecreaseExcludingExchangeRateEffect_

Rule [DQC_0048](https://xbrl.us/dqc_0048) identifies those instances where one of these elements do not appear as a root node in the cash flow calculation tree.

_DQC_0062_

Rule [DQC_0062](https://xbrl.us/dqc_0062) identifies where no fact value is provided for any of the six change in cash flow elements listed above and a cash flow statement is reported by the entity. This rule is intended to identify those cases where the filer has reported a cash flow statement, but has not reported a value for the change in cash. This rule detects where an incorrect element, an inappropriate extension, an inappropriate dimension, or a missing value has been used to represent the change in cash for the period.

#### [Discontinued Operations](https://asc.fasb.org/xbrllinks&trid=2134478#SL153478)

If a company has income from discontinued operations included in net income, the company must report the cash flow from investing and operating activities related to discontinued operations. Companies must use the elements listed below in either the cash flow statement or notes to the financial statements:

_1\._ [_CashProvidedByUsedInInvestingActivitiesDiscontinuedOperations_](https://asc.fasb.org/xbrllinks&trid=2122207#SL153522)

_2\._ [_CashProvidedByUsedInOperatingActivitiesDiscontinuedOperations_](https://asc.fasb.org/xbrllinks&trid=2122207#SL153520)

When the following income items related to discontinued operations are included in the filing, then it is expected that at least one of the associated discontinued cash flow items (listed above) will also be included in the filing.

_1\._ [_DiscontinuedOperationIncomeLossFromDiscontinuedOperationBeforeIncomeTax_](https://asc.fasb.org/xbrllinks&trid=2122207#SL138038)

_2\._ [_DiscontinuedOperationTaxEffectOfDiscontinuedOperation_](https://asc.fasb.org/xbrllinks&trid=2122207#SL138146)

_3\._ [_IncomeLossFromDiscontinuedOperationsNetOfTaxAttributableToNoncontrollingInterest_](https://asc.fasb.org/xbrllinks&trid=2122207#SL160121)

_4\._ [_IncomeLossFromDiscontinuedOperationsNetOfTaxAttributableToReportingEntity_](https://asc.fasb.org/xbrllinks&trid=2122207#SL160117)

The following example shows how these elements should be used in the statement of cash flows:

**Figure 8: Discontinued Operations**

**![Screen Shot 2017-05-31 at 4.36.22 PM.png](images/cashflows09.png?raw=true)** 

[Link to disclosure](https://test.xbrl.us/ca/inlineCA/ix?doc=/ca/inlineCA/cf/DiscOps/CF_disc_ops-disc.htm)

##### Rules

_DQC_0061_

Rule [DQC_0061](https://xbrl.us/dqc_0061) identifies where any of the following conditions occur in a filing:

1\. _CashProvidedByUsedInInvestingActivitiesDiscontinuedOperations_ is **not** included as a calculation child of the element _NetCashProvidedByUsedInInvestingActivities_ but are both included in the change in cash for the period.

2\. _CashProvidedByUsedInOperatingActivitiesDiscontinuedOperations_ is **not** included as a calculation child of the element _NetCashProvidedByUsedInIOperatingActivities_ but are both included in the change in cash for the period.

3\. _CashProvidedByUsedInFinancingActivitiesDiscontinuedOperations_is not included as a calculation child of the element _NetCashProvidedByUsedInIFinancingActivities_ but are both included in the change in cash for the period.

The elements _NetCashProvidedByUsedInInvestingActivities__,_ _NetCashProvidedByUsedInIFinancingActivities__,_ and _NetCashProvidedByUsedInIOperatingActivities_ are intended to represent the total of cash provided by or used in continuing and discontinued operations. Cash flows from both discontinued operations and investing, financing or operating activities cannot add into the total of a shared ancestor, as this implies that discontinued operations is being double counted. For example, the value could be counted once in investing activities, and once again as investing activities from discontinued operations.

#### Accrual Items in Non Operating Cash flows

In the statement of cash flows, the reconciliation of cash flow from operating activities reverses income statement accrual items to reconcile to the actual operating cash flows. The financing and investing sections of the cash flow statement reconcile the opening and closing balances using direct cash flows (i.e. payments or proceeds) and not accrual items. In the case of the direct cash flows, cash inflows are debit items and cash outflows are credit items.

Accrual items should not be used to represent cash flow items in the financing and investing section such as expense and income elements. Overloading these elements to represent both the accrual and the cash flow undermines the ability of analysts to accurately calculate a company's cash flow from operations. For example, it is not appropriate to take accrual items which are typically found in the shareholders equity section and use them to represent cash flows in the financing section of the cash flow statement. Stockholders equity items typically represent the impact on the equity balance, whereas the cash flow items represent the cash impact on the cash balance at the end of the period.

For example, if a company has a dividend that appears in the stockholders' equity statement ( [_DividendsCommonStock_](https://asc.fasb.org/xbrllinks&trid=2209509#SL158107) with a debit balance), that same element should not be used to represent a cash flow (in the cash flow statement) even if the amount of this element represents the amount actually paid. The element [_PaymentsOfDividendsCommonStock_](https://asc.fasb.org/xbrllinks&trid=2134478#SL143232) with a credit balance should be used, as this represents the actual cash outflow.

In the case of the calculation of indirect cash flow items, accrual elements should be used to calculate operating cash flow. These accrual items typically appear in the income statement and shareholders' equity statement. There is no need to create an extension element to represent these items in the cash flow statement. In some cases, companies have duplicated items to represent non-cash expense items. In the US GAAP taxonomy, the cash flow statement includes the common non-cash expense and income items.

In those sections of the cash flow statement that represent direct cash flows, such as investing and financing items, these items should generally not be taken from other statements.

##### Rules

Investing and financing items should only use cash flow items in the reconciliation. See rule [DQC_0044](https://xbrl.us/dqc_0044)

### 

<div class="inset-right" style="background:#cccccc;border 1px solid #444444;float:right;margin-left:10px;padding:6px;text-align:center;font-size:small;line-height:105%;">[Return to
Table of Contents](#toc)</div>

<a name="7"></a>[230-10-45](https://asc.fasb.org/extlink&oid=99402803&loc=d3e3602-108585) - Reconciliation of Net Income and Net Cash Flow from Operating Activities

#### Selecting elements for the Reconciliation of Net Income

When presenting an indirect cash flow statement, the filer reconciles from net income to the operating cash flows for the period. The starting point however, has to be net income including non-controlling interest. The element for this in the US GAAP taxonomy is _ProfitLoss_. This element should be used as the starting point for net income in the cash flow statement when _ProfitLoss_ and _NetIncomeLoss_ have the same value.

#### Calculation Weights in Reconciliation of Operating Cash flows

It is important to define the correct calculation weights when reconciling net income to net cash provided (used) by operating activities under the indirect cash flow method. These reconciling items require that elements be removed from or added back to net income, such as the loss on sale of marketable securities or depreciation. Adding back depreciation to net income requires the addition of a debit element (such as depreciation) to a credit element (net income), which is not permitted by the XBRL calculation weight rules.

Net Income is represented in the US GAAP taxonomy as a credit concept, however it is used in the cash flow statement to estimate the operational cash flow, which is represented as a debit if the cash flow is positive. For this reason, the elements that represent the aggregated operational cash flows do not have a balance type. Given that Net Income (Loss) is a credit and Net Cash Provided by (Used in) Operating Activities is a natural debit the two items could not be added if a balance type was included on the total. Removing the balance attribute from the operational cash flow elements was implemented in the taxonomy so that the indirect cash flow could take advantage of calculation checking by XBRL processors. However it does have the disadvantage that other items rolling up into calculation of Net Cash Provided by (Used in) Operating Activities cannot be checked to determine if correct calculation weights are used.

In the cash flow statement, a number of items will roll up into Net Cash Provided by (Used in) Operating Activities. Without the balance attribute, the calculation weights are not checked. This means that filers are not restricted on the weight they use and no XBRL specification error will result. Historically, a large number of companies have used an incorrect weight and as a result, the element being added into Net Cash Provided by (Used in) Operating Activities has an incorrect sign (i.e. Is negative when it should be positive).

For example, if a company is adding Gain Loss on Sales of Loans Net into "Net Cash Provided by (Used in) Operating Activities", the gain is a credit item and thus all gain amounts should be entered as a positive amount and losses as a negative amount in the instance document. Because this is a reversal to net income of the non cash amount, the company should deduct any gain from net income, or add back any loss into net income to get a representation of the cash portion of net income. If the company used a positive weight, to make the calculation work, they would need to reverse the sign on the element (i.e. the gain is entered as a negative). In this manner the calculation works and the totals are accurate. Unfortunately, the filer has incorrectly entered the gain as a negative when a gain for this element should be entered as a positive. To correct the error, the filer needs to change the calculation weight to negative 1 and change the sign on the element _GainLossOnSalesOfLoansNet_ to a positive amount.

The filer should treat the element _NetCashProvidedByUsedInOperatingActivities_ as if it had a debit balance. This means any debit balance items rolling into it must be positive. In the graphic below, an example company has included _DepreciationDepletionAndAmortization_ as a debit balance item with a negative weight in the calculation. This calculation child will be flagged as an error. In the actual filing, the value of this element was entered as a negative value to make the calculation work.

**Figure 9: Example of calculation linkbase with incorrect weights**

![Screen Shot 2017-01-16 at 2.37.37 PM.png](images/cashflows10.png?raw=true)

##### Rules

Rule [DQC_0043](https://xbrl.us/dqc_0043) checks the calculation weights in the cash flow statement. This rule treats the element _NetCashProvidedByUsedInOperatingActivities_ as if it had a debit balance.

#### Calculation Linkbase in the Cash Flow Statement

All the calculations associated with the cash flow statement **MUST** be included in the role associated with the cash flow statement in the filing. The calculations for the Cash Flow Statement should not be put in a different role than the cash flow presentation tree. Any additional cash flow calculations, representing alternative calculations, should be included in a parenthetical cash flow role.

The calculation linkbase must start with a single durational element representing the increase or decrease in the cash for the period. There should not be more than one root element in the calculation that could be included in the increase or decrease in cash for the period. The following figure shows where a filer has used multiple root elements (shown as clear circles) representing the change in cash and the adjustment for non cash items. The increase decrease in cash during the period should be the only parent or root element in the calculation for the cash flow statement.

**Figure 10: Example of two Parent (root) Elements**

[![Screen Shot 2017-05-26 at 12.39.59 PM.png](images/cashflows11.png?raw=true)](https://test.xbrl.us/php/dispatch.php?Task=xbrlChildrenGraph&AccessionID=182849&Linkbase=Calculation&GroupURI=http://acornenergy.com/role/StatementsOfCashFlows&API_Key=4cd4576a-aada-4d35-9e40-dc7f0734f8d6) 

The presence of multiple parent elements means that the cash flow calculation is incomplete. The tree with the incorrect weights (above) demonstrates the use of a single parent for the calculation.

If the cash flow statement has additional calculations defined for supplemental cash flow information, these calculations should be defined in the parenthetical calculation role. For example, those companies that use the direct method should show the direct method calculation relationships in the cash flow calculation tree. The supplemental reconciliation of operating cash flow derived from net income for direct method reporting should be shown in the parenthetical cash flow calculation tree. Both calculations should **NOT** be shown in the same calculation tree, as the values will be double counted.

The reconciliation of the closing statement of cash flow balance to the amount of cash reported on the balance sheet, should be included in the calculation linkbase if a reconciliation is provided. This can be defined in the cash flow statement calculation role. A calculation can also be defined, if there is just one calculation child. This would reflect the case where the balance sheet amount is the same as the total of cash, cash equivalents, restricted cash and restricted cash equivalents.

##### Rules

Multiple duration parent (root) elements that comprise the increase or decrease in cash for the period, should not be defined as root elements in the calculation relationship for the cash flow statement. The cash flow statement should only have one calculation parent for durational concepts representing the increase or decrease in cash during the period. See Rule [DQC_0049](https://xbrl.us/dqc_0049). Other calculation root nodes can appear for the disaggregation of non cash items such as the element: _NoncashOrPartNoncashAcquisitionNetNonmonetaryAssetsAcquiredLiabilitiesAssumed1_

#### Investment Tax Credit & <u>Income Tax Credits And Adjustments</u>

The element _InvestmentTaxCredit_ and_IncomeTaxCreditsAndAdjustments_ are defined as debit items and appear in the taxonomy in the cash flow statement. These items reflect the reversal to net income for non cash items. These items should not be used on the income statement with a negative value to represent tax credits that offset tax expense. These elements should not be used on the cash flow statement for the same reason. The items are treated the same as tax expenses in the cash flow statement and could only work if entered as negative amounts. To calculate the addback of non cash tax credits, use a credit element from the income statement or tax note such as _IncomeTaxReconciliationTaxCreditsInvestment._

##### Rules

The element _InvestmentTaxCredit_ should always be positive. (See Nonneg rule [DQC_0015](https://xbrl.us/dqc_0015))

#### Increase Decrease Items in Roll Forward Used in Cashflow

Increase decrease items defined in rollforward disclosures without a balance attribute should not be used in the statement of cash flows. For example, the element _AssetRetirementObligationPeriodIncreaseDecrease_ is used for the increase decrease in asset retirement obligations (reference for the element is to Section 410 of the FASB Codification) and should not be used in the cash flow statement. Instead, the element _IncreaseDecreaseInAssetRetirementObligations_ which has a reference to the Cash Flow Statement, should be used.

When creating an extension element in the operating cash flow section of the Cash Flow Statement, the filer should ensure that all increases to cash flow are defined as debit balances and all items that are decreases to cash flow are credit balances.

##### Rules

Rule [DQC_0047](https://xbrl.us/dqc_0047) checks that calculation children of operating cash flows must have associated balance types.

### 

<div class="inset-right" style="background:#cccccc;border 1px solid #444444;float:right;margin-left:10px;padding:6px;text-align:center;font-size:small;line-height:105%;">[Return to
Table of Contents](#toc)</div>

<a name="8"></a>[**230-10-50**](https://asc.fasb.org/extlink&oid=98513485&loc=d3e4297-108586) - Interest and Income Tax Paid

In the supplemental cash flow section, the FASB Codification requires the disclosure of Interest paid net of any capitalized costs when an indirect cash flow statement is used. This represents the portion of aggregate interest paid categorized as an operating activity and is represented using the element _InterestPaidNet_. The element _InterestPaid_ includes capitalized costs reflecting both the operating and investing cash flows for the period. In XBRL filings the element _InterestPaid_ is often used in the supplemental section of the cash flow statement. This element should only be shown as a supplemental cash flow if _InterestPaidNet_is also disclosed.

When reporting income taxes paid, use the element _IncomeTaxesPaidNet_ when the amount is net of tax refunds. Use the element _IncomeTaxesPaid_ when the amount is known to be gross of tax refunds.

##### Rules

In the cash flow statement if the element _InterestPaid_ is included in supplemental cash flows, then the element _InterestPaidNet_ should also be disclosed. See Rule DQC_0065

### 

<div class="inset-right" style="background:#cccccc;border 1px solid #444444;float:right;margin-left:10px;padding:6px;text-align:center;font-size:small;line-height:105%;">[Return to
Table of Contents](#toc)</div>

<a name="9"></a>230-10-50 - Noncash Investing and Financing Activities

In some cases, companies have reported the change in liabilities attributable to capital expenditures, as detailed below. This is not a required disclosure under US GAAP and differs from capital expenditures incurred but not yet paid. Companies should not use the element _CapitalExpendituresIncurredButNotYetPaid_ for this disclosure, as this element does not represent the change in liabilities attributable to capital expenditures.

**Figure 11: Change in Liabilities Attributable to Capital Expenditures**

![](images/cashflows12.png?raw=true)

If a company does make this disclosure, then do not use the element _CapitalExpendituresIncurredButNotYetPaid__._ Instead use the extension element _ChangeInCapitalExpendituresIncurredButNotYetPaid._

**Non-Cash Acquisitions**

The following figure shows an example supplemental schedule of noncash investing and financing activities.

**Figure 12: Supplemental Schedule Noncash Investing and Financing Activities**

[![Screen Shot 2017-05-21 at 4.23.11 PM.png](images/cashflows13.png?raw=true)](https://test.xbrl.us/php/dispatch.php?Task=xbrlFactID&FactID=126580812) 

This disclosure can be presented at the bottom of the cash flow or presented in a separate note. The example above was reported in a separate note. Either way, the values should be identified using the non cash flow elements defined in the taxonomy and not the acquisition elements defined in the taxonomy.

In the figure below, the company has provided a schedule for noncash investing and financing activities at the bottom of the cash flow statement. The acquisition elements in the disclosure "Issuance of shares and assumed awards in connection with the Merger" should use the elements defined in the taxonomy related to noncash or part noncash acquisitions. In the cash flow disclosure, the element _NoncashOrPartNoncashAcquisitionNetNonmonetaryAssetsAcquiredLiabilitiesAssumed1_ should be used.

[**Figure 13: Non Cash Items where Acquisition is all Non Cash**](https://www.sec.gov/Archives/edgar/data/1140536/000114053616000074/wtw-20160930x10q.htm)

| 

[Supplemental disclosures:](https://www.sec.gov/Archives/edgar/data/1140536/000114053616000074/wtw-20160930x10q.htm)

 |
| 

[Cash paid for interest](https://www.sec.gov/Archives/edgar/data/1140536/000114053616000074/wtw-20160930x10q.htm)

 | 

[$](https://www.sec.gov/Archives/edgar/data/1140536/000114053616000074/wtw-20160930x10q.htm)

 | 

[135](https://www.sec.gov/Archives/edgar/data/1140536/000114053616000074/wtw-20160930x10q.htm)

 | 

[$](https://www.sec.gov/Archives/edgar/data/1140536/000114053616000074/wtw-20160930x10q.htm)

 | 

[123](https://www.sec.gov/Archives/edgar/data/1140536/000114053616000074/wtw-20160930x10q.htm)

 |
| 

[Cash paid for income taxes, net](https://www.sec.gov/Archives/edgar/data/1140536/000114053616000074/wtw-20160930x10q.htm)

 | 

[$](https://www.sec.gov/Archives/edgar/data/1140536/000114053616000074/wtw-20160930x10q.htm)

 | 

[139](https://www.sec.gov/Archives/edgar/data/1140536/000114053616000074/wtw-20160930x10q.htm)

 | 

[$](https://www.sec.gov/Archives/edgar/data/1140536/000114053616000074/wtw-20160930x10q.htm)

 | 

[67](https://www.sec.gov/Archives/edgar/data/1140536/000114053616000074/wtw-20160930x10q.htm)

 |
| 

[Issuance of shares and assumed awards in connection with the Merger](https://www.sec.gov/Archives/edgar/data/1140536/000114053616000074/wtw-20160930x10q.htm)

 | 

[$](https://www.sec.gov/Archives/edgar/data/1140536/000114053616000074/wtw-20160930x10q.htm)

 | 

[8,723](https://www.sec.gov/Archives/edgar/data/1140536/000114053616000074/wtw-20160930x10q.htm)

 | 

[$](https://www.sec.gov/Archives/edgar/data/1140536/000114053616000074/wtw-20160930x10q.htm)

 | 

[0](https://www.sec.gov/Archives/edgar/data/1140536/000114053616000074/wtw-20160930x10q.htm)

 |

Business acquisition line items should not be used for the cash flow disclosure. If the same amounts appear at different locations in the filing, then the non cash item should be used for the supplemental cash flow schedule and the business combination elements should be used in the acquisition note. The figure below shows the value 8,723 as the aggregate merger consideration. This is a non cash acquisition amount paid for by the issuance of shares. The element _NoncashOrPartNoncashAcquisitionNetNonmonetaryAssetsAcquiredLiabilitiesAssumed1_ should not be used. The element _BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedNet_ should be used instead, even though the values are the same.

**Figure 14: Fair Values of the Identifiable Assets Acquired, and Liabilities Assumed**

[![Screen Shot 2017-01-16 at 7.34.08 PM.png](images/cashflows14.png?raw=true)](http://test.xbrl.us/php/dispatch.php?Task=xbrlFactID&FactID=137375182)

If the filer breaks down the non cash amount into multiple acquisitions, the Business acquisition axis should be used, rather than the axis _NoncashOrPartNoncashAcquisitionsByUniqueDescriptionAxis_ when the business acquisition axis is used in the notes to the filing.

If the filer does a number of immaterial acquisitions during the period and the value of these acquisitions represents all acquisitions for the period, then the member _SeriesOfIndividuallyImmaterialBusinessAcquisitionsMember_ should not be associated with this value. This member should only be used when distinguishing material acquisitions from immaterial acquisitions.

### 

<div class="inset-right" style="background:#cccccc;border 1px solid #444444;float:right;margin-left:10px;padding:6px;text-align:center;font-size:small;line-height:105%;">[Return to
Table of Contents](#toc)</div>

<a name="10"></a>[205-20-50](https://asc.fasb.org/link&sourceid=SL51723644-108585&objid=99402803) - Disclosures Required for a Discontinued Operation Comprising a Component or Group of Components of an Entity

**Discontinued Operations**

There are various ways that filers represent discontinued operations in the cash flow statement. This impacts the way that discontinued operations is presented, and can mean the selection of different elements in the cash flow statement. Unlike the income statement, the cash flow items are not necessarily net of the portion attributable to discontinued operations. An expense on the income statement is expected to be net of the portion attributable to discontinued operations. Companies have a number of different ways to show the impact of discontinued operations on the cash flow statement. These are as follows:

*   Discontinued Amounts are included in Cash Flow line items

· Discontinued Operations are disclosed with separate discontinued Line items

· Discontinued Operations are summarized at the end of the Operating, Investing and Financing Sections

*   Discontinued Operations are summarized at the end of the statement

#### Discontinued Amounts are included in line items

In this case, the discontinued operations are included in each individual line item. The final values for Net Cash provided from operating activities are not distinguished between continuing and discontinued. In the cash flow statement, items used in the income statement should be used in the reconciliation to net income. The filer needs to be careful to ensure that the element for a line item in the income statement does not have a different value in the cash flow statement. This can occur when the values reported in the cash flow statement include a component related to discontinued operations. As a result the same element cannot be used in the income statement and cash flow statement. When this occurs, the filer may have to create an extension element for the operating line item in the cash flow statement that represents both continuing and discontinued operations.

**Figure 15: Continuing and Discontinued Operations**

![Screen Shot 2017-01-16 at 7.34.08 PM.png](images/cashflows15.png?raw=true)

#### Discontinued Operations are disclosed with separate discontinued Line items

In the example below, the discontinued operations are included as separate line items without an aggregate total. The discontinued operating line items are limited in the taxonomy and will generally need to be added as extensions in the company filing. The FASB has created expense line items that are specifically for discontinued operations. The items listed in the continuing operations will match the elements defined and used in the income statement. Each of these items should only represent concepts that are applicable to continuing operations.

**Figure 16: Discontinued Operations Disclosed with Separate Line Items**
![Screen Shot 2017-01-16 at 7.35.51 PM.png](images/cashflows16.png?raw=true)

#### Discontinued Operations are summarized at the end of the Operating, Investing and Financing Sections

In this example, the discontinued operations are included as summary line items. The discontinued items are broken out into the different classifications in the cash flow statement which allows continuing cash flows and discontinued cash flows to be separated between operating, financing, and investing classifications.

**Figure 17: Discontinued Operations Summarized at End of Operating, Investing and Financing**

![Screen Shot 2017-01-16 at 7.38.27 PM.png](images/cashflows17.png?raw=true)

#### Discontinued Operations are summarized at the end of the statement

In this example, the discontinued operations are included as an aggregate line item in the cash flow statement.

**Figure 18: Discontinued Operations Summarized at End of Statement**

![Screen Shot 2017-01-16 at 7.40.03 PM.png](images/cashflows18.png?raw=true)

The US GAAP taxonomy has elements that support the last three methods of disclosing the cash flow statement. However, the taxonomy does not define elements that combine continuing and discontinued items. When discontinued and continuing operating items are combined, an extension is required. An extension should be created when the amount in the cash flow statement differs from the amount recorded on the income statement. The extension should only be created for the cash flow item. An extension should never be created for the equivalent income statement item. The extension represents the aggregate of discontinued and continuing operations. The extension element should use the income statement element name as the prefix and add a suffix of "IncludingDiscontinuedOperations". This allows some consistency across filings. The following figure shows depreciation expense in the income statement with a value of 253,812 for the six months ended April 1, 2011\. This is continuing only.

**Figure 19: Income Statement with Depreciation Expense Continuing**

[![Screen Shot 2017-04-24 at 11.45.56 PM.png](images/cashflows19.png?raw=true)](https://www.sec.gov/Archives/edgar/data/7032/000144530512001595/q22012aramark.htm) 

The corresponding cash flow statement shows depreciation expense including both continuing and discontinued operations with a value of 256,706 for the 6 months ended April 1, 2011.

**Figure 20: Cash Flow Statement Showing Continuing and Discontinued Depreciation**

![Screen Shot 2017-04-24 at 11.48.51 PM.png](images/cashflows20.png?raw=true)

When adding the extension element, a calculation anchor should be added that relates the extension element to the income statement element. So the element_DepreciationAndAmortizationContinuingAndDiscontinuedOperations_ for example, would be a calculation parent of depreciation in the income statement. In a number of filings after the discontinued operation was no longer reported, the extension elements continued to be used, even though there was no discontinued operations reported by the entity. In these cases, the value on the income statement and cash flow statement is the same. When this occurs, the use of the extension item should be discontinued.

In the second case, the individual line items should be used from the taxonomy where they exist, such as _DepreciationAndAmortizationDiscontinuedOperations_. If there is no line item in the taxonomy for the discontinued adjustment to net income, then an extension should be created based off the continuing line item with the suffix "DiscontinuedOperations". In addition, an anchor should be added that relates the extension element to the income statement element. So the element _DepreciationAndAmortizationDiscontinuedOperations,_ for example, would be a calculation child of _DiscontinuedOperationIncomeLossFromDiscontinuedOperationBeforeIncomeTax_ _._

#### Aggregate movement in Cash flows

In reporting the movement in cash flows for the period, many companies have used the element Net Cash Provided by (Used in) Operating Activities, Continuing Operations _NetCashProvidedByUsedInOperatingActivitiesContinuingOperations_ to represent all cash flows from operations because they have no discontinued operations and the values reported of Net Cash Provided by (Used in) Operating Activities, Continuing Operations would be the same as "Net Cash Provided by (Used in) Operating Activities".

When companies have no discontinued operations, they should use the element _NetCashProvidedByUsedInOperatingActivities_ in the cash flow statement. If companies separately report discontinued operations, they should use the element _NetCashProvidedByUsedInOperatingActivitiesContinuingOperations_ in the cash flow statement. (Note that this reasoning also applies to financing and investing activities). Cash flow from continuing operations should be used when discontinued and continuing operations are segregated. In those cases where the cash flow statement reports only continuing operations, and discontinued operations is reported in the footnotes, the element _NetCashProvidedByUsedInOperatingActivitiesContinuingOperations_ should still be used.

The following example shows where the company has separated the cash flow from continuing and discontinued operations for the aggregate change in cash. In this case, the company would use the elements_NetCashProvidedByUsedInContinuingOperations_ and _NetCashProvidedByUsedInDiscontinuedOperations_. Note that these elements do not include the effect of changes in the exchange rate.

**Figure 21: Net Cash provided from Continuing and Discontinued Operations**

[**![Screen Shot 2017-05-11 at 6.09.07 PM.png](images/cashflows08.png?raw=true) **](https://www.sec.gov/Archives/edgar/data/1111711/000111171117000037/ni-20161231x10ka.htm) 

### 

<div class="inset-right" style="background:#cccccc;border 1px solid #444444;float:right;margin-left:10px;padding:6px;text-align:center;font-size:small;line-height:105%;">[Return to
Table of Contents](#toc)</div>

<a name="11"></a>Dimensions used on the Cash Flow Statement

Dimensions will generally not be required on the cash flow statement. However, there are some cases where dimensions may be used.

Dimensions can be used when they apply to all values reported in the cash flow statement, for example, if a company reports cash flows for separate legal entities. Filers should be careful however, not to add dimension members for values that should be reported as the default. For example, when reporting the successor and predecessor entities for the cash flow statement, the successor member should not be used on the cash flow statement. The member element _SuccessorMember_ represents the default and values associated with Successor as a column header in the financial statements should be reported as the default value.

The second case where dimensions should be used, is when a line item from the taxonomy is disaggregated into company-specific items and the basis for the disaggregation is also represented with an axis and matching specific members in another part of the filing.

The following cash flow disclosure detailing financing activities shows where either extension line items or dimensions would be required to disaggregate long-term debt payments and proceeds across individual debt issues of the company.

Dimensions should be used if these individual debt issues have been defined as extension members in a note to the financial statements. If ABL Line of Credit, Term B-2, Term B-4 and B-3 Loans have been defined as members on the Debt Instrument Axis (_DebtInstrumentAxis_) in the long term debt note, then a dimension should be used. Each of these specific debt issue cash flows would be created as using either _ProceedsFromLongTermDebt_ or _RepaymentsOfLongTermDebt_ associated with each of the individual members on the Debt Instrument Axis. Each of these elements would appear in the cash flow calculation tree of the company's filing. When a dimension is used on the cash flow statement, the axis and members used with the statement are expected to aggregate to the total of the line item with no dimensions. A user of the data should be able to identify the axis and members, and aggregate the values associated with a given line item and members on an axis and get the correct total for that line item. This means any dimension used in a group associated with the cash flow statement must have all the component members to create a valid total. This is referred to as a well behaved dimension (WBD).

**Figure 22: Extension Elements for Specific Debt Issues**

![Screen Shot 2017-04-07 at 10.48.35 AM.png](images/cashflows21.png?raw=true)

Dimensions can also be used when reporting non cash activities, such as details of specific acquisitions.

The operating activities axis, with the element _StatementOperatingActivitiesSegmentAxis,_ **MUST** not be used to separate continuing and discontinuing operations on the cash flow statement.

### 

<div class="inset-right" style="background:#cccccc;border 1px solid #444444;float:right;margin-left:10px;padding:6px;text-align:center;font-size:small;line-height:105%;">[Return to
Table of Contents](#toc)</div>

<a name="12"></a>830-230-45 Foreign Currency Matters

#### Change in Cash Excluding Impact of Foreign Exchange

In a number of cases, companies report an increase decrease in the cash balance that excludes the impact of the foreign exchange. However, a number of companies have used the element _CashAndCashEquivalentsPeriodIncreaseDecrease_ to represent this change. The element _CashAndCashEquivalentsPeriodIncreaseDecreaseExcludingExchangeRateEffect_ (Prior to adoption of ASU-2016-18)or [_CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsPeriodIncreaseDecreaseExcludingExchangeRateEffect_ ](https://asc.fasb.org/xbrllinks&trid=2134478#SL215053)(After adoption of ASU-2016-18)should be used when the change in cash and cash equivalents excludes the exchange rate impact. The first line in the figure below would use the excluding exchange rate element.

**Figure 23: Change in Cash Excluding Exchange Rate Effect**

[![Screen Shot 2017-05-21 at 1.40.10 PM.png](images/cashflows22.png?raw=true)](https://www.sec.gov/Archives/edgar/data/733269/000073326915000041/f10q.htm#1) 

For the cash flow statement roll-forward, if the exchange rate translation element is disclosed but is not included in the calculation of the increase or decrease of cash, the element _CashAndCashEquivalentsPeriodIncreaseDecreaseExcludingExchangeRateEffect_ (Prior to adoption of ASU-2016-18)or [_CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsPeriodIncreaseDecreaseExcludingExchangeRateEffect_ ](https://asc.fasb.org/xbrllinks&trid=2134478#SL215053)(After adoption of ASU-2016-18) should also be used. See the figure below:

**Figure No subtotal presented that includes the effect of the exchange rate**

![Screen Shot 2017-04-19 at 2.02.40 PM.png](images/cashflows23.png?raw=true)

If a foreign exchange translation is not disclosed, then the element _CashAndCashEquivalentsPeriodIncreaseDecrease_ (Prior to adoption of ASU-2016-18)or[_CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsPeriodIncreaseDecreaseIncludingExchangeRateEffect_ ](https://asc.fasb.org/xbrllinks&trid=2134478#SL215055)should be used.

If the exchange rate translation element is disclosed and is included in the change in cash, the element _CashAndCashEquivalentsPeriodIncreaseDecrease_ (Prior to adoption of ASU-2016-18 only)or[_CashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsPeriodIncreaseDecreaseIncludingExchangeRateEffect_ ](https://asc.fasb.org/xbrllinks&trid=2134478#SL215055)should be used.

#### Element Selection for Impact of Foreign Exchange

Prior to the adoption of ASU-2016-18, the element _EffectOfExchangeRateOnCashAndCashEquivalents_ should be used to show the impact of exchange rate changes on cash and cash equivalents. This element includes both continuing and discontinued operations. If the company splits up the impact of exchange rates between continuing and discontinued, then the following elements should be used to disaggregate the total:

*   _EffectOfExchangeRateOnCashAndCashEquivalentsContinuingOperations_
*   _EffectOfExchangeRateOnCashAndCashEquivalentsDiscontinuedOperations_

After the adoption of ASU-2016-18, the element _EffectOfExchangeRateOnCashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsIncludingDisposalGroupAndDiscontinuedOperations_ should be used to show the impact of exchange rate changes on cash, cash equivalents and restricted cash. This element includes both continuing and discontinued operations. If the company splits up the impact of exchange rates between continuing and discontinued then the following elements should be used to disaggregate the total:

*   EffectOfExchangeRateOnCashCashEquivalentsRestrictedCashAndRestrictedCashEquivalents
*   EffectOfExchangeRateOnCashCashEquivalentsRestrictedCashAndRestrictedCashEquivalentsDisposalGroupIncludingDiscontinuedOperations

**Catch all Elements**

There are a number of elements in the taxonomy that are generically defined in terms of their calculation children. The components of these elements are not standardized and can differ from filer to filer. For example, SGA in the taxonomy has a number of components that can be included as children of this element in one filing and siblings in another. These are referred to as "catch all" elements and, on the cash flow statement, include the following:

*   Depreciation, Depletion and Amortization

If a component of this element in the US GAAP taxonomy is included as a sibling in the filing, there is no requirement to create an extension element for Depreciation, Depletion and Amortization. This is particularly common for the disclosure of Amortization of Debt Issuance Costs which is commonly reported as a sibling to Depreciation, Depletion and Amortization.

* * *

<div id="ftn1">

[[1]](#_ftnref1) The Entity Specific Disclosure Task Force of XBRL International is preparing best practices and recommendations on how to link extensions to standard elements in a base taxonomy. The DQC plans to leverage the work of that task force and will update this guidance with appropriate recommendations for the mechanism to link extensions.

</div>

### 

<div class="inset-right" style="background:#cccccc;border 1px solid #444444;float:right;margin-left:10px;padding:6px;text-align:center;font-size:small;line-height:105%;">[Return to
Table of Contents](#toc)</div>