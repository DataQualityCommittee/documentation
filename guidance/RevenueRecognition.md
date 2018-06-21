## XBRL US Center for Data Quality Committee Guidance
# Revenue Recognition Guidance
### Draft for Committee Review
### June 2018

This guidance is a supplement to the FASB implementation guide and is designed to address problems and inconsistencies that have been identified when companies adopt the revenue recognition standard. 

## Financial Statement Disclosures

### Comparative Line Items on the Face Financials
When reporting income statement and balance sheet items, the ASC 606 revenue recognition elements should be used for these disclosures for all periods reported. Do not use the new elements for the years of adoption and old elements for prior years. If the company has restated prior periods or has used the modified retrospective approach, the same elements should be used for all periods reported. There have been some concerns raised that these numbers would not be comparable. It is important to note that the details of the difference between different revenue recognition approaches is disclosed in the footnotes to the financial statements. 

The values on the income statement and balance sheet should not use the member CalculatedUnderRevenueGuidanceInEffectBeforeTopic606Member. This element would only be used on the income statement if a comparison of adjustment also appeared in the notes for prior years. Filers should use this member for the current period and not for periods prior to adoption. Excluding this member from prior periods is for ease of consumption and to minimize the impact of multi dimensional values used to represent fact values. 

### Using the Revenues Element on the Income Statement
The Revenues line item element can be used on the income statement, this element can be used after ASC 606 has been adopted by filers.  Revenues includes income recognized under ASC 606 and income not recognized under ASC 606.  It is preferable to use use the more specific revenue from contracts with customers when all income is ASC 606 related revenue.

In the following example the company breaks down revenue into the following categories which aggregates to total revenue.

    Medical Revenue (All ASC 606)
    Non-Medical Revenue  (All ASC 606)
    Other Revenue (Partly ASC 606)
    Total Revenue

The element representing "Other Revenue" includes non ASC 606 revenue. A filer in this situation would use the product or services axis to disaggregate the Revenues line item.  The element for Revenue from Contracts with Customers would not be used. The element for Revenue from Contracts with Customers however would have to appear in the notes to the financials.

In the situation described below the element for Revenue from Contracts with Customers can be used for the aggregate revenue.

    Medical Revenue (All 606)
    Non-Medical Revenue (All 606)
    Other Revenue (All 606)
    Total Revenue (All 606)

In this case the filer would use the element for Revenue from Contracts with Customers with the product or service axis and the members for the 3 categories of Revenue. If all revenue is ASC 606 revenue (even without a breakdown) then the element Revenue WIth Contract with Customers is used.

### Sales Taxes
The ability to distinguish if revenues includes sales tax is an important variable for investors. High sales taxes on certain products if not excluded from the calculation of margins can produce misleading results. The US GAAP taxonomy includes elements for Revenues from  Contract with Customers including and excluding sales taxes.

If a company has no sales tax, it is recommended that the company use the revenue from contract with customers element that excludes sales taxes. 

### Revenue for Banks
Typically banks reporting of revenues is broken down between interest based revenue and non-interest revenue.  This means the aggregate revenues cannot be cleanly disaggregated into revenue from contracts with customers.

The following example highlights this complexity:
![Example 1](images/revrec01.png?raw=true)

The non interest income is comprised of income that is ASC 606 revenue and revenue that is not.  To report the net interest related revenue the line items from the taxonomy should be used. For the breakdown of non interest revenue the aggregate total is represented with the element NoninterestIncome.

The aggregate total of non interest income should use line items on the face financial statements where contracts with customers is not specifically disclosed on the face. In the above example, the items highlighted in green do not have an aggregate total reported on the face of the financials for revenue from contracts with customers. In this case the single line items should be used and the element for Revenues for Contracts with Customers should be used in the notes.

Total revenues for the bank including non interest income should use the Revenues element on the income statement.

In some cases companies report non interest income that is out-of-scope of Topic 606.  In those cases, companies need to create an extension element to represent this amount. 

## Revenue Remaining Performance Obligation
Companies are now required to report their remaining performance obligation and the periods when this revenue will be recognized.  The FASB has set up a new axis to report this information. When reporting the obligation the following should be done.

1.  For every fact value reported for an obligation, a corresponding value needs to be tagged for the element RevenueRemainingPerformanceObligationExpectedTimingOfSatisfactionPeriod.
1.  When reporting the element RevenueRemainingPerformanceObligation in the default, the company filing can import the standard FASB template located at: [http://xbrl.fasb.org/us-gaap/2018/dis/us-gaap-dis-rcctmp03-def-2018-01-31.xml](http://xbrl.fasb.org/us-gaap/2018/dis/us-gaap-dis-rcctmp03-def-2018-01-31.xml) or create an equivalent in their filing.
1.  If reporting a thereafter amount, the value of the element RevenueRemainingPerformanceObligationExpectedTimingOfSatisfactionPeriod must be reported with a nil value.

## Selection of Elements
If an element used in a filing that is contained in section 606000 of the taxonomy, then no elements from section 440000 can be used in the filing, except for the following exceptions:

1.  ExciseAndSalesTaxes
1.  RevenueRecognitionPolicyTextBlock
1.  CostOfSalesPolicyTextBlock