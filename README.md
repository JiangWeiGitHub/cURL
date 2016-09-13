# cURL

### Notice
Using project `fruitmix` ( [*Link*](https://github.com/JiangWeiGitHub/FruitMix) ) as a sample project

### Parameters
+ `-H, --header LINE` Pass custom header LINE to server
+ `-X, --request COMMAND` Specify request command to use
+ `-u, --user USER[:PASSWORD]` Server user and password

### GET
+ init -> login -> token -> other api<P>
  ```
  curl http://localhost:3721/init
  curl http://localhost:3721/login        
  curl -u 5da92303-33a1-4f79-8d8f-a7b6becde6c3:123456 http://localhost:3721/token        
  curl -H "Authorization: JWT eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1dWlkIjoiNWRhOTIzMDMtMzNhMS00Zjc5LThkOGYtYTdiNmJlY2RlNmMzIn0.79bUgRf9-m0KYP42_BV06yjtxaxgqYIiNdiIJIXfRMM" http://localhost:3721/drives
  ```


