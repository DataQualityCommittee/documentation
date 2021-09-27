# Data Quality Committee Meeting - September 29, 2021

### Introductions
	New Chair - Shelly Wavrin, Toppan Merrill
  
### Approval of Minutes
  + [June 29, 2021 Meeting Minutes](DRAFTDQCMeetingNotes06292021.docx?raw=true)

### Review and Approval of Version 16 DQC Rules
[Version 16 Rules Summary (.docx)](v16-public-review-updates.docx?raw=true) 
  + [DQC_0117 Financial Statement Tables Dimensional Cross Check](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v16/docs/DQC_US_0117/DQC_0117.md)
  This rule identifies inconsistent calculations defined for the Financial Statements.  The rule covers the Cash Flow Statement, Statement of Financial Position and the Income Statement and excludes the Statement of Changes in Shareholders Equity.  The rule evaluates if the dimensional values reported in the financial statements are equal to the reported sum of these dimensional values. Both the dimensional values and the aggregate value need to be reported in the financial statement.  The rule checks a limited amount of axes. The axis aggregations checked by the rule are as follows:
    - StatementClassOfStockAxis
    - ProductOrServiceAxis'
    - PropertyPlantAndEquipmentByTypeAxis
    - LongtermDebtTypeAxis
    - RelatedPartyTransactionsByRelatedPartyAxis
    - StatementBusinessSegmentsAxis
    - FinancialInstrumentAxis
    - LimitedPartnersCapitalAccountByClassAxis
    - PartnerTypeOfPartnersCapitalAccountAxis
    - FiniteLivedIntangibleAssetsByMajorClassAxis
    - InformationByCategoryOfDebtSecurityAxis
  + [DQC_0118 - Financial Statement Tables Calculation Check of Required Context](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v16/docs/DQC_US_0118/DQC_0118.md)
  This rule identifies inconsistent calculations defined for the Financial Statements.  The rule covers the Cash Flow Statement, Statement of Financial Position, the Income Statement and excludes the Statement of Changes in Shareholders Equity.  The rule evaluates each line in the financial statements representing an aggregation based on the elements defined in the calculation linkbase.  If the sum of the child elements does not equal the value reported for the aggregation then an error is reported.  The rule will only run for the period representing the required context.
  + [DQC_0119 - Income Before Tax Equity Method](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v16/docs/DQC_US_0119/DQC_0119.md)
  This rule is intended to identify those cases where the company uses the element IncomeLossFromContinuingOperationsBeforeIncomeTaxesMinorityInterestAndIncomeLossFromEquityMethodInvestments in an inappropriate manner.  
  + [DQC_0120 - Incorrect Line Item Reference](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v16/docs/DQC_US_0120/DQC_0120.md)
  DQC_0120 - Incorrect Line Item Reference This rule is intended to identify those cases where the company uses an extensible list item that refers to a balance sheet line item that does not exist on the balance sheet.  The rule checks that the values provided for the following extensible list items are legitimate balance sheet line items that appear in the calculation linkbase of the balance sheet:
    - FinanceLeaseLiabilityCurrentStatementOfFinancialPositionExtensibleList
    - FinanceLeaseLiabilityNoncurrentStatementOfFinancialPositionExtensibleList
    - FinanceLeaseRightOfUseAssetStatementOfFinancialPositionExtensibleList 
    - OperatingLeaseLiabilityNoncurrentStatementOfFinancialPositionExtensibleList
    - OperatingLeaseLiabilityCurrentStatementOfFinancialPositionExtensibleList 
    - OperatingLeaseRightOfUseAssetStatementOfFinancialPositionExtensibleList
  + [DQC_0121 - Incorrect Transition Elements Used](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v16/docs/DQC_US_0121/DQC_0121.md)
  This rule is intended to identify those cases where the company reports line items that have been transitioned because of changes in accounting standards. The rule identifies those elements that should no longer be used by the filer.  The taxonomy includes updated elements that reflect the new accounting standards and they should be used. In many cases the filer is unaware that an element has been transitioned and continues to use it until such time as it is deprecated and can no longer be used.  This rule helps identify these elements so that filers can replace the transition elements with elements that reflect current US-GAAP.
  + [DQC_0122 - Components of Equity on the Balance Sheet](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v16/docs/DQC_US_0122/DQC_0122.md)
  This rule is intended to identify those cases where the company reports the components of equity or partners capital on the balance sheet. If one of these two dimensions are included as part of the balance sheet then the rule will return an error identifying the number of facts using the axis reported in the balance sheet.
  + [DQC_0123 - Missing Components of Equity](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v16/docs/DQC_US_0123/DQC_0123.md)
  The rule identifies where a company has reported classes of stock but has not indicated if they are common or preferred or treasury components of equity. The rule identifies facts reported using one of the following line items using the class of stock axis without any other dimensions:
    - StockholdersEquityIncludingPortionAttributableToNoncontrollingInterest or 
    - StockholdersEquity
  + [DQC_0124 - Breakdown of Lease Liabilities & Assets Across Financial Statement Lines Items](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v16/docs/DQC_US_0124/DQC_0124.md)
  The rule flags an error when lease liabilities and assets are present but have not been included in the presentation linkbase of the financial statements. The intent of the rule is to allow filers to check that their filing is consistent with the FASB’s XBRL implementation guide and US-GAAP.  If the extensible list item or Balance Sheet Location Axis is not used then the rule will report an error.
  
