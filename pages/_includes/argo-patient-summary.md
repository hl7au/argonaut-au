#### Complete Summary of the Mandatory Requirements


1.  One or more medical record numbers in `Patient.identifier`
    -   each Patient.identifier must have:
        -   an `identifier.system`
        -   an `identifier.value` that is unique within the system.

2.  One or more names in `Patient.name`
    -   each Patient.name must have:
        -   a `name.family`
        -   a `name.given`

3.  One administrative gender in `Patient.gender`
    -   Patient.gender is bound to [AdministrativeGender] Value set (Code Set)

  [AdministrativeGender]: http://hl7.org/fhir/ValueSet-administrative-gender.html


#### Summary of the Must Support Requirements

Additionally the following data-elements must be supported. See the Argonaut definition of [Must Support].

1.  A date of birth in `Patient.birthDate`
2.  One or more languages spoken in `Patient.communication.language` which has an [extensible](http://hl7.org/fhir/terminologies.html#rextensible) binding to:
    -    [Common Languages] Note: The extensibility is limited to [All Languages]
3.  One indigenous status code in  `Patient.extension`= [Australian Indigenous Status Extension] 


  [Common Languages]: http://build.fhir.org/ValueSet-languages.html
  [All Languages]: http://build.fhir.org/all-languages.html
  [Australian Indigenous Status Extension]: http://fhir.hl7.org.au/fhir/base2017Sep/StructureDefinition-indigenous-status.html
  [Must Support]: definitions.html#must-support
