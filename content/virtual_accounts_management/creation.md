---
title: "Creation"
metaTitle: "Virtual Accounts Management"
metaDescription: "Virtual Accounts Management"
---

Creation

## EndPoint
**POST** : `/api/v1/virtual_accounts.json`

Name                                   | Description                                 | Required/Optional
-------------------------------------- | ------------------------------------------- | ------------------------
due_amount | The amount that needs to be paid by the beneficiary      | Required
merchant_bill_number | The bill number against which VA needs to be created      | Required
due_date | The due date of the payment in the format YYYY-MM-DD | Required
customer_official_id | This is the official ID of the customer(max length 32) | Required

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
curl --location --request POST 'localhost:3001/api/v1/virtual_accounts.json' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiI0MTZlNTk0NC01OWZmLTRkNjItOTQ4Ni0yMzgxODE4ZTkzMzUiLCJzdWIiOiI0Iiwic2NwIjoiYWNjb3VudCIsImF1ZCI6bnVsbCwiaWF0IjoxNTk1MjUwNjgyLCJleHAiOjE1OTUyNTA5ODJ9.W_n4Iks62McaYt1KNhBHxkopcq2eGmivtVoVAosTvOk' \
--form 'due_amount=222' \
--form 'merchant_bill_number=9dd0c327c7f0af22df0d1586fd854c81' \
--form 'due_date=2023-september-30' \
--form 'customer_official_id=official_id_1'
```

--------------------------------------------------------------------------------

## Success Response

Status Code - 201 Created

```json
{
  "request_id"=>"jisr8155EF42D4BF2014C41DC71AAB5B759D",
  "description"=>"Successful operation",
  "body"=>{
    "bill_seq_num"=>"10287693",
    "bill_iban"=>"SA0305011999910010287693"
  },
  "success"=>true
}
```

--------------------------------------------------------------------------------

## Expected Errors
Status Code - 422 Unprocessable Entity

```json
{
  "request_id"=>"jisr95DA29857901725ECB4E13CE26AA0E0F",
  "description"=>"Merchant bill number already exists, it can't be duplicated, use another one.",
  "body"=>nil,
  "success"=>false
}
```