#### Updates to Existing (previously approved) DQC Rules:
  + DQC_0057 – Cash Flow Opening and Closing Balances – updated rule to restrict use of the following elements representing the opening and closing balances on the statement of cash flow:
    - CashAndCashEquivalentsAtCarryingValueIncludingDiscontinuedOperations
    - CashAndCashEquivalentsAtCarryingValue
    - CashCashEquivalentsAndFederalFundsSold
    - Cash
    - CashEquivalentsAtCarryingValue
    - CashAndDueFromBank
  + DQC_0062 – No Fact Value for Change in Cash – updated rule to allow for extension elements where change in cash is split between discontinued and continuing operations
  + DQC_0065 – Interest Paid Net (Operating) Not on Cash Flow – updated rule to check for the occurrence of interest paid under the following additional abstract items:
    - SupplementalCashFlowElementsAbstract
    - NoncashInvestingAndFinancingItemsAbstract
    - AdditionalCashFlowElementsAndSupplementalCashFlowInformationAbstract
    - CashFlowNoncashInvestingAndFinancingActivitiesDisclosureAbstract
  + DQC_0115 – Fact Value Consistency Over Time (IFRS) – updated rule to exclude the following elements:
    - FinanceIncome
    - FinanceCosts
    - MiscellaneousOtherOperatingIncome
    - MiscellaneousOtherOperatingExpense
    - InvestmentIncome
    - InterestExpense
    - InterestIncomeOnFinancialAssetsDesignatedAtFairValueThroughProfitOrLoss
    - InterestExpenseOnFinancialLiabilitiesDesignatedAtFairValueThroughProfitOrLoss
  + DQC_0116 – Line Items Requiring the Asset Acquisition – Updated rule to add the following elements:
    - Goodwill
    - BusinessAcquisitionPlannedRestructuringActivitiesDescription
    - BusinessAcquisitionCostOfAcquiredEntityTransactionCosts
    - NumberOfBusinessesAcquired
    - BusinessCombinationControlObtainedDescription
    - BusinessCombinationGoodwillRecognizedDescription
    - BusinessCombinationConsiderationTransferredOther1
    - BusinessCombinationConsiderationTransferredLiabilitiesIncurred
    - BusinessCombinationConsiderationTransferredEquityInterestsIssuedAndIssuable
    - BusinessCombinationCostOfAcquiredEntityEquityInterestsIssuedAndIssuableFairValueMethod
    - BusinessCombinationConsiderationTransferred1,
    - BusinessCombinationConsiderationTransferredIncludingEquityInterestInAcquireeHeldPriorToCombination1
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedCashAndEquivalents
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedInventory
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedCurrentAssetsMarketableSecurities
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedCurrentAssetsPrepaidExpenseAndOtherAssets
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedCurrentAssetsReceivables
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedCurrentAssetsOther
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedCurrentAssets
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedIndefiniteLivedIntangibleAssets
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedIntangibles, BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedIntangibleAssetsOtherThanGoodwill
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedLand, BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedBuildings,
BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedEquipment, BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedPropertyPlantAndEquipment
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedOtherNoncurrentAssets
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedDeferredTaxAssets
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedNoncurrentAssets
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedFinancialAssets
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedAssets,
BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedCurrentLiabilitiesAccountsPayable
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedCurrentLiabilitiesDeferredRevenue
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedCurrentLiabilitiesLongTermDebt
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedCurrentLiabilitiesOther
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedCurrentLiabilities
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedDeferredTaxLiabilities
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedNoncurrentLiabilitiesOther
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedNoncurrentLiabilitiesLongTermDebt
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedNoncurrentLiabilities
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedCapitalLeaseObligation
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedContingentLiability
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedFinancialLiabilities
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedRestructuringLiabilities
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedLiabilities
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredAndLiabilitiesAssumedNet
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredGoodwillAndLiabilitiesAssumedNet
    - BusinessCombinationAcquisitionOfLessThan100PercentNoncontrollingInterestFairValue
    - BusinessCombinationRecognizedIdentifiableAssetsAcquiredGoodwillAndLiabilitiesAssumedLessNoncontrollingInterest
    - BusinessCombinationAcquiredReceivablesDescription
    - BusinessCombinationAcquiredReceivablesFairValue
    - BusinessCombinationAcquiredDirectFinancingLeaseReceivable
    - BusinessCombinationAcquiredSalesTypeLeaseReceivable
    - BusinessCombinationAcquiredReceivablesGrossContractualAmount
    - BusinessCombinationAcquiredReceivablesEstimatedUncollectible
    - BusinessCombinationAssetsArisingFromContingenciesAmountRecognized
    - BusinessCombinationLiabilitiesArisingFromContingenciesAmountRecognized
    - BusinessCombinationAssetsAndLiabilitiesArisingFromContingenciesAmountRecognized
    - BusinessCombinationAssetsArisingFromContingenciesAmountRecognizedOtherThanAtFairValue
    - BusinessCombinationLiabilitiesArisingFromContingenciesAmountRecognizedOtherThanAtFairValue
    - BusinessCombinationAssetsAndLiabilitiesArisingFromContingenciesAmountRecognizedOtherThanAtFairValue
    - BusinessCombinationAssetsAndLiabilitiesArisingFromContingenciesDescription
    - BusinessAcquisitionPreacquisitionContingencyAmountOfSettlement
    - BusinessCombinationBargainPurchaseGainRecognizedAmount
    - BusinessCombinationAcquisitionOfLessThan100PercentNoncontrollingInterestValuationTechnique
    - BusinessCombinationAcquisitionOfLessThan100PercentNoncontrollingInterestSignificantInputs
    - BusinessCombinationStepAcquisitionEquityInterestInAcquireeValuationTechniques
    - BusinessCombinationStepAcquisitionEquityInterestInAcquireeRemeasurementGain
    - BusinessCombinationStepAcquisitionEquityInterestInAcquireeRemeasurementLoss
    - BusinessCombinationStepAcquisitionEquityInterestInAcquireeRemeasurementGainOrLoss
    - BusinessCombinationStepAcquisitionEquityInterestInAcquireeRemeasurementGainOrLossFinancialStatementCaption
    - BusinessCombinationProvisionalInformationInitialAccountingIncompleteReasons
    - BusinessCombinationProvisionalInformationInitialAccountingIncompleteItems
    - BusinessCombinationProvisionalInformationInitialAccountingIncompleteNatureOfAdjustments
    - BusinessCombinationProvisionalInformationInitialAccountingIncompleteAdjustmentFinancialAssets
    - BusinessCombinationProvisionalInformationInitialAccountingIncompleteAdjustmentInventory
    - BusinessCombinationProvisionalInformationInitialAccountingIncompleteAdjustmentPropertyPlantAndEquipment
    - BusinessCombinationProvisionalInformationInitialAccountingIncompleteAdjustmentIntangibles,
