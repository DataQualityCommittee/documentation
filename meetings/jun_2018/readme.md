# Data Quality Committee Meeting - June 27, 2018

### Introductions 
  
### Approval of Minutes

  + [April 25, 2018 Meeting Minutes](DRAFTDQCMeetingNotes04252018.docx?raw=true)

### Review and Approval of Release of DQC Rules and Guidance Version 7 for Public Review 
  + #### [DQC Rules index](https://github.com/DataQualityCommittee/dqc_us_rules/blob/v7/docs/README.md)

    **DQC_0067- Mutually Exclusive Elements** This rule identifies if elements associated with the new revenue recognition standards are used in conjunction with elements from the previous revenue recognition standard. 

    **DQC_0068 - Geographical Axis Used with Pension Line Items** This rule identifies those cases where the filer has reported the StatementGeographicalAxis in conjunction with a line item in the Compensation Related Costs and Retirement Benefits section of the taxonomy. 

    **DQC_0069 - Plan Asset Categories Component Members** This rule identifies those cases where the following elements have not been tagged with appropriate members and values and checks that they are tagged appropriately based on FASB guidance. These two elements must be used in conjunction with the axis DefinedBenefitPlanByPlanAssetCategoriesAxis.

      *   DefinedBenefitPlanPlanAssetsInvestmentWithinPlanAssetCategoryAmount
      *   DefinedBenefitPlanAmountOfEmployerAndRelatedPartySecuritiesIncludedInPlanAssets
    
    **DQC_0070 - Plan Asset Dimensional Aggregation** This rule aggregates the values of the Plan Asset categories on the DefinedBenefitPlanByPlanAssetCategoriesAxis.  The rule aggregates the values of the members and compares the total to the reported total for the default value of the axis. 

    **DQC_0071 - Revenue/Cost Single Member** This rule identifies if the revenue/cost elements RevenueFromContractWithCustomerIncludingAssessedTax, RevenueFromContractWithCustomerExcludingAssessedTax and CostOfGoodsAndServicesSold  have been used with the ProductOrServiceAxis for only one product or service represented by a single member on the product or service axis.

    **DQC_0072 - Plan Asset Categories Percentage** This rule identifies those cases where the element DefinedBenefitPlanPlanAssetsInvestmentWithinPlanAssetCategoryPercentage has not been tagged with appropriate members based on FASB guidance. This element must be used in conjunction with the axis DefinedBenefitPlanByPlanAssetCategoriesAxis.

    **DQC_0073 - Plan Asset Categories Permissible Line Items** This rule identifies when inappropriate line items are used with the Plan Asset Categories Axis. 

    **DQC_0074 - Nil Values on Typed Axis** This rule identifies when a nil value has been used inappropriately on the following typed axis.   RevenueRemainingPerformanceObligationExpectedTimingOfSatisfactionStartDateAxis

    **DQC_0075 - Revenue Tax Policy** This rule identifies those cases where the inappropriate revenue element is used in conjunction with the tax exclusion policy text block.

    **DQC_0076 - Performance Obligations With No Durations** This rule is intended to ensure that filers follow the guidance defined in the Revenue recognition implementation guide published by the FASB. The rule identifies those cases where the duration over which the performance obligation will be captured is not reported.  If either of the following two elements are reported with a value:

      1.  RevenueRemainingPerformanceObligationPercentage or
      1.  RevenueRemainingPerformanceObligation  
    
    with RevenueRemainingPerformanceObligationExpectedTimingOfSatisfactionStartDateAxis then the satisfaction period elements must have associated duration values.

    **DQC_077 - Satisfaction Period With No Satisfaction Start Date Axis** This rule checks if the satisfaction period elements have been used with RevenueRemainingPerformanceObligationExpectedTimingOfSatisfactionStartDateAxis.

    **DQC_0078 - Ownership Interest With No Ownership Axis** This rule identifies those cases where the ownership interest elements are not used with the ownership axis. This rule is intended to ensure that filers follow the implementation guidance defined in the Dimensional Modeling for Disclosures of Consolidated and Nonconsolidated Entities guide published by the FASB.

    __**Update to Existing DQC Rules**__

    **DQC_0014 - Negative Values With No Dimensions** Added the following elements to the rule
      *   FairValueMeasurementWithUnobservableInputsReconciliationLiabilityTransfersOutOfLevel3
      *   RevenueFromContractWithCustomerIncludingAssessedTax
      *   RevenueFromContractWithCustomerExcludingAssessedTax

    **DQC_0011 - Dimensional Equivalents** Change weight of the following element to from 1 to -1 AccumulatedOtherComprehensiveIncomeLossDefinedBenefitPensionAndOtherPostretirementPlansNetOfTax

  + #### [Dimensional Modeling Guidance - Legal Entities and Consolidations](https://github.com/DataQualityCommittee/documentation/blob/master/guidance/LegalEntitiesConsolidation.md)
  + #### [Revenue Recognition Guidance](https://github.com/DataQualityCommittee/documentation/blob/master/guidance/RevenueRecognition.md)


### DQC IFRS Rules

### Comment Letter to SEC

### Other Business/Future meetings

______________________
