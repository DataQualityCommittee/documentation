## XBRL US Center for Data Quality Committee Guidance
# Revenue Guidance
### Approved October 2018

This DQC guidance is designed to address problems and inconsistencies that have been identified when companies adopt the revenue standard under Accounting Standards Codification® (ASC) Topic 606, including tagging of disclosures that are not required. It is intended to be used in conjunction with FASB’s Taxonomy Implementation Guide for "Revenue from Contracts with Customers".


## Financial Statement Reporting

### Comparative Line Items on the Face Financials
When reporting income statement and balance sheet items, the ASC 606 revenue elements should be used for all periods reported. Do not use the new elements for the years of adoption and old elements for prior years. If the company has used the modified retrospective approach, the same elements should be used for all periods reported. There have been some concerns raised that these numbers would not be comparable. It is important to note that the details of the difference between different revenue approaches is disclosed in the notes to the financial statements. 

The values on the income statement and balance sheet should not use the member CalculatedUnderRevenueGuidanceInEffectBeforeTopic606Member. Filers should use this member in the notes to the financial statements when they have used the modified retrospective method of adoption.

### Disaggregated Revenue
The Revenues line item element can continue to be used on the income statement for filers who have reported revenue under ASC 606 and other standards. It is preferable to use the more specific revenue from contracts with customers when all income is ASC 606 related revenue.

**Scenario 1:**

In the situation described below the element for Revenue from Contract with Customer (either including or excluding assessed tax) can be used for the aggregate revenue.

	Product Revenue (All 606)		100
	Service Revenue (All 606)		 50
	XYZ Revenue (All 606)			 30
	Total Revenue (All 606)			180

In this case the filer would use the element for Revenue from Contract with Customer with the ProductOrServiceAxis and the members for the three categories of revenue on the Income Statement. If all revenue is ASC 606 revenue (even without a breakdown) then the element Revenue from Contract with Customer is used.

Note Disclosure: 

	Product Revenue (All 606)
		US				 90
		International			 10
		Total Product Revenue		100
	Service Revenue (All 606)
		US				 30
		International			 20
	Total Service Revenue			 50
	XYZ Revenue (All 606)
		US				 15
		International			 15
		Total XYZ Revenue		 30
	Total Revenue (All 606)			180

In the note disclosure for Disaggregated Revenue, the filer would use the element for Revenue from Contract with Customer with the ProductOrServiceAxis (with members for these three categories of revenue), together with additional dimensions (such as StatementGeographicalAxis) to further disaggregate revenues, if additional disaggregation is disclosed.

**Scenario 2:**

In the following example the company breaks down revenue into the following categories which aggregate to total revenue.

	Product Revenue (All ASC 606)	100
	Service Revenue (All ASC 606)	 50
	XYZ Revenue (All non ASC 606)	 30
	Total Revenue			180

In this example the non-ASC 606 revenue is one of the following:

![Example 1](images/revrec00.png?raw=true)

The filer would use Revenue from Contract with Customer and ProductOrServiceAxis with its members. To disaggregate the two ASC 606 revenues, use standard element(s) for leases or insurance premiums to tag non-ASC 606 revenue, then use Revenues for the total revenue on the income statement.

Note Disclosure: 

	Product Revenue (All 606)
		US					 90
		International				 10
		Total Product Revenue			100
	Service Revenue (All 606)
		US					 30
		International				 20
		Total Service Revenue			 50
	Operating Lease Revenue (All non 606)
		US					 15
		International				 15
		Total Operating Lease Revenue	 	 30
	Total Revenue 					180

In the note disclosure for Disaggregated Revenue, the filer would use the element for Revenue from Contract with Customer with the ProductOrServiceAxis (with ProductMember and ServiceMember), together with additional dimensions (such as StatementGeographicalAxis) to further disaggregate ASC 606 revenues, if additional disaggregation is disclosed. 

If the non-ASC 606 revenue is also included in the note disclosure for Disaggregated Revenue, the filer would use the same line item as the income statement for the non-ASC 606 revenue, together with additional dimensions (such as StatementGeographicalAxis) to further disaggregate non-ASC 606 revenues, if additional disaggregation is disclosed. 

The Revenues element would be used for the total revenue (ASC 606 and non-ASC 606 revenue). 

**Scenario 3:**

In the following example, the company breaks down revenue into the following categories which aggregate to total revenue.

	Product Revenue (All ASC 606)	100
	Service Revenue (All ASC 606)	 50
	XYZ Revenue (Partly ASC 606)	 30
	Total Revenue			180

The element representing "XYZ Revenue" includes both ASC 606 and non-ASC 606 revenues. A filer in this situation would use the ProductOrServiceAxis to disaggregate the Revenues line item on the income statement (The element for Revenue from Contract with Customer would not be used). The element for Revenue from Contract with Customer however would have to appear in the notes to the financials.

Note Disclosure: 

	Revenue from Contracts with Customers (All ASC 606)
		US							130
		International						 30
		Total Revenue from Contracts with Customers		160
	Non-ASC 606 Revenue (non-ASC 606)
		US							 10
		International						 10
		Total Non-ASC 606 Revenue				 20
	Total Revenue 							180

In this scenario, the filer would use Revenue from Contracts with Customers with the StatementGeographicalAxis to disaggregate revenue from contracts with customers. 