BusinessCombinationProvisionalInformationInitialAccountingIncompleteAdjustmentFinancialLiabilities
    - BusinessCombinationProvisionalInformationInitialAccountingIncompleteAdjustmentEquityInterests
    - BusinessCombinationProvisionalInformationInitialAccountingIncompleteAdjustmentConsiderationTransferred
    - BusinessCombinationProvisionalInformationInitialAccountingIncompleteAdjustmentsRelatedToPreviousPeriod
    - BusinessCombinationContingentConsiderationAssetCurrent
    - BusinessCombinationContingentConsiderationAssetNoncurrent
    - BusinessCombinationContingentConsiderationAsset
    - BusinessCombinationContingentConsiderationLiabilityCurrent
    - BusinessCombinationContingentConsiderationLiabilityNoncurrent
    - BusinessCombinationContingentConsiderationLiability
    - BusinessCombinationContingentConsiderationArrangementsChangeInAmountOfContingentConsiderationAsset1
    - BusinessCombinationContingentConsiderationArrangementsChangeInAmountOfContingentConsiderationLiability1
    - BusinessCombinationContingentConsiderationArrangementsChangeInTheRangeOfOutcomesContingentConsiderationLiabilityValueHigh
    - BusinessCombinationContingentConsiderationArrangementsChangeInTheRangeOfOutcomesContingentConsiderationLiabilityValueLow
    - BusinessCombinationContingentConsiderationArrangementsChangeInTheRangeOfOutcomesContingentConsiderationLiabilityReasons
    - BusinessAcquisitionNameOfAcquiredEntity
    - BusinessAcquisitionDescriptionOfAcquiredEntity
    - BusinessAcquisitionSharePrice
    - BusinessAcquisitionPercentageOfVotingInterestsAcquired
    - BusinessAcquisitionRevenueReportedByAcquiredEntityForLastAnnualPeriod
    - BusinessCombinationReasonForBusinessCombination
    - BusinessAcquisitionDateOfAcquisitionAgreement1
    - BusinessAcquisitionEffectiveDateOfAcquisition1
    - BusinessAcquisitionPeriodResultsIncludedInCombinedEntity1
    - BusinessCombinationStepAcquisitionEquityInterestInAcquireeFairValue1
    - BusinessCombinationIndemnificationAssetsDescription
    - BusinessCombinationIndemnificationAssetsBasisForAmount
    - BusinessCombinationIndemnificationAssetsRangeOfOutcomesValueHigh
    - BusinessCombinationIndemnificationAssetsRangeOfOutcomesValueLow
    - BusinessCombinationIndemnificationAssetsRangeOfOutcomesInestimable
    - BusinessCombinationIndemnificationAssetsRangeOfOutcomesMaximumUnlimited
    - BusinessCombinationIndemnificationAssetsAmountAsOfAcquisitionDate
    - BusinessCombinationBargainPurchaseGainRecognizedDescription
    - BusinessCombinationStepAcquisitionEquityInterestInAcquireeDescription
    - BusinessCombinationStepAcquisitionEquityInterestInAcquireeIncludingSubsequentAcquisitionPercentage
    - BusinessCombinationStepAcquisitionEquityInterestInAcquireePercentage
    - BusinessAcquisitionEquityInterestIssuedOrIssuableDescription
    - BusinessAcquisitionEquityInterestIssuedOrIssuableBasisForDeterminingValue
    - BusinessAcquisitionEquityInterestsIssuedOrIssuableNumberOfSharesIssued
    - BusinessAcquisitionEquityInterestIssuedOrIssuableValueAssigned
    - BusinessCombinationContingentConsiderationArrangementsDescription
    - BusinessCombinationContingentConsiderationArrangementsBasisForAmount
    - BusinessCombinationContingentConsiderationArrangementsRangeOfOutcomesValueHigh
    - BusinessCombinationContingentConsiderationArrangementsRangeOfOutcomesValueLow
    - BusinessCombinationContingentConsiderationArrangementsRangeOfOutcomesInestimable
    - BusinessCombinationContingentConsiderationArrangementsRangeOfOutcomesMaximumUnlimited

