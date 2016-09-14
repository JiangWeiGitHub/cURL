# cURL

### Notice
Using project `fruitmix` ( [*Link*](https://github.com/JiangWeiGitHub/FruitMix) ) as a sample project

### Parameters
+ `-H, --header LINE` Pass custom header LINE to server
+ `-X, --request COMMAND` Specify request command to use, just like 'POST' or 'GET'
+ `-u, --user USER[:PASSWORD]` Server user and password
+ `-F, --form CONTENT` Specify HTTP multipart POST data, don't use `-d` to post data directly
+ `shell nesting` \`ShellCommand parameters\` just like \`ls -la ./\`

### Precondition
+ Create a file named `header` with contents of `Authorization: JWT eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1dWlkIjoiNWRhOTIzMDMtMzNhMS00Zjc5LThkOGYtYTdiNmJlY2RlNmMzIn0.79bUgRf9-m0KYP42_BV06yjtxaxgqYIiNdiIJIXfRMM`<p>
+ Create sha256 string for header<p>
`sha256sum header`

### Procedure
`init -> login -> token -> other api`

### GET

  ```
  curl http://localhost:3721/init
  curl http://localhost:3721/login        
  curl -u 5da92303-33a1-4f79-8d8f-a7b6becde6c3:123456 http://localhost:3721/token        
  
  curl -H "`cat header`" http://localhost:3721/drives
  
  // Download file
  curl -H "Authorization: JWT eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1dWlkIjoiNWRhOTIzMDMtMzNhMS00Zjc5LThkOGYtYTdiNmJlY2RlNmMzIn0.79bUgRf9-m0KYP42_BV06yjtxaxgqYIiNdiIJIXfRMM" http://localhost:3721/files/fc55286e-2de9-4ef2-821f-6f1b79979ecb -X GET -O
  ```

### POST

  ```
  curl -H "`cat header`" http://localhost:3721/libraries -X POST
  curl -H "`cat header`" http://localhost:3721/libraries/cb708f6a-c5f0-4d05-ab82-8ddba2b2eb94 --form "fileupload=@header" --form "sha256=b96b8350159bf5f6cd7af1722d04fdecbe910d5dca244850f55783dd45055fd3"
  ```

### Miscellanea
+ sshfs

  ```
  apt-get install sshfs
  sshfs -p 2222(port) tom(username)@192.168.5.100(host address):/home/tom(destination mount point) sshfs/tmp(source mount point) -o allow_other
  ```
