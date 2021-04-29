### Sample HIV Questionnaire
A [Questionnaire](https://www.hl7.org/fhir/questionnaire.html) is an organized collection of questions intended to gather information from patients, providers or other individuals involved in the healthcare domain.
For mAtches, the Questionnaire is used to map columns from the CSV or JSON data file. The map is used to generate QuestionnaireResponse when data is uploaded. Items in the sample Questionnaire below are to be mapped one-to-one with columns in the CSV file. 

```json
{
  "resourceType": "Questionnaire",
  "id": "PLM-HIV-Questionnaire",
  "url": "http://datim.org/fhir/Questionnaire/PLM-HIV-Questionnaire",
  "meta": {
    "profile": [ "http://hl7.org/fhir/uv/sdc/StructureDefinition/sdc-questionnaire-extract" ]
  },
  "name": "PLMHIVQuestionnaire",
  "title": "PLM Prototype Questionnaire - HIV",
  "status": "active",
  "item": [
    {
      "linkId": "/Patient",
      "text": "Patient ID",
      "type": "group",
      "item": [
        {
          "linkId": "/Patient/id",
          "text": "Patient ID",
          "type": "string",
          "definition": "http://datim.org/fhir/StructureDefinition/PLM-HIV-Patient#Patient.id"
        },
        {
          "linkId": "/Patient/birthDate",
          "text": "Birth Date",
          "type": "date",
          "definition": "http://datim.org/fhir/StructureDefinition/PLM-HIV-Patient#Patient.birthDate"
        },
        {
          "linkId": "/Patient/gender",
          "text": "Gender",
          "type": "choice",
          "answerValueSet": "http://hl7.org/fhir/ValueSet/administrative-gender",
          "definition": "http://datim.org/fhir/StructureDefinition/PLM-HIV-Patient#Patient.gender"
        }
      ]
    },
    {
      "linkId": "/Encounter",
      "text": "Encounter",
      "type": "group",
      "item": [
        {
          "linkId": "/Encounter/location",
          "text": "Location ID",
          "type": "string",
          "definition": "http://datim.org/fhir/StructureDefinition/PLM-HIV-Encounter#Encounter.location.location.identifier.value"
        }
      ]
    },
    {
      "linkId": "/Observation",
      "text": "Practitioner",
      "type": "group",
      "item": [
        {
          "linkId": "/Observation/performer",
          "text": "Practitioner ID",
          "type": "string",
          "definition": "http://datim.org/fhir/StructureDefinition/PLM-HIV-Observation#Observation.performer.identifier.value"
        },
        {
          "linkId": "/Observation/date",
          "text": "Observation Date",
          "type": "dateTime",
          "definition": "http://datim.org/fhir/StructureDefinition/PLM-HIV-Observation#Observation.effectiveDateTime"
        },
        {
          "linkId": "/Observation/viralLoad",
          "text": "Viral Load Count",
          "type": "integer",
          "definition": "http://datim.org/fhir/StructureDefinition/PLM-HIV-Observation#Observation.valueQuantity"
        }
      ]
    },
    {
      "linkId": "/MedicationStatement",
      "text": "MedicationStatement",
      "type": "group",
      "item": [
        {
          "linkId": "/MedicationStatement/startDate",
          "text": "ART Start Date",
          "type": "dateTime",
          "definition": "http://datim.org/fhir/StructureDefinition/PLM-HIV-MedicationStatement#MedicationStatement.effectivePeriod.start"
        }
      ]
    }
  ]
}
```