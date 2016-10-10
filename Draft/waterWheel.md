# Test WaterWheel with cURL

+ Get

  `curl 192.168.5.226/nas/uuid`
  
+ Post

  `curl 192.168.5.226/nas/uuid -X POST`
  
+ Upload File

  1. Post File Infor
  
    `curl -l -H "Content-type: application/json" -X POST -d '{"data":["file's hash"]}' 192.168.5.226/nas/456fe918-1872-4ec1-b4f8-c09b62b49d72/waterwheel/37a-af3a-ec4dc4c43624`
    
  2. Post File
  
