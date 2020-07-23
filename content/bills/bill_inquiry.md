---
title: "Bill Inquiry"
metaTitle: "Bills"
metaDescription: "Bills"
---

Bill Inquiry

## EndPoint
**GET** : `/api/v1/bill_payments.json`

Name                                   | Description                                 | Required/Optional
-------------------------------------- | ------------------------------------------- | ------------------------
biller_name | Biller identifier Like (stc, sec, zain and mobily)| Required
billing_acct | Billing account that supposed to be paid      | Required

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
curl --location --request GET 'integrator.clicksandbox.com/api/v1/bill_payments.json' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiIxMWFjZWM3Mi1iNjM0LTQwODUtODY2Yy1hYjQ0YjI0Yjg0OWYiLCJzdWIiOiI0Iiwic2NwIjoiYWNjb3VudCIsImF1ZCI6bnVsbCwiaWF0IjoxNTkxNjE3MDYyLCJleHAiOjE1OTE2MTczNjJ9.icIFpRzm_h6hCl1eYlkinTQDSWCd05nk3DXLBd0QRoo' \
--form 'billing_acct=12*****0001' \
--form 'biller_name=mobily'
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