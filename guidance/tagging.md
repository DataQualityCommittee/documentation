## XBRL US Center for Data Quality Committee Guidance
# Guidance on Tagging Axis and Members Using the US GAAP Taxonomy
### Approved October 2016
### Updated January 2017

[Download as PDF](AxisMemberTagging.pdf?raw=true)

The XBRL US Data Quality Committee (DQC) has developed prescriptive guidance for issuers submitting XBRL files that contain financial statements to the Securities Exchange Commission (SEC). This guidance provides for uniform, consistent tagging of financial data using the US GAAP taxonomy to improve the usability of such data. The DQC has also developed rules that test XBRL files for conformity with the guidance. The guidance in this document provides links and references, where applicable, to the associated rules developed by the DQC. It is expected that issuers will comply with the guidance presented in this document when tagging their financial statements for submission to the SEC.

## Appropriate Modeling of Axis and Members

In its Staff Observations, the SEC suggested filers utilize the pre-defined table structures included in the US GAAP taxonomy. Certain axes in the US GAAP taxonomy should only have certain members, otherwise consumption of the data is adversely impacted because the resulting axis and member combinations are nonsensical, e.g., reporting a type of currency as a member on a debt instrument axis. The following guidance provides limitations on the use of certain axis and member combinations that should be adhered to when tagging financial information using the US GAAP Taxonomy.

### Default Dimension

The default dimension should not be changed from that defined in the US GAAP taxonomy. Users of XBRL data expect that the default member of an axis will be the same across filings. For example, if a company reports a value of Revenues with no dimensions it is assumed that this represents revenues of the consolidated entity. However, if the company changed the default member of the Legal Entity axis to the parent company member then every value without a dimension would represent the parent company and not the revenue of the consolidated entity. ([DQC_0041](https://xbrl.us/data-rule/dqc_0041/).73).

### Fair Value, Hierarchy [Axis] <span style="font-size: small;">(_FairValueByFairValueHierarchyLevelAxis)_</span>

This axis is used to categorize the valuation techniques used to measure the fair value of an asset or liability. It is expected that only three members from the US GAAP taxonomy will be used on this axis representing the three separate levels defined by the FASB (i.e., level 1, level 2 and level 3 members defined on this axis). Extensions on this axis are limited to those cases where the company combines multiple hierarchical levels together such as, combinations of level 1 and level 2 and combinations of level 2 and level 3\. The element names to be used for these extension members are:  

| Element Name | Label | Namespace |
| ----- | ----- | ----- |
| FairValueInputsLevel1AndLevel2Member | Fair Value Inputs Level 1 And Level 2 [Member] | extension |
| FairValueInputsLevel2AndLevel3Member | Fair Value Inputs Level 2 And Level 3 [Member] | extension |


Do not use the Estimate of Fair Value Measurement [Member] element on this axis. This member is often used incorrectly to represent a total for this axis. The total does not need a member associated with it on this axis. ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).51)

### Reclassification out of Accumulated Other Comprehensive Income [Axis] <span style="font-size: small;">_(ReclassificationOutOfAccumulatedOtherComprehensiveIncomeAxis)_</span>

This axis is used to indicate that an item was reclassified from accumulated other comprehensive income into income. The element Reclassification out of Accumulated Other Comprehensive Income [Member] is the only member permitted on this axis. Do not create extensions members on this axis. ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).52)  

| Element Name | Label | Namespace | Documentation |
| ReclassificationOutOfAccumulatedOtherComprehensiveIncome | Reclassification out of Accumulated Other Comprehensive Income [Member] | us-gaap | Identifies item reclassified out of accumulated other comprehensive income (loss). |

### Other Ownership Interests Name [Axis] <span style="font-size: small;">_(OtherOwnershipInterestsByNameAxis)_</span>

This axis is used to define the specific ownership interests of the company by specific name. Given that these are specific to the reporting company, the members on this axis must be defined as extension elements. The company extension element name should match the legal name of the legal entity if it is available and should remain consistent across filing periods and should be consistent within a single filing. The label of the member can be a short name or full name. ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).53)

### Legal Entity [Axis] <span style="font-size: small;">(_LegalEntityAxis)_</span>

This axis is used to define the details of specific legal entities. Only extension members representing specific legal entities should be used on this axis in addition to members that represent classes of legal entities defined in the US GAAP taxonomy. The members in the US GAAP taxonomy that can be used on this axis include the members on the Legal Entity [Axis] and the members on the Federal Home Loan Bank Advances Branch Of FHLB Bank [Axis]. The following members in the table below are also permitted. ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).54)  

