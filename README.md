# Create Fhir Resources
The steps i have followed to created the resources are;

-  Download the Json Fhir Schema (http://hl7.org/fhir/fhir.schema.json.zip).
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

