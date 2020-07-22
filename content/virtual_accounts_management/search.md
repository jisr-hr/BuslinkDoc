---
title: "Search"
metaTitle: "Syntax Highlighting is the meta title tag for this page"
metaDescription: "This is the meta description for this page"
---

Deactivation

## EndPoint
**GET** : `/api/v1/virtual_accounts.json`

## Parameters
Name                                   | Description                                 | Required/Optional
-------------------------------------- | ------------------------------------------- | ------------------------
merchant_bill_number | The bill number against which VA     | Optional
iban | Virtual Account IBAN that needs to be searched      | Optional
bill_state | Virtual Account status('Initial State', 'Active', 'Inactive') that needs to be searched| Optional
due_amount_from | The minimum due amount that needs to be paid by the beneficiary     | Optional
due_amount_to | The maximum due amount that needs to be paid by the beneficiary      | Optional
due_date_from | The minimum due date of the payment in the format YYYY-MM-DD     | Optional
due_date_upto | The maximum due date of the payment in the format YYYY-MM-DD     | Optional
created_from | The minimum created date of the VA in the format YYYY-MM-DD     | Optional
created_upto | The maximum created date of the VA in the format YYYY-MM-DD     | Optional
max_records | The maximum number of records in the result set      | Optional
records_offset | The number of records in the result set that needs to be skipped      | Optional
customer_official_id | This is the official ID of the customer(max length 32)     | Optional

## Response Fields

- `bill_dtl_status`

<ol>
<li> [BillPaid]: The bill is fully paid and the net due amount is set to zero</li>
<li>[BIllPartialPd]: One or more payments have been applied to the bill,but an outstanding balance remains</li>
<li>[BillOverPd]: The bill has a net due amount less than zero</li>
<li>[BillUnpaid]: No payments have been applied to the bill</li>
</ol>


## Headers
```powershell
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiI1NjU4NDM5My1jODM1LTQ4N2MtOTI3MS1mMmVkOWZiZDJhYTAiLCJzdWIiOiI5Iiwic2NwIjoiYWNjb3VudCIsImF1ZCI6bnVsbCwiaWF0IjoxNTkwOTE5MDk4LCJleHAiOjE1OTA5MTkzOTh9.5ibcQqGhu-_Jdn7KObfPY_0H3wLh3GXTVfMAceJO98w
Content-Type: application/json
Host: example.org
Cookie:
```
## Example Request

```powershell
curl --location --request GET 'localhost:3001/api/v1/virtual_accounts.json?iban=SA1905011999810010287895&customer_official_id=kuldeep-official-id10287528&bill_sequence_number=10291366' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJpZCI6MTIsIm5hbWUiOiJzdXBlcl9hZG1pbiIsInJvbGUiOiJzdXBlcl9hZG1pbiIsImVtYWlsIjoic3VwZXJfYWRtaW5AY2xpY2thcHBzLmNvIiwibW9iaWxlIjoiNzMzNjU5MzQ3IiwiY29kZV9jb3VudHJ5IjoiMDA5NjciLCJjYW5fbWFuYWdlX3BvbGljeSI6ZmFsc2UsImFjY2VzcyI6ImFkbWluIiwiaWF0IjoxNTk0NTM5NzQzLCJleHAiOjE1OTQ1Njg1NDN9.UeWiH905afRDZsNWlSTC_hhF2r0h5HZ2dwHYRTZ2pIA'
```

--------------------------------------------------------------------------------

## Success Response

Status Code - 201 Created

```json
{"request_id"=>"jisr8155EF42D4BF2014C41DC71AAB5B759D", "description"=>"Successful operation", "body"=>{"rec_ctrl_out"=>{"matched_recs"=>"1", "sent_recs"=>"1"}, "bms_bill_list"=>{"bms_bill_info"=>[{"mrchnt_id"=>"19998", "bill_seq_num"=>"10287528", "bill_num"=>"1049659324", "svc_id"=>"100", "pmt_type"=>"POST", "iban"=>"SA3405011999810010287528", "bill_state"=>"10", "bill_status_desc"=>"Active", "bill_dtl_status"=>"BillUnpaid", "due_amt"=>"0", "due_dt"=>"2019-07-21", "create_dt"=>"2019-07-16T15:04:02.000+00:00", "last_update_dt"=>"2019-07-16T15:04:02.000+00:00", "total_paid_amt"=>"0", "paid_amt_last_reset"=>"0", "cust_name"=>"husam almomani"}]}}, "success"=>true}
```

--------------------------------------------------------------------------------

## Expected Errors
Status Code -

```json
{}
```
