# การรัน Docker compose: Friend API 

สร้างไฟล์ **docker-compose.yml** และกำหนดค่าตามด้านล่าง

```yml
version: '3'

services:

    # ชื่อของ service ที่ต้องการกำหนดอ้างอิงในกลุ่มเดียวกัน
    # ในที่นี้เรากำหนด container ของ mongoDB image ในชื่อ db
    db:
        # หากต้องการกำหนดชื่อ container
        # container_name: database_mongo

        # ให้แน่ใจว่าได้ระบุ image ที่ต้องการ รวมถึง tag ที่ถูกต้องจริงๆ
        image: teerasej/mongodb-friend-api

    # ชื่อของ service ที่ต้องการกำหนดอ้างอิงในกลุ่มเดียวกัน
    api:
        # หากต้องการกำหนดชื่อ container
        # container_name: api_main

        # ให้แน่ใจว่าได้ระบุ image ที่ต้องการ รวมถึง tag ที่ถูกต้องจริงๆ 
        image: teerasej/node-friend-api

        # สามารถกำหนด environment variable จาก compose ได้ด้วย
        environment:
            - PORT=3000
            - MONGO_HOST=db
            - MONGO_PORT=27017

        # กำหนดอ้างอิงถึง db
        depends_on:
            - db

        # map port
        ports:
          - "3000:3000"
```

จากนั้นรันคำสั่งใน Terminal ที่มีไฟล์ **docker-compose.yml** โดยตรง

```
docker-compose up 
```
