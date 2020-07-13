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
X-Frame-Options: SAMEORIGIN
X-XSS-Protection: 1; mode=block
X-Content-Type-Options: nosniff
X-Download-Options: noopen
X-Permitted-Cross-Domain-Policies: none
Referrer-Policy: strict-origin-when-cross-origin
Content-Type: application/json; charset=utf-8
ETag: W/"c356a3ebd4d3ba91a885300d0601b0c4"
Cache-Control: max-age=0, private, must-revalidate
Set-Cookie: _buslnk_session=MdA8c86%2FAvx0F4q5JNEVV8LeoaBxCAW0zzA2327YXsQmIfk48INjqaCL4v71SZScUB77N0H9TpLecnIQ3ZaSLVDoiw0nCPMVCTG344xCcqDx5dsQwHBaIGBOQRmBXYLn1x9QXeidenA2CZ%2BE36FhBWpYbng73vaptBErYQOpL4Xyr8UzO7rl--MoB0%2FdgS2v9j18PK--5HWGMQzsbGRoBS%2FBvDjfgQ%3D%3D; path=/; HttpOnly
X-Request-Id: a90ba369-e96c-42f5-a9c6-3b07fa35ecd0
X-Runtime: 0.011196
Content-Length: 314
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