| Element Name | Label | Namespace | Documentation |
| ----- | ----- | ----- | ----- |
| PredecessorMember | Predecessor [Member] | us-gaap | This element represents the designation of financial information as pertaining, but not limited, to a predecessor company or plan as defined in the context of the financial statements. |
| CoVenturerMember | Co-Venturer [Member] | us-gaap | Other venturer from the perspective of the entity in the corporate joint venture. |
| SpinoffMember | Spinoff [Member] | us-gaap | Creation of an independent entity from an existing entity through divestiture, for example, but not limited to, sale or distribution of new shares. |
| PartnershipMember | Partnership [Member] | us-gaap | Legal entity in the form of a partnership created to conduct business. |
| LimitedLiabilityCompanyMember | Limited Liability Company [Member] | us-gaap | Legal form of business company offering limited liability to its owners (denoted by L.L.C. or LLC in the U.S.). |
| TrustForBenefitOfEmployeesMember | Trust For Benefit Of Employees [Member] | us-gaap | Trust created by the entity that exists for the benefit of its employees, such as pension and profit-sharing trusts that are managed by or under the trusteeship of the entity's management. |

### Unique Name [Axis] <span style="font-size: small;">_(NoncashOrPartNoncashDivestituresByUniqueNameAxis)_</span>

This axis is used to provide divestiture information by unique name of asset or business. Given that these are specific to the reporting company, the members on this axis must be defined as extension elements. ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).56)

### Investment, Name [Axis] <span style="font-size: small;">_(ScheduleOfEquityMethodInvestmentEquityMethodInvesteeNameAxis)_</span>

This axis is used to provide the name of each investee accounted for under the equity method of accounting. Given that these are specific to the reporting company, the members on this axis must be defined as extension elements. In many cases, companies have incorrectly used the element Equity Method Investments [Member] in conjunction with a financial statement line item like revenues to represent summary financial information for equity method investments. This member should not be used as specific equity method line items are defined for financial statement line items ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).57)

### Counterparty Name [Axis] <span style="font-size: small;">_(CounterpartyNameAxis)_</span>

This axis is used to provide the name of the counterparty. Given that these are specific to the reporting entity, the members on this axis should be extensions. There are a number of members defined in the US GAAP taxonomy that can also be used on this axis. The table below lists the allowable members. Some companies have used generic members defined in the taxonomy like Subsidiary Issuer [Member] or Director [Member]. These should only be used where these members are synonymous with a single entity. The Parent Company [Member] should not be used as the consolidated entity is comprised of the parent. If a subsidiary had a transaction with the parent, the subsidiary would be the counterparty. ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).58)

| Element Name | Label | Namespace | Documentation |
| ----- | ----- | ----- | ----- |
| AffiliatedEntityMember | Affiliated Entity [Member] | us-gaap | An affiliate is a party that, directly or indirectly through one or more intermediaries, controls, is controlled by, or is under common control with the entity. |
| InvestorMember | Investor [Member] | us-gaap | Business entity or individual that puts money, by purchase or expenditure, in something offering potential profitable returns, such as interest income or appreciation in value. |
| VariableInterestEntityNotPrimaryBeneficiaryMember | Variable Interest Entity, Not Primary Beneficiary [Member] | us-gaap | Variable Interest Entities (VIE) in which the entity does not have a controlling financial interest (as defined) and of which it is therefore not the primary beneficiary. VIEs of which the entity is not the primary beneficiary because it does not have the power to direct the activities of the VIE that most significantly impact the VIE's economic performance and for which it does not have the obligation to absorb losses of the VIE that could potentially be significant to the VIE or the right to receive benefits from the VIE that could potentially be significant to the VIE are not included in the consolidated financial statements of the entity. |
| ChiefFinancialOfficerMember | Chief Financial Officer [Member] | us-gaap | Senior executive officer responsible for overseeing the financial activities of the entity. |
| IndividualMember | Individual Counterparty [Member] | us-gaap | Individual person that is legally permitted to enter into a contract and be sued if that person fails to meet the obligations imposed by a contract. |
| GovernmentMember | Government [Member] | us-gaap | Organization that is the governing authority of a community. |
| GuarantorSubsidiariesMember | Guarantor Subsidiaries [Member] | us-gaap | Entity owned or controlled by another entity which has guaranteed the issue of securities by another subsidiary of the parent or has guaranteed the issue of securities by the parent. |
| SubsidiaryIssuerMember | Subsidiary Issuer [Member] | us-gaap | A company controlled, directly or indirectly, by its parent, which has issued securities and those securities are guaranteed by its parent and another subsidiary of the parent. |
| DirectorMember | Director [Member] | us-gaap | Person serving on the board of directors (who collectively have responsibility for governing the entity). |
| ChiefExecutiveOfficerMember | Chief Executive Officer [Member] | us-gaap | Highest ranking executive officer, who has ultimate managerial responsibility for the entity and who reports to the board of directors. In addition, the chief executive officer (CEO) may also be the chairman of the board or president. |
| ChiefOperatingOfficerMember | Chief Operating Officer [Member] | us-gaap | Senior executive officer responsible for management of day-to-day activities of the entity. |
| GeneralPartnerMember | General Partner [Member] | us-gaap | Party to a partnership business who has unlimited liability. |
| CorporateJointVentureMember | Corporate Joint Venture [Member] | us-gaap | Corporation owned and operated by a small group of ventures to accomplish a mutually beneficial venture or project. |
| SubsidiaryOfCommonParentMember | Subsidiary of Common Parent [Member] | us-gaap | Refers to an entity under the control of the same parent as another entity (that is, a sister company). |