The filer would use an extension element: Revenue not from Contract with Customer<sup>[1](#1)</sup> (RevenueNotFromContractWithCustomer) with the StatementGeographicalAxis to disaggregate revenues not from contract with customers. 

The Revenues element would be used for the total revenue (ASC 606 and non-ASC 606 revenue).  

**Scenario 4:**
#### Revenue for Financial Institutions
Typically, a financial institution's reporting of revenues is broken down between interest-based revenue and non-interest revenue.  This means the aggregate revenues cannot be cleanly disaggregated into revenue from contracts with customers.

The following example highlights this complexity:
![Example 2](images/revrec01.png?raw=true)

The non-interest income is comprised of income that is ASC 606 revenue and non-606 revenue.  To report the net interest-related revenue the line items from the Taxonomy should be used. 

The aggregate total of non-interest income should use line item (NoninterestIncome) on the face financial statements. In the above example, the specific line items (standard elements or extensions) should be used for the items within the non-interest income section on the income statement. 

Total revenues for the bank including non-interest income should use the Revenues element on the income statement.

Note Disclosure:  
![Note Disclosure 1](images/revrec02.png?raw=true)

In this scenario, the filer would use InterestIncomeExpenseNet  to tag the net interest income. For non-interest income line items, the filer would use the revenue line items used on the income statement.  

To identify which components, represent Revenue from Contract with Customer and Revenues Not from Contract with Customers, the filer should also provide two calculation relationships:
1.  Standard element Revenue from Contract with Customer with calculation children of all revenue from contract with customer (items underlined in 'green')
1.  Extension element Revenue Not from Contract with Customer with calculation children of all revenue not from contract with customer (items underlined in 'red')

The calculation children appear in both the calculation link and presentation link, but the calculation parent is in the calculation link only (not in the presentation link as there is no value entered).

Total noninterest income is tagged using the same element on the income statement (NoninterestIncome).
 
Total net revenue is tagged using the same element on the income statement (Revenues).

### Assessed Taxes<sup>[2](#2)</sup> 
The ability to distinguish if revenues includes assessed taxes is an important variable for investors. High sales taxes on certain products, if not excluded from the calculation of margins, can produce misleading results. The US GAAP Financial Reporting Taxonomy includes elements for Revenues from Contract with Customers including and excluding assessed taxes.

If a company has no assessed taxes, it is recommended that the company use the revenue from contracts with customers element that excludes assessed taxes.

## Revenue Remaining Performance Obligation
Companies are now required to report their remaining performance obligation and the periods when this revenue will be recognized.  The Taxonomy has a new axis to report this information. When reporting the obligation, the following should be done:

1.  For every fact value reported for an obligation, a corresponding value needs to be tagged for the element `RevenueRemainingPerformanceObligationExpectedTimingOfSatisfactionPeriod1`.
1.  When reporting the element `RevenueRemainingPerformanceObligation` in the default, the company filing can import the standard FASB template located at: [http://xbrl.fasb.org/us-gaap/2018/dis/us-gaap-dis-rcctmp03-def-2018-01-31.xml](http://xbrl.fasb.org/us-gaap/2018/dis/us-gaap-dis-rcctmp03-def-2018-01-31.xml) or create an equivalent in their filing.
1.  If reporting a thereafter amount, the value of the element RevenueRemainingPerformanceObligationExpectedTimingOfSatisfactionPeriod1 must be reported with a nil value.

## Selection of Elements
If an element used in a filing is contained in section 606000 of the Taxonomy, then no elements from section 440000 can be used in the filing, except for the following exceptions:

1.  ExciseAndSalesTaxes (Included in 440000 calculation linkbase of 2017 taxonomy)
1.  RevenueRecognitionPolicyTextBlock (Moved out of 440000 in 2019 Taxonomy)
1.  CostOfSalesPolicyTextBlock (Moved out of 440000 in 2019 Taxonomy)

## Sub totals by Product
In some cases, companies break down revenues by sub categories of product and include a total for the sub category. In the example below, the company has created a sub category for sales of vehicles and services.
![Example 3](images/revrec03.png?raw=true)

In this example the company has disclosed their revenue from contracts with customers by product line. The company has created subtotals for revenues from vehicles and services of 145,407 for the consolidated total of revenue from contracts with customers. Each of the product categories defined on the left (such as Used Vehicles) will appear as members on the ProductOrServiceAxis. When this axis is used the member defined for Revenue from vehicles must be a parent member of the following members:
*  Vehicles, parts and accessories
*  Used Vehicles

The member used for Revenue from services must be a parent member of the following members:
*  Extended service contract
*  Other 
This structure indicates that these revenue sources are a component of vehicles and services and prevents double counting. The values for revenues from vehicles and services would be tagged with no members and the element for revenue from contracts with customers. The leasing, financing and Insurance income would be non 606 income.

## Revenue Before Topic 606

The CalculatedUnderRevenueGuidanceInEffectBeforeTopic606Member is only intended to be used by filers who have adopted the revenue standard using the modified retrospective approach.  Typically, it will be used in a disclosure that shows the current period values as measured under previous guidance to the revenues measured under ASC 606.  

Example:  
![Example 4](images/revrec04.png?raw=true)

In the example above the member is used on the third column called "Proforma balance without the adoption of ASC 606". The second column would use the member "DifferenceBetweenRevenueGuidanceInEffectBeforeAndAfterTopic606Member".

<hr>

<a name="1"></a>1.  Use the US GAAP Taxonomy name for this element defined in the  2019 Taxonomy. This element was not included in the 2018 taxonomy.  
<a name="2"></a>2.  Assessed by a governmental authority that are both imposed on and concurrent with a specific revenue-producing transaction and collected by the entity from a customer (for example, sales, use, value added, and some excise taxes).
