---
title: "Customer Accounts Transfers"
metaTitle: "Syntax Highlighting is the meta title tag for this page"
metaDescription: "This is the meta description for this page"
---

Customer Accounts Transfers API

## EndPoint
**POST** : `/api/v1/customer_accounts_transfers.json`

Name                                   | Description                                 | Required/Optional
-------------------------------------- | ------------------------------------------- | ------------------------
receiver_account_number | The account number of the beneficiary      | Required
amount                              | The transaction amount in SAR that will be transfered to the beneficiary account              | Required
description                              | Description of the transaction which will reflect in the sender's bank statement, max 16 characters              | Optional
memo                              | Memorization of the transaction which will reflect in the receiver's bank statement, max 105 characters              | Optional
payment_description |  Payment Description , max 140 characters | Optional

## Headers
```powershell
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiI1NjU4NDM5My1jODM1LTQ4N2MtOTI3MS1mMmVkOWZiZDJhYTAiLCJzdWIiOiI5Iiwic2NwIjoiYWNjb3VudCIsImF1ZCI6bnVsbCwiaWF0IjoxNTkwOTE5MDk4LCJleHAiOjE1OTA5MTkzOTh9.5ibcQqGhu-_Jdn7KObfPY_0H3wLh3GXTVfMAceJO98w
Content-Type: application/json
Host: example.org
Cookie:
```
## Example Request

```powershell
curl --location --request POST 'integrator.clicksandbox.com/api/v1/customer_accounts_transfers.json' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiIxMWFjZWM3Mi1iNjM0LTQwODUtODY2Yy1hYjQ0YjI0Yjg0OWYiLCJzdWIiOiI0Iiwic2NwIjoiYWNjb3VudCIsImF1ZCI6bnVsbCwiaWF0IjoxNTkxNjE3MDYyLCJleHAiOjE1OTE2MTczNjJ9.icIFpRzm_h6hCl1eYlkinTQDSWCd05nk3DXLBd0QRoo' \
--data-raw '{
	"receiver_account_number": "***************",
	"amount": 212,
	"description": "by clickappp",
	"payment_description": "Hello, Demo transfered money",
	"memo": "Hello, Demo transfered money"
}'
```

--------------------------------------------------------------------------------

## Success Response

Status Code - 201 Created

```json
{
  "request_id"=>"jisr34E2AEFCA9961536B85E5E254EFE7A45",
  "description"=>"Successful operation",
  "body"=>{
    "curr_bal"=>"17494055114",
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
    "stmt_entry_id"=>"190857188765738.05"
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
  "description"=>"Duplicate Transaction",
  "body"=>nil,
  "success"=>false
}
```