#### Complete Summary of the Mandatory Requirements


1.  One patient reference in `MedicationStatement.patient`
1.  One date `MedicationStatement.dateAsserted`
1.  One status in `MedicationStatement.status` which has an [required](http://hl7.org/fhir/terminologies.html#required) binding to:
-   [MedicationStatementStatus] value set.
1.  One medication via `MedicationStatement.medicationCodeableConcept` or `MedicationStatement.medicationReference`   
-  `MedicationStatement.medicationCodeableConcept`.

#### Summary of the Must Support Requirements

1.  One date or period in `MedicationStatement.effectiveDateTime` or `MedicationStatment.effectivePeriod`


[MedicationRequestStatus]: http://hl7.org/fhir/ValueSet-medication-order-status.html
[MedicationStatementStatus]: http://hl7.org/fhir/ValueSet-medication-statement-status.html
