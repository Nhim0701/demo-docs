#API一覧

## API List

|No.|API function no.|Method|API name|Functional overview|
|---|---|---|---|---|
|0|CSC-001|Get|userinfo|lấy thông tin của user|
|1|CSC-002|Get|permission|Lấy permission của user|
|2|CSC-003|Get|listSeatChartName|lấy tên của toàn bộ chart có trong hệ thống|
|3|CSC-004|Get|seatChart2DDetail|hiển thị toàn bộ model tương ứng với chart được chọn|
|4|CSC-005|Get|listEmployee|hiển thị toàn bộ nhân viên|
|5|CSC-006|Post|addSeatChart|thêm seat chart vào hệ thống|
|6|CSC-007|Put|upadteSeatChart|sửa đổi thông tin seat chart|
|7|CSC-008|Delete|deleteSeatChart|xóa seat chart khỏi hệ thống|
|8|CSC-009|Post|addModel|thêm model vào seat chart đang chọn|
|9|CSC-010|Put|updateModel|thay đổi thông tin model trong seat chart|
|10|CSC-011|Delete|deleteModel|xóa model khỏi seat chart|

## Status code

It will return the code below.

|Status code|Description|
|---|---|
|200|Request successful|
|201|Successful registration|
|204|The request was successful, but the body to be returned does not exist.|
|400|Specifying invalid request parameters|
|401|API access token is invalid or permissions are invalid|
|404|Access non-existent URL|
|429|Request limit exceeded|
|500|Unknown error|
## Header setting

### This section will be added to all API request headers

|JSON Key|Type|Size|Required|encryption|Value description|
|---|---|---|---|---|---|
|X-Auth-Type|String||○||sso|
|X-Csv-Key|String||○|＊||
|X-Csv-Token|String||○|＊|Bearer|

Example:
```
X-Auth-Type:sso
X-Csv-Key:8e31b3553533e085da38702a5a8f220c
X-Csv-Token:Bearer eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJCY1RsRld4NjRhWlZ2eFZDa1VsblphYnd3NHU0SzFMZXlrTF9UWmVTSVYwIn0.eyJleHAiOjE3MDIwNDUyMDcsImlhdCI6MTcwMjAxNjQwNywiYXV0aF90aW1lIjoxNzAyMDE2NDA3LCJqdGkiOiI5NjUwZjdkNS1hMTVmLTRlNGEtOTM2OC02YjAzNjFjYjE1MWYiLCJpc3MiOiJodHRwczovL3Nzby5jdWJldm4tc2VydmljZS5jb20vcmVhbG1zL2NzdiIsImF1ZCI6WyJ1cm46YW1hem9uOndlYnNlcnZpY2VzIiwiZGV2b3BzLXBvcnRhbCIsImFjY291bnQiXSwic3ViIjoiYzJjNTY2M2UtNTkwNy00NTMyLWI1YWYtN2YyYmRiZTc1ZTliIiwidHlwIjoiQmVhcmVyIiwiYXpwIjoiY2Jvb2siLCJub25jZSI6IjJkNDFjNzk1LWJhNTEtNDg4Ny1hMWNkLTE3MjA2NDI3NzMzYSIsInNlc3Npb25fc3RhdGUiOiIxZjUxN2Y2ZC0yYmRiLTQyZjktOGQ4NS0xZDIzZGNhOThiODUiLCJhY3IiOiIxIiwiYWxsb3dlZC1vcmlnaW5zIjpbIioiXSwicmVhbG1fYWNjZXNzIjp7InJvbGVzIjpbIm9mZmxpbmVfYWNjZXNzIiwiZGVmYXVsdC1yb2xlcy1hd3MiLCJ1bWFfYXV0aG9yaXphdGlvbiJdfSwicmVzb3VyY2VfYWNjZXNzIjp7InVybjphbWF6b246d2Vic2VydmljZXMiOnsicm9sZXMiOlsiYXJuOmF3czppYW06OjcwMjA5NzY2OTk5ODpyb2xlL2FkbWluaXN0cmF0b3IsYXJuOmF3czppYW06OjcwMjA5NzY2OTk5ODpzYW1sLXByb3ZpZGVyL2Nzdi1zc28iXX0sImRldm9wcy1wb3J0YWwiOnsicm9sZXMiOlsiZnVsbGFjY2VzcyJdfSwiYWNjb3VudCI6eyJyb2xlcyI6WyJtYW5hZ2UtYWNjb3VudCIsIm1hbmFnZS1hY2NvdW50LWxpbmtzIiwidmlldy1wcm9maWxlIl19fSwic2NvcGUiOiJvcGVuaWQgZW1haWwgY3N2LWNsaWVudC1zY29wZSIsInNpZCI6IjFmNTE3ZjZkLTJiZGItNDJmOS04ZDg1LTFkMjNkY2E5OGI4NSIsImVtYWlsX3ZlcmlmaWVkIjp0cnVlLCJsZGFwX2lkIjoiNTUyODYzMWYtZjBiNy00YTcyLTk4ZTEtNTIxNGZjNTk2MTIzIiwibmFtZSI6Ik5HVVlFTiBUUk9ORyBISUVVIiwiZW1wbG95ZWVJRCI6IjE2MjkiLCJnaXZlbl9uYW1lIjoiSElFVSIsImZhbWlseV9uYW1lIjoiTkdVWUVOIFRST05HIiwibGRhcF91c2VybmFtZSI6ImhpZXUubnQiLCJlbWFpbCI6ImhpZXUubnRAdm4tY3ViZXN5c3RlbS5jb20iLCJ1c2VybmFtZSI6IjE2MjkifQ.cDTNER3fH6hTN3Exw0gCAovA7P7GyqSvOF2RZO5MUdKM6BOoz6HFTjOo8c1uekoIQHnsf154YawUmEpZgxWcjxgf9fi5g1NyeCQYuy8UyGXvYZ_eHKyk42Su-jXjmxl8TZs03kZ0B8PcsOt-9IR7iIECTsMDACAtAr3y9MGIt6ghzy5ROLdV7zIcmdGgjcV8b6BDArqIiL83BtAGnW8hMcjFdYPLcDq1EOJtX0il6WBk4Q33b5-200HwufljatUU2PxXRYNSCegypxj-1q7tVQ6ABE8xafhSMnDwj3URZVxeQd0Kxk5WyG6rupIma4DOoecif08ixeh0AJ2s89veGnObPaBJw4pvzlflLzoO0ZJ0IkPApYhBPB0mfMJE1worsimurHiPEjaAWX69_FYW11UXDeacxAbdXa-zTkVTDuP30SULj-2QZat833BkjM_oUEbaQd3fUjNWsx2vGNQl-LaE3fIHkROx2VKIgF9A-iIj1dfzUJgHL4UzxhzjYk0PA9CYLibmrULZ8GHCSH7ooqXCCChkE29w8mNH-wvTNJ5kyDSwTVifYpyHmBfJZBNZi8pOZwfo2WS7bzNBFnTYVflPmP2KRMHfsAbOLyNT1Rs4bOqfGZPXBMQCexG9ws9v3L5fQ0NjHupPM2mHT1cNfmwgF048yXF1pP4HMUpYS1k
```






