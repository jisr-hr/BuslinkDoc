---
title: "Introductions"
metaTitle: "Buslink service"
metaDescription: "Buslink service"
---
## Envs

Environment | API Url                                             | Admin                                        |       Status
----------- | --------------------------------------------------- | -------------------------------------------- | :----------------:
Test     | <http://integrator.clicksandbox.com/api/v1> | <http://integrator.clicksandbox.com/api/v1> | :white_check_mark:
Production  | -                                                   | -                                            |        :x:

## Token

## EndPoint
**POST** : `/api/v1/accounts/sign_in.json`

Name                                   | Description                                 | Required/Optional
-------------------------------------- | ------------------------------------------- | ------------------------
account[email]	 | The email address of the account holder      | Required
account[password] | The password of the account holder      | Required

## Request Headers
```powershell
Content-Type: application/json
Host: example.org
Cookie: 

```
--------------------------------------------------------------------------------
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
## Response Headers
```powershell
X-Frame-Options: SAMEORIGIN
X-XSS-Protection: 1; mode=block
X-Content-Type-Options: nosniff
X-Download-Options: noopen
X-Permitted-Cross-Domain-Policies: none
Referrer-Policy: strict-origin-when-cross-origin
Location: /
Content-Type: application/json; charset=utf-8
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJkNTRjNzM2NS02MmNkLTQzMWUtOWE2MS00ZTU3YzZlMmI4NzEiLCJzdWIiOiIxMyIsInNjcCI6ImFjY291bnQiLCJhdWQiOm51bGwsImlhdCI6MTU5MDkxOTA5OCwiZXhwIjoxNTkwOTE5Mzk4fQ.tF-qCY37YvoqoHDe9haVV1Y3CpFQiaO0AV8tXXVtKco
ETag: W/"114acfc3fdcccb2cfcefa1fb6423ef80"
Cache-Control: max-age=0, private, must-revalidate
Set-Cookie: _buslnk_session=QbYDjPN3yipg5m2X6%2FrOELpnoZd2MGELfPV%2B9xY8Jjo9PDMzDCOIMrgJjvU%2B%2BP%2FhUURUUqaIoJDeseiLdLlwMICUgKa1AkJ%2FKnTv5zt6DZYTJ7tSMMJ%2FvjCQFzumZvlvUHlot89tR%2FbhECj%2Fv8ZTKHTm9qdtHu73%2Bwl1H%2Bes1iKAe7DmilSvkKBwAVe3MsmYJ4OKWJWX1tVJhAP2BMop5Zj7SuWIPXmjct2HWQOGPwzjv17qGiEKntatmShHAS4WttLGR2Ky68C5TEb6wdFGXbzh36EzXDFZKNTI--Wodr5YkSqS398sCn--mP4U0JET74YziII1WRFX5A%3D%3D; path=/; HttpOnly
X-Request-Id: 869ff49b-db0f-4858-a51d-b21b7a1df417
X-Runtime: 0.008569
Content-Length: 172
```
--------------------------------------------------------------------------------
## Success Response

Status Code - 201 Created

```json
{
    "id"=>13,
    "status"=>"active",
    "email"=>"kuldeep-13-ceaf44eb90e9@gmail.com",
    "created_at"=>"2020-05-31T09:58:18.277Z",
    "updated_at"=>"2020-05-31T09:58:18.284Z",
    "admin_user_id"=>nil
}
```

--------------------------------------------------------------------------------

## Expected Errors
Status Code - 401 Unauthorized

```json
{
    "sucess": false,
    "message": "Invalid Email or password."
}
```