### Plan Name [Axis] <span style="font-size: small;">_(PlanNameAxis)_</span>

This axis is used to distinguish information by the name of an equity-based compensation arrangement plan. Given that these are specific to the reporting company, the members on this axis must be defined as extension elements. Members on this axis should represent discrete plans of the company such as Stock Option Plan 2016\. ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).59)

### Defined Contribution Plan Name [Axis] <span style="font-size: small;">_(DefinedContributionPlanNameAxis)_</span>

This axis is used to distinguish information by the name of the defined contribution plan. Given that these are specific to the reporting company, the members on this axis must be defined as extension elements. ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).60)

### Currency [Axis] <span style="font-size: small;">_(CurrencyAxis)_</span>

This axis is used to indicate the currency that an instrument is denominated in and members are restricted to only valid currencies listed in the current taxonomy. The members on this axis should match the currency designators defined by ISO. Extension members are only permitted in those cases where the currency has not been incorporated into the taxonomy. When creating an extension for these items, they should match the element name defined for the allowable extensions below. ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).62)  

| Element Name | Label | Namespace | Documentation |
| ----- | ----- | ----- | ----- |
| SICAD1Member | SICA D1 [Member] | extension | Venezuelan complementary currency exchange system, Sistema Complementario de Administracion de Divisas 1 |
| SICAD2Member | SICA D2 [Member] | extension | Venezuelan complementary currency exchange system, Sistema Complementario de Administracion de Divisas 2 |
| OtherCurrencyMember | Other [Member] | extension | Represents all other currencies not specifically defined. |
| NonUSDollarMember | Non-U.S. Dollar [Member] | extension | Represents all other currencies that are not USD. |
| CENCOEXMember | CENCOEX [Member] | extension | The official Venezuelan exchange rate offered by the National Foreign Trade Center. (CENCOEX) |
| SICADMember | SICAD [Member] | extension | The Venezuelan exchange rate available to companies importing essential goods (e.g., certain food, medicine, raw materials). Consolidates SICAD 1 and SICAD 2 |
| SIMADIMember | SIMADI [Member] | extension | The market based Venezuelan Exchange Rate. |
| DIPROMember | DIPRO [Member] | extension | Venezuelan Exchange Rate that replaced the SICAD on March 10, 2016\. The DIPRO, is used for payments of critical importance such as healthcare. |
| DICOMMember | DICOM [Member] | extension | Venezuelan Exchange Rate that replaced the SIMADI on March 10, 2016\. The DICOM, fluctuates according to market supply and demand. |

### Position [Axis] <span style="font-size: small;">_(PositionAxis)_</span>

