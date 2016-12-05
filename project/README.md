### Notice
Using project `Appifi` ( [*Link*](https://github.com/JiangWeiGitHub/Appifi) ) as a sample project

### Procedure
`init -> login -> token -> other api`

1. init with formating disk `sdb` & adding administrator `admin`

  `curl -l -H "Content-type: application/json" -X POST -d '{"target":["sdb"],"mkfs":{"type":"btrfs","mode":"single"},"init":{"username":"admin","password":"123"}}' 192.168.1.6:3000/system/mir`

  return: `{"message": "ok"}`

2. init with adding administrator `admin` only

  `curl -l -H "Content-type: application/json" -X POST -d '{"target":["5e817e19-eea2-4634-9c1f-ddd64410033e"],"init":{"username":"admin","password":"123"}}' 192.168.1.6:3000/system/mir`

  return: `{"message": "ok"}`

3. get login's user list

  `curl 192.168.1.6:3721/login`

  return: `[{"uuid":"9b7bc0a4-f76d-4eda-b210-b461766644cb","username":"admin","avatar":null,"unixUID":2000}]`

4. get pointed user's token

  `curl -u 9b7bc0a4-f76d-4eda-b210-b461766644cb:123 192.168.1.6:3721/token`

  return: `{"type":"JWT","token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1dWlkIjoiOWI3YmMwYTQtZjc2ZC00ZWRhLWIyMTAtYjQ2MTc2NjY0NGNiIn0.kV8OYritQFoSSmyR1tkC2m8Dto8vGgEiITES14mNNVQ"}`

5. add new user

  `curl -l -H "Authorization: JWT eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1dWlkIjoiNWRhOTIzMDMtMzNhMS00Zjc5LThkOGYtYTdiNmJlY2RlNmMzIn0.79bUgRf9-m0KYP42_BV06yjtxaxgqYIiNdiIJIXfRMM" -H "Content-type: application/json" -X POST -d '{"username":"a","password":"123"}' 192.168.1.6:3721/users`

  return: `{"type":"local","uuid":"dc0a6f73-0aa9-4c7d-948e-31579f12c712","username":"a","avatar":null,"email":null,"isAdmin":false,"isFirstUser":false,"home":"848ef27e-6ab3-4846-ba96-d0be356f0aed","library":"50528f50-a378-4176-8b52-8e2d081d6368","unixUID":2001}`
