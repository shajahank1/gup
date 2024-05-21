## API Specification: Get Institutes for Patient
> Description: This API retrieves all associated institutes for a given patient based on their civil ID.

### HTTP Method
- POST

### Endpoint
 ``` {BASEURL}/v2/getAppInstitutes ```

### Headers
- Authorization: Bearer d0816a77-af67-43fc-bad1-2edb2aae3dc5 - The Bearer token required for authentication.
### Request Body
```
{
  "civilId": 20134401
}
```
### Parameters:
- civilId (integer): The civil ID of the patient.
#### Successful Response
- HTTP Status Code: 200 (OK)

### Content-Type: application/json

## Body:

```
{
    "version": "v2",
    "code": 0,
    "message": "1 Records found",
    "result": [
        {
            "mpiId": 2704847,
            "estCode": "20068",
            "fhirPatientId": "67.20068.54124",
            "estPatientId": 54124,
            "activeYn": "Y",
            "estName": "Directorate General of Information Technology",
            "estShortName": "DGIT",
            "fhirEnabledYn": "N",
            "estTypeCode": 106,
            "estNameNls": "المديرية العامة لتقنية المعلومات",
            "newAppYn": "Y",
            "reschAppYn": "Y"
        }
    ]
}
```
## Fields:

- version (string): API version.
- code (integer): Status code of the operation.
- message (string): Description regarding the result.
- result (array): Array of institutes linked to the patient.
  - mpiId (integer): MPI ID of the institute.
  - estCode (string): Establishment code.
  - fhirPatientId (string): FHIR patient ID.
  - estPatientId (integer): Establishment's patient ID.
  - activeYn (string): Indicates if the record is active ('Y' for yes).
  - estName (string): Full name of the establishment.
  - estShortName (string): Short name of the establishment.
  - fhirEnabledYn (string): Indicates if FHIR is enabled ('N' for no).
  - estTypeCode (integer): Establishment type code.
  - estNameNls (string): Localized name of the establishment.
  - newAppYn (string): Indicates if new appointments are available ('Y' for yes).
  - reschAppYn (string): Indicates if rescheduling is available ('Y' for yes).
### Error Responses
- HTTP Status Code: 401 (Unauthorized)

### Content-Type: application/json
Body:
```
{
  "code": 401,
  "message": "Unauthorized: Access is denied due to invalid credentials."
}
```
HTTP Status Code: 404 (Not Found)

Content-Type: application/json
Body:
```
{
  "code": 404,
  "message": "No records found for the given civil ID."
}
```
> This document serves as a comprehensive guide for developers to understand how to integrate and troubleshoot interactions with this specific API endpoint.
