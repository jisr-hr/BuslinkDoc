---
title: "Fetch Processed File"
metaTitle: "Payroll Process"
metaDescription: "Payroll Process"
---

Upload Payroll File

## EndPoint
**GET** : `/api/v1/payroll_processes/:id.json`

Name                                   | Description                                 | Required/Optional
-------------------------------------- | ------------------------------------------- | ------------------------
id | The id for the payroll process for which file to be requested      | Required
file_type | Type of the file (result, pval) that needs to be downloaded      | Optional

--------------------------------------------------------------------------------

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
curl --location --request GET 'localhost:3001/api/v1/payroll_processes/PAX2004290040482.json?file_type=result' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiI0MTZlNTk0NC01OWZmLTRkNjItOTQ4Ni0yMzgxODE4ZTkzMzUiLCJzdWIiOiI0Iiwic2NwIjoiYWNjb3VudCIsImF1ZCI6bnVsbCwiaWF0IjoxNTk1MjUwNjgyLCJleHAiOjE1OTUyNTA5ODJ9.W_n4Iks62McaYt1KNhBHxkopcq2eGmivtVoVAosTvOk'
```

--------------------------------------------------------------------------------

## Success Response

Status Code - 201 Created

```csv
Payroll File Transactions Validation Result
File ID: PAX1908290032054
File Description:
CIF: 13262
Number Of Records: 1
Salary Transfer Date: 2019-09-28
Fund Date: 2019-10-05
Total Amount: 10
Account Number: 68200013262000
Header Errors Description:

Line number,Original line,Error Description
2,"1,1,1,علي العمري,6825522222200,No,INMA,SA,10,SAR,1,/Payroll/,BANK ACCOUNT,,,,,,,,,,,,,1812678017","Successful Operation",
```

--------------------------------------------------------------------------------

## Expected Errors
Status Code - 404 Not Found

```json
{
  "request_id"=>"jisr95DA29857901725ECB4E13CE26AA0E0F",
  "description"=>"Failure operation(404)",
  "body"=>nil,
  "success"=>false
}
```