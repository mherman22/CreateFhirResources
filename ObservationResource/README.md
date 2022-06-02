
# Test the Observation.fhir.json  resource
- When i make a POST request to the Hapi Fhir server with the Observation.fhir.json(https://github.com/mherman22/CreateFhirResources/blob/main/ObservationResource/observation.fhir.json) using http://hapi.fhir.org/baseR4/Observation in PostMan, i get the result shown below.

```
{
    "resourceType": "Observation",
    "id": "3060182",
    "meta": {
        "versionId": "1",
        "lastUpdated": "2022-06-02T11:02:56.415+00:00"
    },
    "status": "final",
    "code": {
        "coding": [
            {
                "system": "https://loinc.org/",
                "code": "15874-8",
                "display": "Glucose [Moles/volume] in Blood"
            }
        ]
    },
    "subject": {
        "reference": "Patient/3053315",
        "display": "Muhereza Herman"
    },
    "valueQuantity": {
        "value": 6.3,
        "unit": "mmol/1",
        "system": "http://unitsofmeasure.org",
        "code": "mmol/L"
    }
}
```
- In order to make a GET request of the same patient resource, all i need to do is add http://hapi.fhir.org/baseR4/Observation/{id}, i.e http://hapi.fhir.org/baseR4/Observation/3053315