This update is available for public comment until December 6, 2016 - [https://xbrl.us/data-rule/guidance-tagging-v2](https://xbrl.us/data-rule/guidance-tagging-v2)
# Guidance Update - Tagging Axis and Members Using the US GAAP Taxonomy

The XBRL US Data Quality Committee (DQC) has developed prescriptive guidance for issuers submitting XBRL files that contain financial statements to the Securities Exchange Commission (SEC). This guidance provides for uniform, consistent tagging of financial data using the US GAAP taxonomy to improve the usability of such data. The DQC has also developed rules that test XBRL files for conformity with the guidance. The additional guidance included in this document is being exposed for public review. Once approved for release, the Committee’s [Guidance on Tagging Axes and Members](/data-rule/guid-tag) will be updated to include this information.

## Appropriate Modeling of Axis and Members

In its Staff Observations, the SEC suggested filers utilize the pre-defined table structures included in the US GAAP taxonomy. Certain axes in the US GAAP taxonomy should only have certain members, otherwise consumption of the data is adversely impacted because the resulting axis and member combinations are nonsensical, e.g., reporting a type of currency as a member on a debt instrument axis. The following guidance provides limitations on the use of certain axis and member combinations that should be adhered to when tagging financial information using the US GAAP Taxonomy.

### Statement Equity Components [Axis] <span style="font-size: small; font-style: italic;">(StatementEquityComponentsAxis)</span>

This axis is used to disaggregate shareholders equity into all its possible components. This axis should only include sub categories of shareholders equity and partnership capital on this axis. This axis can only have those members identified as components of stockholder equity in the US GAAP taxonomy, the additional members identified below and extension members which may be specific to a given company that are not included in the taxonomy. ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).75)

| Element Name | Label | Namespace | Documentation |
| WarrantsNotSettleableInCashMember | Warrants Not Settleable in Cash [Member] | us-gaap | Warrants not settleable in cash that are classified in shareholders' equity. |
| ContingentConsiderationClassifiedAsEquityMember | Contingent Consideration Classified as Equity [Member] | us-gaap | Contingent consideration in a business combination that is classified in shareholders' equity. |
| EquityIssuedInBusinessCombinationMember | Equity Issued in Business Combination [Member] | us-gaap | Equity issued by an entity in a business combination that is classified in shareholders' equity. |
| TrustForBenefitOfEmployeesMember | Trust for Benefit of Employees [Member] | us-gaap | Trust created by the entity that exists for the benefit of its employees, such as pension and profit-sharing trusts that are managed by or under the trusteeship of the entity's management. |

### Statement Scenario [Axis] <span style="font-size: small; font-style: italic;">(StatementScenarioAxis)</span>

This axis is used to indicate different scenarios that can impact a company. This axis can only have those members defined on the Statement Scenario axis in the US GAAP taxonomy and extension members. No other members from the US-GAAP taxonomy should be used on this axis. ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).76)

### Range [Axis] <span style="font-size: small; font-style: italic;">(RangeAxis)</span>

The range axis was introduced by the FASB to eliminate the need to define multiple line item elements for every concept that has a maximum and a minimum value in a range. Rather than define separate XBRL line items to represent the minimum and maximum values of a concept, a range axis was created. This has the advantage of reducing the number of line items required in the taxonomy and providing the filer with greater flexibility to report ranges of values. The range axis; however, is unlike other axes. Normally an axis is used to subdivide an aggregate population of transactions into smaller groups based on an attribute of the population. For example, Revenues can be subdivided into US and International Revenues based on the attribute of where the goods were physically sold. These two components will add to the total as they still include all sale transactions. The range axis is different, it is used either to identify the maximum amount or minimum amount of a given population or to define the upper or lower limit or a range of possible values. The range axis also contains a third member called WeightedAverageMember, this member is used to report the weighted average of a population. The following general principles should be followed when using the Range Axis

*   Do not use the range axis where an element exists that is already explicitly defined as the minimum and maximum. For example the _elementShareBasedCompensationSharesAuthorizedUnderStockOptionPlansExercisePriceRangeLowerRangeLimit_ should not use the range axis with the minimum member.
*   Do not add extension elements to the range axis, such as median, average mode etc. These change the meaning of the element and should not be used with the range axis. In these cases the company should define a new element.
*   Do not add members that represent ranges of values such as maturing in a year, maturing in 2 years, maturing in 3 years etc.
*   If element implicitly includes weighted average then do not add the weighted average member.
*   Do not use the range axis for earliest and latest dates. <sup>[1](#ftn1)</sup>

See [DQC_0001 List of Axes Update V3](/data-rule/dqc_0001-la-v3/)

* * *

<div id="ftn1"><a title="" name="ftnref1"></a><sup>[1]</sup> The FASB has issued a FAQ on this which states the following:  
**Is it appropriate to use RangeAxis for dates?**  
TheRangeAxis can be used in instances in which the value is useful life. For example, it is common to disclose the useful life of property, plant, and equipment as a minimum and maximum life, and that would be an acceptable use ofRangeAxis.It would not be appropriate to use RangeAxisfor earliest and latest because those terms are not synonymous with minimum and maximum. [Revised 2014-03]</div>