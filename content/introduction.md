---
title: "Introductions"
metaTitle: "Buslink service"
metaDescription: "Buslink service"
---
## Envs

Environment | API Url  
----------- | ---------------------------------------------------
Test     | <http://integrator.clicksandbox.com/api/v1>
Production  | https://PleaseContact.us
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
curl -X POST \
  http://integrator.clicksandbox.com/api/v1/accounts/sign_in.json \
  -H 'Accept: */*' \
  -H 'Cache-Control: no-cache' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'Host: integrator.clicksandbox.com' \
  -H 'Postman-Token: b51b2c0e-fc67-46e7-9c97-8ca15696227f,5a90b915-6646-42c9-8502-811e1bfe8843' \
  -H 'User-Agent: PostmanRuntime/7.11.0' \
  -H 'accept-encoding: gzip, deflate' \
  -H 'cache-control: no-cache' \
  -H 'content-length: 307' \
  -H 'content-type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW' \
  -H 'cookie: _payments_integrator_session=NdlEQw%2BHhc6TsZmE89F2ddXNS%2BDkw0JW0GN6UBUlCVdXqbJn8ujdOerZNT%2FCDkZnvhHy9e%2BuUx1jIXRLtAn%2F16L961kcNJ29QWv5l1EQ9Y3SIY2qezqItHC7v5L1MrhhKhPoPucAoni3ndZD58kRt6QC4%2F6ui04YTqlZze0j2V3uVsnpp4mU%2BI87GVQjUvxhFxV%2B%2FA%3D%3D--cfU4DWmJYR2ZJ%2BRk--lp71M6UgMe6A%2FbQN4kui1A%3D%3D; _buslnk_session=KLfZuteGO5LwZa5OBpWhCCixS%2FwrjJJExPIlJXCOyXOaag4tQJwnbFRJhWecLrkFBaWvKtbFlA3hcJBtdDByAYJkquAs%2BGz4WuU7EhvFJnq34B2eeUpN1%2B7Oxha5nV%2BfkfXHLoMM5BONg2zoMk9apWCifWFeNGUri9DU7TrVIS%2FnPy17XEYs--9R66%2FUzfM5C6nPIK--MXsm2%2B0BtK6WM03z7VK%2FMg%3D%3D' \
  -b '_payments_integrator_session=NdlEQw%2BHhc6TsZmE89F2ddXNS%2BDkw0JW0GN6UBUlCVdXqbJn8ujdOerZNT%2FCDkZnvhHy9e%2BuUx1jIXRLtAn%2F16L961kcNJ29QWv5l1EQ9Y3SIY2qezqItHC7v5L1MrhhKhPoPucAoni3ndZD58kRt6QC4%2F6ui04YTqlZze0j2V3uVsnpp4mU%2BI87GVQjUvxhFxV%2B%2FA%3D%3D--cfU4DWmJYR2ZJ%2BRk--lp71M6UgMe6A%2FbQN4kui1A%3D%3D; _buslnk_session=KLfZuteGO5LwZa5OBpWhCCixS%2FwrjJJExPIlJXCOyXOaag4tQJwnbFRJhWecLrkFBaWvKtbFlA3hcJBtdDByAYJkquAs%2BGz4WuU7EhvFJnq34B2eeUpN1%2B7Oxha5nV%2BfkfXHLoMM5BONg2zoMk9apWCifWFeNGUri9DU7TrVIS%2FnPy17XEYs--9R66%2FUzfM5C6nPIK--MXsm2%2B0BtK6WM03z7VK%2FMg%3D%3D' \
  -F 'account[email]=demo@buslnk.com' \
  -F 'account[password]=password'
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
    "email"=>"demo@buslnk.com",
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