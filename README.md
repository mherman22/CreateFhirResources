## FHIR STANDARD
### What is fhir?
FHIR is an abbreviation for `Fast Healthcare Interoperability Resources` and can be defined as a standard describing resources and an API for exchanging electronic health records. The standard was created by the [Health Level Seven International](https://www.hl7.org/) (HL7) health-care standards organization.

FHIR builds on previous data format standards from HL7, like HL7 version 2.x and HL7 version 3.x. But it is easier to implement because it uses a modern web-based suite of API technology, including a HTTP-based RESTful protocol, and a choice of JSON, XML or RDF for data representation.[1] One of its goals is to facilitate interoperability between legacy health care systems, to make it easy to provide health care information to health care providers and individuals on a wide variety of devices from computers to tablets to cell phones, and to allow third-party application developers to provide medical applications which can be easily integrated into existing systems.

FHIR provides an alternative to document-centric approaches by directly exposing discrete data elements as services. For example, basic elements of healthcare like patients, admissions, diagnostic reports and medications can each be retrieved and manipulated via their own resource URLs.

`The philosophy behind FHIR is to build a base set of resources that, either by themselves or when combined, satisfy the majority of common use cases. FHIR resources aim to define the information contents and structure for the core information set that is shared by most implementations` HL7 states on its website.
## Create Fhir Resources
The whole idea behind this documentation is to be able to explore the various resources enabled by fhir standard. I used the following the following tools to play around with fhir;-
 1. vscode
 2. postman: to make rest calls to the fhir server.

## The steps i have followed to created the resources are;

-  Download the Json Fhir Schema [fhir schema](http://hl7.org/fhir/fhir.schema.json.zip).
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
- When i make a POST request to the Hapi Fhir server with the [Observation.fhir.json](https://github.com/mherman22/CreateFhirResources/blob/main/ObservationResource/observation.fhir.json) using [fhir observation resource](http://hapi.fhir.org/baseR4/Observation) in PostMan, i get the result shown below.

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
- In order to make a GET request of the same patient resource, all i need to do is add (http://hapi.fhir.org/baseR4/Observation/{id}), i.e (http://hapi.fhir.org/baseR4/Observation/3053315)


# Test the Patient.fhir.json resource
- When i make a POST request to the Hapi Fhir server with the [patient.fhir.json](https://github.com/mherman22/CreateFhirResources/blob/main/patientResource/patient.fhir.json) using [fhir patient resource](http://hapi.fhir.org/baseR4/Patient) in PostMan, i get the result shown below.

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
- In order to make a GET request of the same patient resource, all i need to do is add (http://hapi.fhir.org/baseR4/Patient/{id}), i.e (http://hapi.fhir.org/baseR4/Patient/3053315)

