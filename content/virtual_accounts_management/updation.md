---
title: "Updation"
metaTitle: "Virtual Accounts Management"
metaDescription: "Virtual Accounts Management"
---

Deactivation

## EndPoint
**PUT** : `/api/v1/virtual_accounts/:bill_sequence_number.json`

Name                                   | Description                                 | Required/Optional
-------------------------------------- | ------------------------------------------- | ------------------------
due_amount | The amount that needs to be paid by the beneficiary      | Required
due_date | The due date of the payment in the format YYYY-MM-DD      | Required
bill_sequence_number | The bill sequence number of VA that needs to be updated | Required

## File Structure


## Headers
```powershell
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiI1NjU4NDM5My1jODM1LTQ4N2MtOTI3MS1mMmVkOWZiZDJhYTAiLCJzdWIiOiI5Iiwic2NwIjoiYWNjb3VudCIsImF1ZCI6bnVsbCwiaWF0IjoxNTkwOTE5MDk4LCJleHAiOjE1OTA5MTkzOTh9.5ibcQqGhu-_Jdn7KObfPY_0H3wLh3GXTVfMAceJO98w
Content-Type: application/json
Host: example.org
Cookie:
```
## Example Request

```powershell
curl --location --request PUT 'localhost:3001/api/v1/virtual_accounts/10143278' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiI0MTZlNTk0NC01OWZmLTRkNjItOTQ4Ni0yMzgxODE4ZTkzMzUiLCJzdWIiOiI0Iiwic2NwIjoiYWNjb3VudCIsImF1ZCI6bnVsbCwiaWF0IjoxNTk1MjUwNjgyLCJleHAiOjE1OTUyNTA5ODJ9.W_n4Iks62McaYt1KNhBHxkopcq2eGmivtVoVAosTvOk' \
--form 'due_date=2020-01-01' \
--form '='
```

--------------------------------------------------------------------------------

## Success Response

Status Code - 200 OK

```json
{
  "request_id"=>"jisr87E0C44D0FFF89380BFD3FF3C874993D",
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
  "request_id"=>"jisr726921B83E07AA7C44C08A2E76B331CF",
  "description"=>"Bill sequence number not exists, Bill sequence number must exists, use a valid one.",
  "body"=>nil,
  "success"=>false
}
```
