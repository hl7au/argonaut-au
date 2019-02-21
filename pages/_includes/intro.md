## Australian Argonaut Data Query IG

 The Australian Argonaut Data Query IG is based upon the core **[FHIR STU3 API]** and documents:

 - Security and Authorization
 - Data element query of the ONC Common Clinical Data Set
 - Document query of static documents

This Implementation Guide is the Australian Adaptation of the [US argonaut implementation guide](http://www.fhir.org/guides/argonaut/r2/). 
To see the changes between this implementation guide and the US base, use the "Compare to US argonaut" link at the bottom of each page.

#### Use Cases

This specification describes four use cases and sets search expectations for each. For complete details and background, see [Use Cases] for the Argonaut Project.

1.  Patient  uses  provider-approved  web  application  to  access  health  data
2.  Patient  uses  provider-­approved  mobile  app  to  access  health  data
3.  Clinician  uses  provider­-approved  web  application  to  access  health  data
4.  Clinician  uses  provider­-approved  mobile  app  to  access  health  data

Note, the Common MU Data Set referenced in the Use Cases is now the ONC 2015 Common Clinical Data Set .

[Use Cases]: http://argonautwiki.hl7.org/images/e/ec/Argonaut_UseCasesV1-1.pdf

#### Security

-----------------------------------------------

Argonaut uses SMART on FHIR authorization for apps that connect to EHR data. For details, see [SMART Application Launch Framework Implementation Guide] and the [Useful Argonaut Links].

[SMART Application Launch Framework Implementation Guide] :  http://hl7.org/fhir/smart-app-launch
  
[Useful Argonaut Links] : http://www.fhir.org/AU/Argonaut-Links

#### Data Element Query

  ----------------------

  The Argonaut data element query IG is intended to meet the 2015 Edition certification criterion for Patient Selection 170.315(g)(7) and Application Access – Data Category Request 170.315(g)(8). They were created for each of the 2015 Edition Common Clinical Data Set. Where applicable they are based on the HL7 U.S. [Data Access Framework (DAF) FHIR STU3 Implementation Guide]. However, the Argonaut use case and requirements per resource are a subset of those of the DAF implementation guide.

  The table below lists the FHIR Resources used for the corresponding 2015 Edition Common Clinical Data Set (CCDS) Data elements:

  No| CCDS Data Element | FHR Resource
  ---|---|---|
  (1) |  Patient Name | Patient
  (2) |  Sex | Patient
  (3) |  Date of birth | Patient
  (4) |  Race | Patient
  (5) |  Ethnicity | Patient
  (6) |  Preferred language | Patient
  (7) |  Smoking status | Observation
  (8) |  Problems | Condition
  (9) |  Medications | Medication, MedicationStatement, MedicationRequest
  (10) |  Medication allergies | AllergyIntolerance
  (11) |  Laboratory test(s) | Observation, DiagnosticReport
  (12) |  Laboratory value(s)/result(s) | Observation, DiagnosticReport
  (13) |  Vital signs | Observation
  (14) |  (no longer required) | -
  (15) |  Procedures | Procedure
  (16) |  Care team member(s) | CarePlan
  (17) |  Immunizations | Immunization
  (18) |  Unique device identifier(s) for a patient’s implantable device(s) | Device
  (19) |  Assessment and plan of treatment | CarePlan
  (20) |  Goals | Goal
  (21) |  Health concerns | Condition


  The Argonaut Profiles for each of the data element queries is listed below.  Each profile defines the minimum mandatory elements, extensions and terminology requirements that **MUST** be present. Requirements and guidance are given in the profile narrative summary. A formal hierarchical table that presents a [logical view] of the content in both a differential and snapshot view is also provided along with references to appropriate terminologies and examples.

  -  [Argonaut AllergyIntolerance Profile](StructureDefinition-argo-allergyintolerance.html)
  -  [Argonaut CarePlan Profile](StructureDefinition-argo-careplan.html)
  -  [Argonaut CareTeam Profile](StructureDefinition-argo-careteam.html)
  -  [Argonaut Condition Profile](StructureDefinition-argo-condition.html)
  -  [Argonaut Device Profile](StructureDefinition-argo-device.html)
  - Laboratory Tests and Results
     -  [Argonaut DiagnosticReport Profile](StructureDefinition-argo-diagnosticreport.html)
     -  [Argonaut Observation Results Profile](StructureDefinition-argo-observationresults.html)
  -  [Argonaut Goal Profile](StructureDefinition-argo-goal.html)
  -  [Argonaut Immunization Profile](StructureDefinition-argo-immunization.html)
  - Medications
     -  [Argonaut Medication Profile](StructureDefinition-argo-medication.html)
     -  [Argonaut MedicationRequest Profile](StructureDefinition-argo-medicationrequest.html)
     -  [Argonaut MedicationStatement Profile](StructureDefinition-argo-medicationstatement.html)
  -  [Argonaut Patient Profile](StructureDefinition-argo-patient.html)
  -  [Argonaut Procedure Profile](StructureDefinition-argo-procedure.html)
  -  [Argonaut Smoking Status Observation Profile](StructureDefinition-argo-smokingstatus.html)
  -  [Argonaut Vital Signs Observation Profile](StructureDefinition-argo-vitalsigns.html)

  *Note on Searches based on a date or date range:*

  1. Allergies, Immunizations, Medications, Problems and Health Concerns, UDI, Smoking Status do not require a date range search since a system should return all relevant resources.
  1. Date range search requirements are included in the Quick Start section for the following resources - Vital Signs, Laboratory Results, Goals, Procedures, and Assessment and Plan of Treatment.


#### Document Query

 ------------------

 The Argonaut Document Query Implementation guide defines how a provider or patient can retrieve a patient's existing clinical document - specifically, transition of care and patient summary C-CDA [CCD documents] required for Meaningful Use.  However other document formats, such as PDF, can be retrieved too. These are exposed in FHIR using a [DocumentReference] Resource:  to index/search for them. This guide provides the minimal requirements to fetch a URL link to either a) patient's existing documents which have been indexed or b) a “virtual” documents such as a CCD that could be created “on-demand”.

 The Document itself can be subsequently retrieved using the link provided from the DocumentQuery search results. The link could be, for example, a [FHIR endpoint] (FHIR STU3) to a [Binary Resource]  or some other document repository. The details of how to retrieve the document are not covered in this guide.

 **Use Case**

 Patient or Provider search for a patient's Documents

 **Example Search**

 -   Locate a patient's CCD document from a recent or current encounter

 **Assumptions and Preconditions**

 -   Initial search for a reference to a document instead of documents itself (retrieval of actual document is a two-step process)
 -   Documents may or may not already exist and be indexed prior to the search
 -   Document references may be created “on-demand” when requested
 -   Documents may be created “on-demand” when requested
 -   Details of document retrieval is out of scope

**Requirements**

The [Argonaut DocumentReference Profile](StructureDefinition-argo-documentreference.html) defines the minimum mandatory elements, extensions and terminology requirements that **MUST** be present.  Requirements and Guidance are given in a simple narrative summary. A formal hierarchical table
that presents a [logical view:  of the content in both a differential and snapshot view is also provided along with references to appropriate terminologies and examples.


[FHIR endpoint]: http://hl7.org/fhir/http.html
[Binary Resource]: http://hl7.org/fhir/STU3/binary.html
[DocumentReference]: http://hl7.org/fhir/STU3/documentreference.html
[CCD documents]: https://en.wikipedia.org/wiki/Continuity_of_Care_Document
[FHIR STU3 API]: http://hl7.org/fhir/STU3/index.html
[Data Access Framework]: http://hl7.org/fhir/daf/daf.html
[logical view]: http://hl7.org/fhir/formats.html
[Data Access Framework (DAF) FHIR STU3 Implementation Guide]: http://hl7.org/fhir/STU3/daf/daf.html
