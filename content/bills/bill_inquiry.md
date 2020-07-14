---
title: "Bill Inquiry"
metaTitle: "Syntax Highlighting is the meta title tag for this page"
metaDescription: "This is the meta description for this page"
---

InterBank Transfers API

## EndPoint
**POST** : `/api/v1/inter_bank_transfers.json`

Name                                   | Description                                 | Required/Optional
-------------------------------------- | ------------------------------------------- | ------------------------
receiver_account_number | The IBAN number of the beneficiary      | Required
receiver_bank_code                              | The beneficiary's bank code  | Required
amount                              | The transaction amount in SAR that will be transfered to the beneficiary account              | Required
receiver_full_name | Beneficiary's full name   | Required
description | Description of the transaction which will reflect in the sender's bank statement, max 16 characters | Optional
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
curl --location --request POST 'integrator.clicksandbox.com/api/v1/inter_bank_transfers.json' \
--form 'receiver_iban_account_number=SA6110000013347269006708' \
--form 'receiver_bank_code=NCBKSAJE' \
--form 'amount=999' \
--form 'receiver_full_name=MaJeD BoJaN' \
--form 'description=16chrs long'
```

--------------------------------------------------------------------------------

## Success Response

Status Code - 201 Created

```json
{
  "request_id"=>"jisr53E2AEFCA9961536B85E5E254EFE7A65",
  "description"=>"Successful operation",
  "body"=>{
    "curr_bal"=>"17494588740.73",
    "amt_debited"=>{
      "amt"=>"1006.35",
      "cur_code"=>"SAR",
      "amt_lcl"=>"1006.35"
    },
    "amt_credited"=>{
      "amt"=>"999.00",
      "cur_code"=>"SAR",
      "amt_lcl"=>"999.00"
    },
    "total_debited_fee_amt"=>"7.35",
    "stmt_entry_id"=>"VAL",
    "fee_info"=>{
      "fee_category"=>"2",
      "cur_amt"=>{
        "amt"=>"7.00",
        "cur_code"=>"SAR"
      }
    },
    "tax_info"=>{
      "tax_type"=>"1",
      "tax_amt"=>"0.35",
      "tax_percen"=>"5",
      "invoice_num"=>"ALIN-VAT36365040002299603"
    }
  },
  "success"=>true
}
```

--------------------------------------------------------------------------------

## Expected Errors
Status Code - 422 Unprocessable Entity

```json
{
  "request_id"=>"jisr53E2AEFCA9961536B85E5E254EFE7A65",
  "description"=>"Duplicate Transaction",
  "body"=>nil,
  "success"=>false
}
```