This axis is used to indicate the long or short position taken on a security. The US GAAP taxonomy includes a Long [Member] and Short [Member] that can be used on this axis. The rule also permits two extensions Net Long Positions [Member] and Net Short Positions [Member]. These two extension elements can be used on this axis to represent the notional amounts when long and short positions are netted. The Long [Member] and Short [Member] represent positions before any netting occurs. For example, in the diagram below the company reports the notional amounts for purchases and sales and a third column of notional amounts that represent the net purchases and sales. All of the values in this table are reported using the notional line item with the various axes shown. In the final three columns, in red, are the notion values of the Long, Short and Net positions. In order to tag the column of Net Purchases and Sales, the extension members Net Long Positions [Member] and Net Short Positions [Member] are required. ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).63)  
[DQC-guidance_image001](https://xbrl.us/wp-content/uploads/2016/05/DQC-guidance_image001.png)

### Measurement Frequency [Axis] <span style="font-size: small;">_(FairValueByMeasurementFrequencyAxis)_</span>

This axis is used to indicate if a measurement is on a recurring or non recurring basis. This axis can only have these two members defined in the US GAAP taxonomy associated with it. Extensions on this axis are not permitted. ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).64)  

| Element Name | Label | Namespace | Documentation |
| ----- | ----- | ----- | ----- |
| FairValueMeasurementsRecurringMember | Fair Value, Measurements, Recurring [Member] | us-gaap | This item represents a description of the frequency with which certain items are measured at fair value. Items measured at fair value on a recurring basis generally include those items for which measurement inputs are readily available and which are measured at fair value at successive reporting periods. |
| FairValueMeasurementsNonRecurringMember | Fair Value, Measurements, Nonrecurring [Member] | us-gaap | This item represents a description of the frequency with which certain items are measured at fair value. Items measured at fair value on a nonrecurring basis generally include those items for which measurement inputs are not readily available and which are measured at fair value infrequently (for example, impaired assets). |

### Measurement Basis [Axis] <span style="font-size: small;">_(FairValueByMeasurementBasisAxis)_</span>

This axis is used to indicate the measurement basis for a given asset or liability. This axis can only have five members that are defined in the US GAAP taxonomy associated with it. Extensions on this axis are not permitted. ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).65)

### Hedging Designation [Axis] <span style="font-size: small;">_(HedgingDesignationAxis)_</span>

This axis is used to indicate if a derivative is designated as a hedging instrument or if a derivative is not designated as a derivative instrument. This axis can have these two members that are defined in the US GAAP taxonomy associated with it. This axis can also have two extension members ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).66):  

| Element Name | Label | Namespace |
| NotDesignatedAsHedgingInstrumentEconomicHedgesMember | Not Designated As Hedging Instrument Economic Hedges [Member] | extension |
| NotDesignatedAsHedgingInstrumentTradingMember | Not Designated As Hedging Instrument Trading [Member] | extension |

### Products and Services [Axis] <span style="font-size: small;">_(ProductOrServiceAxis)_</span>

=======

| Element Name | Label | Namespace |
| ----- | ----- | ----- |
| NotDesignatedAsHedgingInstrumentEconomicHedgesMember | Not Designated As Hedging Instrument Economic Hedges [Member] | extension |
| NotDesignatedAsHedgingInstrumentTradingMember | Not Designated As Hedging Instrument Trading [Member] | extension |

### Products and Services [Axis] <span style="font-size: small;">_(ProductOrServiceAxis)_</span>

This axis is used to distinguish the details of products or services of the reporting entity. Given that products and services are generally specific to the reporting company, the members on this axis would be predominantly defined using extension elements. In the US GAAP taxonomy, a number of generic product and service members are defined for industries where the products are highly standardized such as, insurance or where the products are commodities such as, oil. In these cases, members from the US GAAP taxonomy can be used. The list of product and service members that can be used from the US GAAP taxonomy are those included on the following axes:

*   _ProductOrServiceAxis_
*   _ReinsurancePremiumsForInsuranceCompaniesByProductSegmentAxis, ScheduleOfMalpracticeInsuranceTypeAndTierIdentifierAxis_
*   _AircraftTypeAxis_

In addition the members defined below can also be used. ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).69)  

