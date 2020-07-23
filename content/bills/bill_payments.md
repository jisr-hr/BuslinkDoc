---
title: "Bill Payments"
metaTitle: "Bills"
metaDescription: "Bills"
---

Bill Payments

## EndPoint
**POST** : `/api/v1/bill_payments.json`

Name                                   | Description                                 | Required/Optional
-------------------------------------- | ------------------------------------------- | ------------------------
biller_name | Biller identifier Like (stc, sec, zain and mobily)| Required
amount | The amount that needs to be paid by the beneficiary      | Required
bill_number | The bill number that supposed to be paid      | Required
due_date | The due date of the payment in the format YYYY-MM-DD     | Required
due_date | The processing date of the payment in the format YYYY-MM-DD      | Required
customer_mobile_number | The customer mobile number      | Optional
account_number | The account Number      | Optional

--------------------------------------------------------------------------------

## Supported bills
<ol>
<li>stc</li>
<li>sec</li>
<li>zain</li>
<li>mobily</li>
</ol>

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
curl --location --request POST 'integrator.clicksandbox.com/api/v1/bill_payments.json' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiIxMWFjZWM3Mi1iNjM0LTQwODUtODY2Yy1hYjQ0YjI0Yjg0OWYiLCJzdWIiOiI0Iiwic2NwIjoiYWNjb3VudCIsImF1ZCI6bnVsbCwiaWF0IjoxNTkxNjE3MDYyLCJleHAiOjE1OTE2MTczNjJ9.icIFpRzm_h6hCl1eYlkinTQDSWCd05nk3DXLBd0QRoo' \
--form 'customer_mobile_number=0506966507' \
--form 'processing_date=2019-09-09' \
--form 'due_date=2025-10-14' \
--form 'biller_name=sec' \
--form 'amount=100' \
--form 'bill_account=12232019000000017'
```

--------------------------------------------------------------------------------

## Success Response

Status Code - 201 Created

```json
{}
```

--------------------------------------------------------------------------------

## Expected Errors
Status Code - 422 Unprocessable Entity

```json
{
  "error"=>"Sorry!, You are not authroized to use this service.",
  "status"=>"forbidden"
}
```