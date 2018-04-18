
-----------

**`GET /MedicationRequest?patient={id}`**

Example:

[GET https://fhir-open-api-dstu3.smarthealthit.org/MedicationRequest?patient=1137192](https://fhir-open-api-dstu3.smarthealthit.org/MedicationRequest?patient=1137192)

*Implementation Notes:*  Search for all MedicationRequest resources for a patient. Fetches a bundle of all MedicationRequest resources for the specified patient  [(how to search by reference)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

-----------

`GET /MedicationRequest?patient={id}&_include=MedicationRequest:medication`
**Example:**

[GET http://fhirtest.uhn.ca/baseDstu3/MedicationRequest?patient=1137192&_include=MedicationRequest:medication](http://fhirtest.uhn.ca/baseDstu3/MedicationRequest?patient=14676&_include=MedicationRequest:medication)

*Support:* Mandatory for client to support search by patient using the include parameter.  Optional for server to support.

*Implementation Notes:*  Used when the server application represents the medication with an external reference to  a Medication resource. This searches for all MedicationRequest resources for a patient and returns a Bundle of all MedicationRequest and Medication resources for the specified patient.  [(how to search by reference)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

  [(how to search by reference)]: http://hl7.org/fhir/STU3/search.html#reference
  [(how to search by token)]: http://hl7.org/fhir/STU3/search.html#token
  [Composite Search Parameters]: http://hl7.org/fhir/search.html#combining
  [(how to search by date)]: http://hl7.org/fhir/STU3/search.html#date
