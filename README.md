# Create Fhir Resources
The whole idea behind this documentation is to be able to explore the various resources enabled by fhir standard. I used the following the following tools to play around with fhir;-
 1. vscode
 2. postman: to make rest calls to the fhir server.

## The steps i have followed to created the resources are;

-  Download the Json Fhir Schema (http://hl7.org/fhir/fhir.schema.json.zip).
-  Create the **CreateFhirResources** folder.
-  Open the CreateFhirResources folder in vscode.
-  Copy the **json Fhir Schema** extract insode the folder
-  Click **Ctrl + Shift + P** in order to choose the **Preferences: Open Workspace settings(Json)** option to generate the *settings.json* file.
-  Then type the following code (below)
```
{
    "json.schemas": [
        {
            "fileMatch": [
                "*.fhir.json"
            ],
            "url": "./fhir.schema.json"
        }
    ]
}
```


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


# Test the Patient.fhir.json resource
- When i make a POST request to the Hapi Fhir server with the patient.fhir.json(https://github.com/mherman22/CreateFhirResources/blob/main/patientResource/patient.fhir.json) using http://hapi.fhir.org/baseR4/Patient in PostMan, i get the result shown below.

```{
    "resourceType": "Patient",
    "id": "3053315",
    "meta": {
        "versionId": "1",
        "lastUpdated": "2022-06-02T09:04:40.617+00:00"
    },
    "text": {
        "status": "generated",
        "div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"><div class=\"hapiHeaderText\">Herman <b>MUHEREZA </b></div><table class=\"hapiPropertyTable\"><tbody><tr><td>Address</td><td><span>KampalaCity </span><span>Uganda </span></td></tr><tr><td>Date of birth</td><td><span>27 June 1996</span></td></tr></tbody></table></div>"
    },
    "name": [
        {
            "use": "official",
            "family": "Muhereza",
            "given": [
                "Herman"
            ]
        }
    ],
    "telecom": [
        {
            "system": "phone",
            "value": "0777041946",
            "use": "mobile"
        },
        {
            "system": "email",
            "value": "hermanmuhereza22@gmail.com"
        }
    ],
    "gender": "male",
    "birthDate": "1996-06-27",
    "address": [
        {
            "city": "KampalaCity",
            "district": "Wakiso District",
            "country": "Uganda"
        }
    ],
    "maritalStatus": {
        "text": "single"
    }
}
```
- In order to make a GET request of the same patient resource, all i need to do is add http://hapi.fhir.org/baseR4/Patient/{id}, i.e http://hapi.fhir.org/baseR4/Patient/3053315