### Discussion of Version 17 DQC Rules 
#### Summary of Rules ([.zip of rule submission forms](v17-public-review.zip) proposed for public review)

**DQC_0125 - Lease Cost Cannot be Negative** 
This rule identifies those cases where the lease cost is negative and no Sublease Income is reported. Lease costs can be negative in those cases where the lease is sub leased to another party and the sublease income exceeds the lease cost.

This rule uses the same logic as rule 15 except that it adds an additional check to ensure that the element SubleaseIncome has been reported in the same period.

**DQC_0126 - FS Calculation Check with Non Dimensional Data** 
This rule identifies those cases where the calculations defined for the financial statements in the company provided calculation linkbase do not match the actual values reported. The rule checks all networks that contain the text '- Statement -' in the definition.  It excludes any statements that are not the Balance Sheet, Income Statement and Cash Flow Statement.  The Statement of Changes in Shareholders Equity is not covered by this rule.

This rule only applies to those facts that are reported in the company's required context (current reporting context). This means prior periods are not checked. This eliminates the possibility of generating false positives on incomplete periods. It is assumed that the required context for each statement includes all the facts to make each report a complete calculation set.

This rule only operates on those financial statements that are not defined as an XBRL table using dimensions to represent values on the statement. This rule checks if a definition linkbase is defined for the statement. If it is not then the rule will proceed to execute. The absence of dimensions means that the rule will only add those values with no dimensions associated with them.

