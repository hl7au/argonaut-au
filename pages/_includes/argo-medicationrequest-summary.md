#### Complete Summary of the Mandatory Requirements

1.  One date in `MedicationRequest.dateWritten`
1.  One status in `MedicationRequest.status` which has an [required](http://hl7.org/fhir/terminologies.html#required) binding to:
-   [MedicationRequestStatus] value set
1.  One patient reference in `MedicationRequest.patient`
1.  One practitioner in `MedicationRequest.prescriber`
1.  One medication via `MedicationRequest.medicationCodeableConcept` or `MedicationRequest.medicationReference`   
     -  `MedicationRequest.medicationCodeableConcept` has an [extensible](http://hl7.org/fhir/terminologies.html#extensible) binding to [Medication Clinical Drug (RxNorm)]

  [Medication Clinical Drug (RxNorm)]: ValueSet-medication-codes.html
  [MedicationRequestStatus]: http://hl7.org/fhir/ValueSet-medication-order-status.html
[MedicationStatementStatus]: http://hl7.org/fhir/ValueSet-medication-statement-status.html
