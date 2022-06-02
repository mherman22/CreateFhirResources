
# Test the Patient.fhir.json resource
When i make a POST request to the Hapi Fhir server with the patient.fhir.json(https://github.com/mherman22/CreateFhirResources/blob/main/patientResource/patient.fhir.json) using http://hapi.fhir.org/baseR4/Patient in PostMan, i get the result shown below.

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
}```