| Element Name | Label | Namespace | Documentation |
| ----- | ----- | ----- | ----- |
| AuctionRateSecuritiesMember | Auction Rate Securities [Member] | us-gaap | Debt instrument securities (for example, but not limited to, corporate or municipal bonds) that typically have long-term nominal maturities for which the interest rate is reset through an auction process. |
| AutomobileLoanMember | Automobile Loan [Member] | us-gaap | Loan to finance the purchase of a vehicle. |
| CommercialLoanMember | Commercial Loan [Member] | us-gaap | A loan, whether secured or unsecured, to a company for purposes such as seasonal working capital needs, inventory financing, equipment purchases and acquisitions. |
| CommercialRealEstateMember | Commercial Real Estate [Member] | us-gaap | Property that is solely used for business purposes. |
| ConstructionLoansMember | Construction Loans [Member] | us-gaap | A borrowing arrangement which provides the entity constructing a facility (such as a building and a landfill) with funds to effect construction, generally on a draw down, or as needed, basis. |
| ConsumerLoanMember | Consumer Loan [Member] | us-gaap | Loan or extension of credit for personal, family, or household use excluding real estate. |
| CrudeOilMember | Crude Oil [Member] | us-gaap | Unrefined, unprocessed oil, which may be used in a variety of applications, and from which, petroleum-based products are produced. |
| FuelMember | Fuel [Member] | us-gaap | Represents material used for the production of energy in the form of heat or power. Examples may include, but not be limited to heating, transpiration, etc. |
| GeneralLiabilityMember | General Liability [Member] | us-gaap | Type of business insurance which provides insurance coverage for a wide variety of liability exposures including, but not limited to, contractual liability, product liability and personal injury liability. |
| HeatingOilMember | Heating Oil [Member] | us-gaap | Fuel oil used to produce heat in an office, plant, or any other location where temperature is controlled or managed. |
| HomeEquityLoanMember | Home Equity Loan [Member] | us-gaap | Loan based on the equity of the borrower's residential property in which the borrower receives the loan amount upfront. Excludes home equity lines of credit. |
| HomeEquityMember | Home Equity Line of Credit [Member] | us-gaap | Revolving, open-end loan extended under a line of credit and secured by the borrower's residential property. |
| LetterOfCreditMember | Letter of Credit [Member] | us-gaap | A document typically issued by a financial institution which acts as a guarantee of payment to a beneficiary, or as the source of payment for a specific transaction (for example, wiring funds to a foreign exporter if and when specified merchandise is accepted pursuant to the terms of the letter of credit). |
| LineOfCreditMember | Line of Credit [Member] | us-gaap | A contractual arrangement with a lender under which borrowings can be made up to a specific amount at any point in time, and under which borrowings outstanding may be either short-term or long-term, depending upon the particulars. |
| LoansMember | Loans [Member] | us-gaap | When a lender gives money or property over other debt securities sold by the issuer. In the event the issuer goes bankrupt, senior debt holders receive priority for [must receive] repayment [prior] relative to junior and unsecured (general) creditors. |
| MortgageLoansOnRealEstateMember | Mortgage Loans on Real Estate [Member] (Deprecated 2015-01-31) | us-gaap | A loan to finance the purchase of real estate where the lender has a lien on the property as collateral for the loan. |
| NaturalGasLiquidsReservesMember | Natural Gas Liquids [Member] | us-gaap | Natural gas liquids that include, but are not limited to, ethane, propane, natural gasoline, butane and isobutane. |
| NaturalGasReservesMember | Natural Gas [Member] | us-gaap | Natural gas composed primarily of methane gas, excluding liquid or condensate natural gas. |
| OilReservesMember | Oil [Member] | us-gaap | Crude oil, which may also include condensate and natural gas liquids. |
| ProfessionalMalpracticeLiabilityMember | Professional Malpractice Liability Insurance [Member] | us-gaap | Business insurance coverage for professionals, such as doctors, lawyers, insurance agents, accountants, real estate agents, veterinarians, and others. This liability coverage insures losses for claims arising from mistakes and errors or omissions in the course of professional activities. |
| RealEstateLoanMember | Real Estate Loan [Member] | us-gaap | Loan to finance the purchase of real estate, including but not limited to, land or building. |
| ResidentialMortgageMember | Residential Mortgage [Member] | us-gaap | Loan to purchase or refinance residential real estate for example, but not limited to, a home, in which the real estate itself serves as collateral for the loan. |
| SyntheticOilMember | Synthetic Oil [Member] | us-gaap | Lubricant consisting of chemical compounds that are synthetically made. |
| PublicUtilitiesInventoryWaterMember | Water [Member] | us-gaap | Clear, colorless, odorless and tasteless liquid essential for most plant and animal life comprised of two parts hydrogen and one part oxygen (H2O). |
| PublicUtilitiesInventoryPropaneMember | Propane [Member] | us-gaap | Product derived from petroleum during the processing of oil or natural gas which is then used as a heat source or fuel. |
| ResidentialRealEstateMember | Residential Real Estate [Member] | us-gaap | Property that is used as a home. |

