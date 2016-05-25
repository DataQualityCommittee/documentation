# Guidance on Tagging Axis and Members Using the US GAAP Taxonomy<span style="font-size:small">  
XBRL US Data Quality Committee</span>

The XBRL US Data Quality Committee (DQC) has developed prescriptive guidance for issuers submitting XBRL files that contain financial statements to the Securities Exchange Commission (SEC).  This guidance provides for uniform, consistent tagging of financial data using the US GAAP taxonomy to improve the usability of such data.  The DQC has also developed rules that test XBRL files for conformity with the guidance.  The guidance in this document provides links and references, where applicable, to the associated rules developed by the DQC.  It is expected that issuers will comply with the guidance presented in this document when tagging their financial statements for submission to the SEC.

## Appropriate Modeling of Axis and Members

In its Staff Observations[<sup>[1]</sup>](#ftn1), the SEC suggested filers utilize the pre-defined table structures included in the US GAAP taxonomy. Certain axes in the US GAAP taxonomy should only have certain members, otherwise consumption of the data is adversely impacted because the resulting axis and member combinations are nonsensical, e.g., reporting a type of currency as a member on a debt instrument axis.  The following guidance provides limitations on the use of certain axis and member combinations that should be adhered to when tagging financial information using the US GAAP Taxonomy.

### Default Dimension

The default dimension should not be changed from that defined in the US GAAP taxonomy. Users of XBRL data expect that the default member of an axis will be the same across filings.  For example, if a company reports a value of Revenues with no dimensions it is assumed that this represents revenues of the consolidated entity.  However, if the company changed the default member of the Legal Entity axis to the parent company member then every value without a dimension would represent the parent company and not the revenue of the consolidated entity.  (DQC_0041.73).

### Fair Value, Hierarchy [Axis] <span style="font-size:small">(_FairValueByFairValueHierarchyLevelAxis)_</span>

This axis is used to categorize the valuation techniques used to measure the fair value of an asset or liability. It is expected that only three members from the US GAAP taxonomy will be used on this axis representing the three separate levels defined by the FASB (i.e., level 1, level 2 and level 3 members defined on this axis).  Extensions on this axis are limited to those cases where the company combines multiple hierarchical levels together such as, combinations of level 1 and level 2 and combinations of level 2 and level 3\. The element names to be used for these extension members are: Fair Value Inputs Level 1 And Level 2 [Member] Fair Value Inputs Level 2 And Level 3 [Member] Do not use the Estimate of Fair Value Measurement [Member] element on this axis.  This member is often used incorrectly to represent a total for this axis. The total does not need a member associated with it on this axis. (DQC_0001.51)

### Reclassification out of Accumulated Other Comprehensive Income [Axis] <span style="font-size:small">_(ReclassificationOutOfAccumulatedOtherComprehensiveIncomeAxis)_</span>

This axis is used to indicate that an item was reclassified from accumulated other comprehensive income into income. The element Reclassification out of Accumulated Other Comprehensive Income [Member] is the only member permitted on this axis.  Do not create extensions members on this axis. (DQC_0001.52)

### Other Ownership Interests Name [Axis] <span style="font-size:small">_(OtherOwnershipInterestsByNameAxis)_</span>

This axis is used to define the specific ownership interests of the company by specific name. Given that these are specific to the reporting company, the members on this axis must be defined as extension elements. The company extension element name should match the legal name of the legal entity if it is available and should remain consistent across filing periods and should be consistent within a single filing. The label of the member can be a short name or full name. (DQC_0001.53)

### Legal Entity [Axis] <span style="font-size:small">(_LegalEntityAxis)_</span>

This axis is used to define the details of specific legal entities. Only extension members representing specific legal entities should be used on this axis in addition to members that represent classes of legal entities defined in the US GAAP taxonomy. The members in the US GAAP taxonomy that can be used on this axis include the members on the Legal Entity [Axis] and the members on the Federal Home Loan Bank Advances Branch Of FHLB Bank [Axis].  The following members are also permitted: Predecessor [Member], CoVenturer [Member], SpinOff [Member], Partnership [Member], Limited Liability Company [Member], and Trust For Benefit Of Employees [Member].  (DQC_0001.54)

### Unique Name [Axis] <span style="font-size:small">_(NoncashOrPartNoncashDivestituresByUniqueNameAxis)_</span>

This axis is used to provide divestiture information by unique name of asset or business. Given that these are specific to the reporting company, the members on this axis must be defined as extension elements.  (DQC_0001.56)

### Investment, Name [Axis] <span style="font-size:small">_(ScheduleOfEquityMethodInvestmentEquityMethodInvesteeNameAxis)_</span>

This axis is used to provide the name of each investee accounted for under the equity method of accounting. Given that these are specific to the reporting company, the members on this axis must be defined as extension elements.  In many cases, companies have incorrectly used the element Equity Method Investments[Member] in conjunction with a financial statement line item like revenues to represent summary financial information for equity method investments. This member should not be used as specific equity method line items are defined for financial statement line items. (DQC_0001.57)

### Counterparty Name [Axis] <span style="font-size:small">_(CounterpartyNameAxis)_</span>

This axis is used to provide the name of the counterparty. Given that these are specific to the reporting entity, the members on this axis should be extensions. There are a number of members defined in the US GAAP taxonomy that can also be used on this axis. The table below lists the allowable members. Some companies have used generic members defined in the taxonomy like Subsidiary Issuer [Member] or Director [Member]. These should only be used where these members are synonymous with a single entity. The Parent Company [Member] should not be used as the consolidated entity is comprised of the parent.  If a subsidiary had a transaction with the parent, the subsidiary would be the counterparty. (DCQ_0001.58)

<table>

<tbody>

<tr>

<th style="max-width:120px">**Element Name**</th>

<th style="width:75px">**Label**</th>

<th style="width:75px">**Namespace**</th>

<th>**Documentation**</th>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">AffiliatedEntityMember</td>

<td valign="top">Affiliated Entity [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">An affiliate is a party that, directly or indirectly through one or more intermediaries, controls, is controlled by, or is under common control with the entity.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">InvestorMember</td>

<td valign="top">Investor [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Business entity or individual that puts money, by purchase or expenditure, in something offering potential profitable returns, such as interest income or appreciation in value.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">VariableInterestEntityNotPrimaryBeneficiaryMember</td>

<td valign="top">Variable Interest Entity, Not Primary Beneficiary [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Variable Interest Entities (VIE) in which the entity does not have a controlling financial interest (as defined) and of which it is therefore not the primary beneficiary. VIEs of which the entity is not the primary beneficiary because it does not have the power to direct the activities of the VIE that most significantly impact the VIE's economic performance and for which it does not have the obligation to absorb losses of the VIE that could potentially be significant to the VIE or the right to receive benefits from the VIE that could potentially be significant to the VIE are not included in the consolidated financial statements of the entity.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">ChiefFinancialOfficerMember</td>

<td valign="top">Chief Financial Officer [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Senior executive officer responsible for overseeing the financial activities of the entity.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">IndividualMember</td>

<td valign="top">Individual Counterparty [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Individual person that is legally permitted to enter into a contract and be sued if that person fails to meet the obligations imposed by a contract.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">GovernmentMember</td>

<td valign="top">Government [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Organization that is the governing authority of a community.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">GuarantorSubsidiariesMember</td>

<td valign="top">Guarantor Subsidiaries [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Entity owned or controlled by another entity which has guaranteed the issue of securities by another subsidiary of the parent or has guaranteed the issue of securities by the parent.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">SubsidiaryIssuerMember</td>

<td valign="top">Subsidiary Issuer [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">A company controlled, directly or indirectly, by its parent, which has issued securities and those securities are guaranteed by its parent and another subsidiary of the parent.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">DirectorMember</td>

<td valign="top">Director [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Person serving on the board of directors (who collectively have responsibility for governing the entity).</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">ChiefExecutiveOfficerMember</td>

<td valign="top">Chief Executive Officer [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Highest ranking executive officer, who has ultimate managerial responsibility for the entity and who reports to the board of directors. In addition, the chief executive officer (CEO) may also be the chairman of the board or president.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">ChiefOperatingOfficerMember</td>

<td valign="top">Chief Operating Officer [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Senior executive officer responsible for management of day-to-day activities of the entity.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">GeneralPartnerMember</td>

<td valign="top">General Partner [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Party to a partnership business who has unlimited liability.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">CorporateJointVentureMember</td>

<td valign="top">Corporate Joint Venture [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Corporation owned and operated by a small group of ventures to accomplish a mutually beneficial venture or project.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">SubsidiaryOfCommonParentMember</td>

<td valign="top">Subsidiary of Common Parent [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Refers to an entity under the control of the same parent as another entity (that is, a sister company).</td>

</tr>

</tbody>

</table>

### Plan Name [Axis] <span style="font-size:small">_(PlanNameAxis)_</span>

This axis is used to distinguish information by the name of an equity-based compensation arrangement plan. Given that these are specific to the reporting company, the members on this axis must be defined as extension elements. Members on this axis should represent discrete plans of the company such as Stock Option Plan 2016\. (DCQ_0001.59)

### Defined Contribution Plan Name [Axis] <span style="font-size:small">_(DefinedContributionPlanNameAxis)_</span>

This axis is used to distinguish information by the name of the defined contribution plan. Given that these are specific to the reporting company, the members on this axis must be defined as extension elements. (DCQ_0001.60)

### Currency [Axis] <span style="font-size:small">_(CurrencyAxis)_</span>

This axis is used to indicate the currency that an instrument is denominated in and members are restricted to only valid currencies listed in the current taxonomy. The members on this axis should match the currency designators defined by ISO.  Extension members are only permitted in those cases where the currency has not been incorporated into the taxonomy. When creating an extension for these items, they should match the element name defined for the allowable extensions below. (DCQ_0001.62)

<table border="0" cellspacing="0" cellpadding="0">

<tbody>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">**Element Name**</td>

<td valign="top">**Label**</td>

<td valign="top">**Namespace**</td>

<td valign="top">**Documentation**</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">SICAD1Member</td>

<td valign="top">SICA D1 [Member]</td>

<td valign="top">extension</td>

<td valign="top">Venezuelan complementary currency exchange system, Sistema Complementario de Administracion de Divisas 1</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">SICAD2Member</td>

<td valign="top">SICA D2 [Member]</td>

<td valign="top">extension</td>

<td valign="top">Venezuelan complementary currency exchange system, Sistema Complementario de Administracion de Divisas 2</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">OtherCurrencyMember</td>

<td valign="top">Other [Member]</td>

<td valign="top">extension</td>

<td valign="top">Represents all other currencies not specifically defined.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">NonUSDollarMember</td>

<td valign="top">Non-U.S. Dollar [Member]</td>

<td valign="top">extension</td>

<td valign="top">Represents all other currencies that are not USD.</td>

</tr>

</tbody>

</table>

### Position [Axis] <span style="font-size:small">_(PositionAxis)_</span>

This axis is used to indicate the long or short position taken on a security. The US GAAP taxonomy includes a Long [Member] and Short [Member] that can be used on this axis. The rule also permits two extensions Net Long Positions [Member] and Net Short Positions [Member]. These two extension elementscan be used on this axis to represent the notional amounts when long and short positions are netted. The Long [Member] and Short [Member] represent positions before any netting occurs. For example, in the diagram below the company reports the notional amounts for purchases and sales and a third column of notional amounts that represent the net purchases and sales. All of the values in this table are reported using the notional line item with the various axes shown. In the final three columns, in red, are the notion values of the Long, Short and Net positions. In order to tag the column of Net Purchases and Sales, the extension members Net Long Positions [Member] and Net Short Positions [Member] are required. (DCQ_0001.63) ![DQC-guidance_image001](https://xbrl.us/wp-content/uploads/2016/05/DQC-guidance_image001.png)

### Measurement Frequency [Axis] <span style="font-size:small">_(FairValueByMeasurementFrequencyAxis)_</span>

This axisis used to indicate if a measurement is on a recurring or non recurring basis. This axis can only have these two members defined in the US GAAP taxonomy associated with it.  Extensions on this axis are not permitted. (DCQ_0001.64)

### Measurement Basis [Axis] <span style="font-size:small">_(FairValueByMeasurementBasisAxis)_</span>

This axis is used to indicate the measurement basis for a given asset or liability. This axis can only have five members that are defined in the US GAAP taxonomy associated with it.  Extensions on this axis are not permitted. (DCQ_0001.65)

### Hedging Designation [Axis] <span style="font-size:small">_(HedgingDesignationAxis)_</span>

This axis is used to indicate if a derivative is designated as a hedging instrument or if a derivative is not designated as a derivative instrument. This axis can have these two members that are defined in the US GAAP taxonomy associated with it. This axis can also have two extension members (DCQ_0001.66):

*   _NotDesignatedAsHedgingInstrumentEconomicHedgesMember_
*   _NotDesignatedAsHedgingInstrumentTradingMember_

### Products and Services [Axis] <span style="font-size:small">_(ProductOrServiceAxis)_</span>

This axisis used to distinguish the details of products or services of the reporting entity. Given that products and services are generally specific to the reporting company, the members on this axis would be predominantly defined using extension elements. In the US GAAP taxonomy, a number of generic product and service members are defined for industries where the products are highly standardized such as, insurance or where the products are commodities such as, oil. In these cases, members from the US GAAP taxonomy can be used. The list of product and service members that can be used from the US GAAP taxonomy are those included on the following axis:

*   _ProductOrServiceAxis_
*   _ReinsurancePremiumsForInsuranceCompaniesByProductSegmentAxis, ScheduleOfMalpracticeInsuranceTypeAndTierIdentifierAxis_
*   _AircraftTypeAxis_

In addition the members defined below can also be used. (DCQ_0001.69)

<table border="0" cellspacing="0" cellpadding="0">

<tbody>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">**Element Name**</td>

<td valign="top">**Label**</td>

<td valign="top">**Namespace**</td>

<td valign="top">**Documentation**</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">AuctionRateSecuritiesMember</td>

<td valign="top">Auction Rate Securities [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Debt instrument securities (for example, but not limited to, corporate or municipal bonds) that typically have long-term nominal maturities for which the interest rate is reset through an auction process.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">AutomobileLoanMember</td>

<td valign="top">Automobile Loan [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Loan to finance the purchase of a vehicle.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">CommercialLoanMember</td>

<td valign="top">Commercial Loan [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">A loan, whether secured or unsecured, to a company for purposes such as seasonal working capital needs, inventory financing, equipment purchases and acquisitions.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">CommercialRealEstateMember</td>

<td valign="top">Commercial Real Estate [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Property that is solely used for business purposes.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">ConstructionLoansMember</td>

<td valign="top">Construction Loans [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">A borrowing arrangement which provides the entity constructing a facility (such as a building and a landfill) with funds to effect construction, generally on a draw down, or as needed, basis.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">ConsumerLoanMember</td>

<td valign="top">Consumer Loan [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Loan or extension of credit for personal, family, or household use excluding real estate.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">CrudeOilMember</td>

<td valign="top">Crude Oil [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Unrefined, unprocessed oil, which may be used in a variety of applications, and from which, petroleum-based products are produced.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">FuelMember</td>

<td valign="top">Fuel [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Represents material used for the production of energy in the form of heat or power. Examples may include, but not be limited to heating, transpiration, etc.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">GeneralLiabilityMember</td>

<td valign="top">General Liability [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Type of business insurance which provides insurance coverage for a wide variety of liability exposures including, but not limited to, contractual liability, product liability and personal injury liability.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">HeatingOilMember</td>

<td valign="top">Heating Oil [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Fuel oil used to produce heat in an office, plant, or any other location where temperature is controlled or managed.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">HomeEquityLoanMember</td>

<td valign="top">Home Equity Loan [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Loan based on the equity of the borrower's residential property in which the borrower receives the loan amount upfront. Excludes home equity lines of credit.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">HomeEquityMember</td>

<td valign="top">Home Equity Line of Credit [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Revolving, open-end loan extended under a line of credit and secured by the borrower's residential property.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">LetterOfCreditMember</td>

<td valign="top">Letter of Credit [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">A document typically issued by a financial institution which acts as a guarantee of payment to a beneficiary, or as the source of payment for a specific transaction (for example, wiring funds to a foreign exporter if and when specified merchandise is accepted pursuant to the terms of the letter of credit).</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">LineOfCreditMember</td>

<td valign="top">Line of Credit [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">A contractual arrangement with a lender under which borrowings can be made up to a specific amount at any point in time, and under which borrowings outstanding may be either short-term or long-term, depending upon the particulars.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">LoansMember</td>

<td valign="top">Loans [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">When a lender gives money or property over other debt securities sold by the issuer. In the event the issuer goes bankrupt, senior debt holders receive priority for [must receive] repayment [prior] relative to junior and unsecured (general) creditors.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">MortgageLoansOnRealEstateMember</td>

<td valign="top">Mortgage Loans on Real Estate [Member] (Deprecated 2015-01-31)</td>

<td valign="top">us-gaap</td>

<td valign="top">A loan to finance the purchase of real estate where the lender has a lien on the property as collateral for the loan.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">NaturalGasLiquidsReservesMember</td>

<td valign="top">Natural Gas Liquids [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Natural gas liquids that include, but are not limited to, ethane, propane, natural gasoline, butane and isobutane.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">NaturalGasReservesMember</td>

<td valign="top">Natural Gas [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Natural gas composed primarily of methane gas, excluding liquid or condensate natural gas.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">OilReservesMember</td>

<td valign="top">Oil [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Crude oil, which may also include condensate and natural gas liquids.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">ProfessionalMalpracticeLiabilityMember</td>

<td valign="top">Professional Malpractice Liability Insurance [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Business insurance coverage for professionals, such as doctors, lawyers, insurance agents, accountants, real estate agents, veterinarians, and others. This liability coverage insures losses for claims arising from mistakes and errors or omissions in the course of professional activities.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">RealEstateLoanMember</td>

<td valign="top">Real Estate Loan [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Loan to finance the purchase of real estate, including but not limited to, land or building.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">ResidentialMortgageMember</td>

<td valign="top">Residential Mortgage [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Loan to purchase or refinance residential real estate for example, but not limited to, a home, in which the real estate itself serves as collateral for the loan.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">SyntheticOilMember</td>

<td valign="top">Synthetic Oil [Member]</td>

<td valign="top">us-gaap</td>

<td valign="top">Lubricant consisting of chemical compounds that are synthetically made.</td>

</tr>

</tbody>

</table>

### Consolidation Items [Axis] <span style="font-size:small">_(ConsolidationItemsAxis)_</span>

This axis is used to reconcile the values reported for the operating segments and the totals reported for the consolidated entity. The values used on this axis are restricted to the members that appear on this axis in the US GAAP taxonomy. Generally, extension members should not be used on this axis except in cases where the company aggregates eliminations, material reconciling items and corporate items in various combinations. If these combinations are reported by the company, then use the extension members defined below. The use of this axis is discussed in detail in [FASB Segment Reporting guide](http://www.fasb.org/cs/ContentServer?c=Document_C&pagename=FASB%2FDocument_C%2FDocumentPage&cid=1176167943040). (DQC_0001.70)

<table border="0" cellspacing="0" cellpadding="0">

<tbody>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">**Extension Element**</td>

<td valign="top">**Element Name**</td>

<td valign="top">**Documentation**</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">Eliminations, Corporate and Reconciling items</td>

<td valign="top">CorporateReconcilingItemsAndEliminationsMember</td>

<td valign="top">Represents the aggregate total of adjustments for non operating corporate items, reconciling items and eliminations.</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">Corporate and Reconciling Items</td>

<td valign="top">CorporateAndReconcilingItemsMember</td>

<td valign="top">Represents the aggregate total of non operating corporate items and reconciling items</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">Corporate and Eliminations</td>

<td valign="top">CorporateAndEliminationsMember</td>

<td valign="top">Represents the aggregate total of non operating corporate items and elimination items</td>

</tr>

<tr>

<td valign="top" style="word-wrap:break-word;max-width:120px">Eliminations and Reconciling Items</td>

<td valign="top">EliminationsAndReconcilingItemsMember</td>

<td valign="top">Represents the aggregate total of reconciling items and  elimination items</td>

</tr>

</tbody>

</table>

### Defined Benefit Plan, Asset Categories [Axis] <span style="font-size:small">_(DefinedBenefitPlanByPlanAssetCategoriesAxis)_</span>

This axis is used to define the various categories of plan assets held by a defined benefit pension plan. This axis should only have members that represent assets of the plan. The members that appear on this axis can be extensions or members from within the US GAAP taxonomy that represent assets. Many company have incorrectly used members on this axis to define the actual pension plan type such as, US Pension Plans. Do not use members that represent various types of pension plans as types of plan assets. (DQC_0001.71)

### Award Date [Axis] <span style="font-size:small">_(AwardDateAxis)_</span>

This axis is used to distinguish equity-based compensation arrangements by the date or year of grant. Given that these are specific to the reporting company, the members on this axis must be defined as extension elements. (DQC_0001.72)

### Subsequent Event Type [Axis]  <span style="font-size:small">_(SubsequentEventTypeAxis)_</span>

This axis is used to indicate that a value is reported subsequent to the balance sheet. The member element Subsequent Event [Member] is the only member permitted on this axis. The FASB Taxonomy Implementation Guide on subsequent events states: "_Subsequent Event [Member]", the member already included in the Taxonomy, is intended to be used to qualify the reported facts so as to "flag" the information being reported as a subsequent event. There are no other member elements that are appropriate for use with "Subsequent Event Type [Axis]"_. (DQC_0001.74)

* * *

<div id="ftn1"><a title="" name="ftnref1"></a><sup>[1]</sup> SEC Staff Observations November 1, 2010 stated that "the SEC noted circumstances where filers have not used the modeling of elements currently published in the US GAAP Taxonomy. The SEC suggested filers utilize the pre-defined table structures included in the taxonomy, and use the related line item elements and domain members to the extent they are applicable for their specific circumstances. (FAQ E.16)"</div>
