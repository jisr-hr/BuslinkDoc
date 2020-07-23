---
title: "Payroll Process"
metaTitle: "Payroll Process"
metaDescription: "Payroll Process"
---

Upload Payroll File

## EndPoint
**POST** : `/api/v1/payroll_processes.json`

Name                                   | Description                                 | Required/Optional
-------------------------------------- | ------------------------------------------- | ------------------------
file | The file for the payroll process to be executed      | Required

--------------------------------------------------------------------------------

## File Structure

![File Structure Sample](./file_structure_sample.png)
## Headers
```powershell
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiI1NjU4NDM5My1jODM1LTQ4N2MtOTI3MS1mMmVkOWZiZDJhYTAiLCJzdWIiOiI5Iiwic2NwIjoiYWNjb3VudCIsImF1ZCI6bnVsbCwiaWF0IjoxNTkwOTE5MDk4LCJleHAiOjE1OTA5MTkzOTh9.5ibcQqGhu-_Jdn7KObfPY_0H3wLh3GXTVfMAceJO98w
Content-Type: application/json
Host: example.org
Cookie:
```

--------------------------------------------------------------------------------

## Example Request

```powershell
curl --location --request POST 'localhost:3001/api/v1/payroll_processes.json' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiI0MTZlNTk0NC01OWZmLTRkNjItOTQ4Ni0yMzgxODE4ZTkzMzUiLCJzdWIiOiI0Iiwic2NwIjoiYWNjb3VudCIsImF1ZCI6bnVsbCwiaWF0IjoxNTk1MjUwNjgyLCJleHAWEEDF1OTUyNTA5ODJ9.W_n4Iks62McaYt1KNhBHxkopcq2eGmivtVoVAosTvOk' \
--form 'file=@/Path/to/file/filename.csv'
```

--------------------------------------------------------------------------------

## Success Response

Status Code - 201 Created

```json
{
  "request_id"=>"jisr53E2AEFCA9961536B85E5E254EAA7A65",
  "description"=>"Successful operation",
  "body"=>{
    "desc"=>{},
    "file_id"=>"PAX1908290032054"
  },
  "success"=>true,
  "file_upload"=>{
    "request_id"=>"jisr53E2AEFCA9961536B85E5E254EAA7A65",
    "sub_directory_path"=>"1586021799_53E2AEFC"
  }
}
```

--------------------------------------------------------------------------------

## Expected Errors
Status Code - 422 Unprocessable Entity

```json
{
  "request_id"=>"jisr95DA29857901725ECB4E13CE26AA0E0F",
  "description"=>"Failure operation(00)",
  "body"=>nil,
  "success"=>false,
  "file_upload"=>{
    "request_id"=>"jisr95DA29857901725ECB4E13CE26AA0E0F",
    "sub_directory_path"=>"1586021799_95DA2985"
  }
}
```