### Consolidation Items [Axis] <span style="font-size: small;">_(ConsolidationItemsAxis)_</span>

This axis is used to reconcile the values reported for the operating segments and the totals reported for the consolidated entity. The values used on this axis are restricted to the members that appear on this axis in the US GAAP taxonomy. Generally, extension members should not be used on this axis except in cases where the company aggregates eliminations, material reconciling items and corporate items in various combinations. If these combinations are reported by the company, then use the extension members defined below. The use of this axis is discussed in detail in [FASB Segment Reporting guide](http://www.fasb.org/cs/ContentServer?c=Document_C&pagename=FASB%2FDocument_C%2FDocumentPage&cid=1176167943040). ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).70)  

| Element Name | Label | Namespace | Documentation |
| ----- | ----- | ----- | ----- |
| CorporateReconcilingItemsAndEliminationsMember | Eliminations, Corporate and Reconciling Items [Member] | extension | Represents the aggregate total of adjustments for non operating corporate items, reconciling items and eliminations. |
| CorporateAndReconcilingItemsMember | Corporate and Reconciling Items [Member] | extension | Represents the aggregate total of non operating corporate items and reconciling items |
| CorporateAndEliminationsMember | Corporate and Eliminations [Member] | extension | Represents the aggregate total of non operating corporate items and elimination items |
| EliminationsAndReconcilingItemsMember | Eliminations and Reconciling Items [Member] | extension | Represents the aggregate total of reconciling items and elimination items |
| OperatingSegmentsAndCorporateNonSegmentMember | Operating Segments and Corporate Non Segment [Member] | extension | Represents the aggregate total of "Operating Segments" and "Corporate, Non-Segment", before elimination and reconciliation items. |

### Defined Benefit Plan, Asset Categories [Axis] <span style="font-size: small;">_(DefinedBenefitPlanByPlanAssetCategoriesAxis)_</span>

This axis is used to define the various categories of plan assets held by a defined benefit pension plan. This axis should only have members that represent assets of the plan. The members that appear on this axis can be extensions or members from within the US GAAP taxonomy that represent assets. Many company have incorrectly used members on this axis to define the actual pension plan type such as, US Pension Plans. Do not use members that represent various types of pension plans as types of plan assets. ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).71)

### Award Date [Axis] <span style="font-size: small;">_(AwardDateAxis)_</span>

This axis is used to distinguish equity-based compensation arrangements by the date or year of grant. Given that these are specific to the reporting company, the members on this axis must be defined as extension elements. ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).72)

### Subsequent Event Type [Axis]  <span style="font-size: small;">_(SubsequentEventTypeAxis)_</span>

This axis is used to indicate that a value is reported subsequent to the balance sheet. The member element Subsequent Event [Member] is the only member permitted on this axis. The FASB Taxonomy Implementation Guide on subsequent events states: "_Subsequent Event [Member]", the member already included in the Taxonomy, is intended to be used to qualify the reported facts so as to "flag" the information being reported as a subsequent event. There are no other member elements that are appropriate for use with "Subsequent Event Type [Axis]_". ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).74)  

| Element Name | Label | Namespace | Documentation |
| ----- | ----- | ----- | ----- |
| SubsequentEventMember | Subsequent Event [Member] | extension | Identifies event that occurred after the balance sheet date but before financial statements are issued or available to be issued. |

### Statement Equity Components [Axis] <span style="font-size: small; font-style: italic;">(StatementEquityComponentsAxis)</span>

This axis is used to disaggregate shareholders equity into all its possible components. This axis should only include sub categories of shareholders equity and partnership capital on this axis. This axis can only have those members identified as components of stockholder equity in the US GAAP taxonomy, the additional members identified below and extension members which may be specific to a given company that are not included in the taxonomy. ([DQC_0001](https://xbrl.us/data-rule/dqc_0001/).75)

| Element Name | Label | Namespace | Documentation |
| ----- | ----- | ----- | ----- |
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

* * *

<div id="ftn1"><a title="" name="ftnref1"></a><sup>[1]</sup> The FASB has issued a FAQ on this which states the following:  
**Is it appropriate to use RangeAxis for dates?**  
TheRangeAxis can be used in instances in which the value is useful life. For example, it is common to disclose the useful life of property, plant, and equipment as a minimum and maximum life, and that would be an acceptable use ofRangeAxis.It would not be appropriate to use RangeAxisfor earliest and latest because those terms are not synonymous with minimum and maximum. [Revised 2014-03]</div>
