---
title: "Intra Bank Transfers"
metaTitle: "Syntax Highlighting is the meta title tag for this page"
metaDescription: "This is the meta description for this page"
---

InterBank Transfers API

## EndPoint
**POST** : `/api/v1/intra_bank_transfers.json`

Name                                   | Description                                 | Required/Optional
-------------------------------------- | ------------------------------------------- | ------------------------
receiver_account_number | The account number of the beneficiary      | Required
amount                              | The transaction amount in SAR that will be transfered to the beneficiary account              | Required
description                              | Description of the transaction which will reflect in the sender's bank statement, max 16 characters              | Optional
memo                              | Memorization of the transaction which will reflect in the receiver's bank statement, max 105 characters              | Optional

## Headers
```powershell
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiI1NjU4NDM5My1jODM1LTQ4N2MtOTI3MS1mMmVkOWZiZDJhYTAiLCJzdWIiOiI5Iiwic2NwIjoiYWNjb3VudCIsImF1ZCI6bnVsbCwiaWF0IjoxNTkwOTE5MDk4LCJleHAiOjE1OTA5MTkzOTh9.5ibcQqGhu-_Jdn7KObfPY_0H3wLh3GXTVfMAceJO98w
Content-Type: application/json
Host: example.org
Cookie:
```
## Example Request

```powershell
curl --location --request POST 'integrator.clicksandbox.com/api/v1/intra_bank_transfers.json' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiIxMWFjZWM3Mi1iNjM0L*************************6bnVsbCwiaWF0IjoxNTkxNjE3MDYyLCJleHAiOjE1OTE2MTczNjJ9.**************************' \
--data-raw '{
	"receiver_account_number": "*********************",
	"amount": 213,
	"description": "by Jisr",
	"memo": "Hello, Demo transfered money to SecondDemo"
}'
```

--------------------------------------------------------------------------------

## Success Response

Status Code - 201 Created

```json
{
  "request_id"=>"jisr34E2AEFCA9961536B85E5E254EFE7A65",
  "description"=>"Successful operation",
  "body"=>{
    "curr_bal"=>"17494547738.38",
    "amt_debited"=>{
      "amt"=>"999.00",
      "cur_code"=>"SAR",
      "amt_lcl"=>"999.00"
    },
    "amt_credited"=>{
      "amt"=>"999.00",
      "cur_code"=>"SAR",
      "amt_lcl"=>"999.00"
    },
    "stmt_entry_id"=>"188839645428321.02"
  },
  "success"=>true
}
```

--------------------------------------------------------------------------------

## Expected Errors
Status Code - 422 Unprocessable Entity

```json
{
  "request_id"=>"jisrKULDEEP-ID-2",
  "description"=>"Previous transaction was successful",
  "body"=>nil,
  "success"=>false
}
```