The rule works through every element in the statement and checks if it has any calculation children. If it does it takes the values of the children in the default and checks that they add to the parent value.

**DQC_0127 - Incorrect Dimensional Item Used on Financial Statements** 
This rule identifies those cases where the dimensional structures defined for the financial statements in the company provided definition linkbase do not match the actual values reported. The rule checks all networks that contain the text '- Statement -' in the network definition description.  It excludes any statements that are not the Balance Sheet, Income Statement and Cash Flow Statement.  The Statement of Changes in Shareholders Equity is not covered by this rule.

The rule has two components.  The first component checks those statements where no dimensions are defined and the second component checks those statements where dimensions are defined.

**DQC_0128 - Dimensional Values Larger than the Default** 
This rule identifies those facts on specific dimensions and checks the values are smaller than the default value with no dimensions. The rule identifies a list of dimensions that should not have negative values and determines if any of the dimensionalized monetary values are greater than the default value.

The rule only checks those concepts that are monetary items that are also items that cannot ever be reported with a negative value. This uses the same list of elements used by DQC_0015 for validating negative items.

The rule also only compares the two values where the decimals of each of the values is the same.

The rule only checks dimensionalized values that appear on the following axes:

  - PropertyPlantAndEquipmentByTypeAxis, 
  - StatementClassOfStockAxis, 
  - LongtermDebtTypeAxis, 
  - srt:ProductOrServiceAxis, 
  - FiniteLivedIntangibleAssetsByMajorClassAxis, 
  - DebtInstrumentAxis

**DQC_0129 - Dimensional Equivalents IFRS** 
This rule evaluates whether a fact expressed with no dimensions is equal to the same fact expressed in a table with dimensions. This can occur when fact values are represented in a table format in one part of the financial statements and the same value is expressed without using a table in a separate part of the financial statements. For example, the value of Additional Paid in Capital is represented as a line item on the face of the Balance Sheet with no dimensions and as Stockholders Equity as a line item with an Additional Paid in Capital Member in the Statement of Shareholders Equity.

In addition this rule determines if the dimensional value should be the inverse of the same value represented as a line item. For example, the value of Treasury Stock on the Balance Sheet will be a positive value but the value of Stockholders Equity with the Treasury Stock Member in the Statement of Shareholders Equity will be a negative value.

**DQC_0130 - Earnings Per Share Calculation IFRS** 
This rule evaluates if the value reported for earnings per share metrics matches the value calculated from its components.  The rule reperforms the calculation for the following elements using defined numerators and denominators. This rule evaluates if the value reported for earnings per share metrics matches the value calculated from its components.  The rule reperforms the calculation for the following elements using the defined numerators and denominators. If any of the components of the calculation are missing then the rule will not run. The values are compared using a tolerance of 4 based on the decimals used.

### Trends in Filings
  - Transition elements
  - Inconsistent dimensions (face financial statements)
  - Inline filings - lack of review of EDGAR renderer
  - Analysis of DQC errors by rule

### IFRS/ESEF Alignment
  - Inconsistent requirements (e.g., extension abstracts)
  - IFRS/DQCRT

### Conclusion of Public Session

### Future Meetings
  - January 19, 2022
  - March 23, 2022 (with SEC staff)
  - June 29, 2022
  - September 21, 2022 (with SEC staff)
______________________
