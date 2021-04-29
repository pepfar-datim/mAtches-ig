### Sample HIV QuestionnaireResponse
[QuestionnaireResponse](https://www.hl7.org/fhir/questionnaireresponse.html) provides a complete or partial list of answers (from uploaded data) in response to a previously mapped Questionnaire. WHen data is uploaded to mAtches, a QuestionnaireResponse FHIR bundle will be generated. Below is a sample QuestionnaireResponse;
```json
{
  "resourceType": "QuestionnaireResponse",
  "id": "PLM-HIV-QuestionnaireResponse-example",
  "questionnaire": "http://datim.org/fhir/Questionnaire/PLM-HIV-Questionnaire",
  "status": "completed",
  "item": [
    {
      "linkId": "/Patient",
      "text": "Patient ID",
      "item": [
        {
          "linkId": "/Patient/id",
          "text": "Patient ID",
          "answer": [{
              "valueString": "12345"
          }]
        },
        {
          "linkId": "/Patient/birthDate",
          "text": "Birth Date",
          "answer": [{
              "valueDate": "1999-04-19"
          }]
        },
        {
          "linkId": "/Patient/gender",
          "text": "Gender",
          "answer": [{
              "valueCoding": {
                  "system": "http://hl7.org/fhir/administrative-gender",
                  "code": "female"
              }
          }]
        }
      ]
    },
    {
      "linkId": "/Encounter",
      "text": "Encounter",
      "item": [
        {
          "linkId": "/Encounter/location",
          "text": "Location ID",
          "answer": [{
              "valueString": "aBKlrjL"
          }]
        }
      ]
    },
    {
      "linkId": "/Observation",
      "text": "Practitioner",
      "item": [
        {
          "linkId": "/Observation/performer",
          "text": "Practitioner ID",
          "answer": [{
              "valueString": "abcd-efg-hij-klm"
          }]
        },
        {
          "linkId": "/Observation/date",
          "text": "Observation Date",
          "answer": [{
              "valueDateTime": "2019-04-10T10:00:00.000Z"
          }]
        },
        {
          "linkId": "/Observation/viralLoad",
          "text": "Viral Load Count",
          "answer": [{
              "valueInteger": 400
          }]
        }
      ]
    },
    {
      "linkId": "/MedicationStatement",
      "text": "MedicationStatement",
      "item": [
        {
          "linkId": "/MedicationStatement/startDate",
          "text": "ART Start Date",
          "answer": [{
              "valueDateTime": "2019-03-22T09:00:00.000Z"
          }]
        }
      ]
    }
  ]
}
```