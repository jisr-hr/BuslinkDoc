---
title: "Activation"
metaTitle: "Virtual Accounts Management"
metaDescription: "Virtual Accounts Management"
---

Activation

## EndPoint
**PUT** : `/api/v1/virtual_accounts/:bill_sequence_number/activate.json`

Name                                   | Description                                 | Required/Optional
-------------------------------------- | ------------------------------------------- | ------------------------
bill_sequence_number | The bill sequence number of VA that needs to be activated      | Required

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
curl --location --request PUT 'localhost:3001/api/v1/virtual_accounts/10143278/activate.json' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiI0MTZlNTk0NC01OWZmLTRkNjItOTQ4Ni0yMzgxODE4ZTkzMzUiLCJzdWIiOiI0Iiwic2NwIjoiYWNjb3VudCIsImF1ZCI6bnVsbCwiaWF0IjoxNTk1MjUwNjgyLCJleHAiOjE1OTUyNTA5ODJ9.W_n4Iks62McaYt1KNhBHxkopcq2eGmivtVoVAosTvOk'
```

--------------------------------------------------------------------------------

## Success Response

Status Code - 201 Created

```json
{
  "request_id"=>"jisr30521CABB0E779CC85DE7A3A35757386",
  "description"=>"Successful operation",
  "body"=>{
    "bill_seq_num"=>"10287693"
  },
  "success"=>true
}
```

--------------------------------------------------------------------------------

## Expected Errors
Status Code - 422 Unprocessable Entity

```json
{
  "request_id"=>"jisr5330D053C923BD80044254F3F8D73626",
  "description"=>"Bill sequence number not exists, Bill sequence number must exists, use a valid one.",
  "body"=>nil,
  "success"=>false
}
```
