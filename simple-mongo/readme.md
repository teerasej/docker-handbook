

# ดาวน์โหลด และใช้งาน MongoDB ในรูปแบบ Docker

เพื่ออำนวยความสะดวก สามารถติดตั้ง[ส่วนเสริม MongoDB for VSCode](https://marketplace.visualstudio.com/items?itemName=mongodb.mongodb-vscode)

## 1. สมัครและเปิดใช้งานบัญชี Docker Hub 

[สมัคร Docker Hub](https://hub.docker.com/signup)


## 2. ดาวน์โหลด Container Image ของ MongoDB 

ค้นหา docker image container ชื่อ **mongo** หรือ[กดที่ลิ้งค์นี้](https://hub.docker.com/_/mongo) 

จากนั้นคัดลอกคำสั่งด้านล่าง ไปรันในโปรแกรม

- Command Prompt (Windows)
- Terminal (MacOS)

```
docker pull mongo
```

สังเกตว่าจะมีชื่อ Image แสดงขึ้นใน Docker Extension ของ VSCode 

<img width="317" alt="2021-03-23_21-39-10" src="https://user-images.githubusercontent.com/85179/112164252-4fc3b480-8c20-11eb-8ec7-56b1c15cce01.png">


## 3. รันคำสั่งสร้าง Container จาก Image 

เปิด Terminal ใน VSCode และรันคำสั่งเพื่อสร้าง Container และเปิดการทำงาน

```
docker run -p 80:80 -p 27017:27017 mongo
```

- `-p EXTERNAL_PORT:INTERNAL_PORT`: ทำการจับคู่ port ภายนอก กับหมายเลข port ภายใน container

## 4. เช็คการทำงานของ Container ที่รันทำงาน

<img width="317" alt="2021-03-23_21-39-22" src="https://user-images.githubusercontent.com/85179/112164352-65d17500-8c20-11eb-949e-884d2968d5a1.png">


**จากส่วนของ Container Panel** เราสามารถ

1. แสดง Log ของ Container ที่ทำงานอยู่ได้
2. เปิด shell ที่เชื่อมต่อเข้าไปภายใน Container
3. หยุดการทำงานของ Container
4. รีสตาร์ทการทำงานของ Container
5. ลบ Container

## 5. ทดสอบเชื่อมต่อ MongoDB Container 

เปิดส่วนเสริม MongoDB for VSCode 

1. เลือก Add Connection 

<img width="316" alt="2021-03-23_21-44-46" src="https://user-images.githubusercontent.com/85179/112165487-5ef73200-8c21-11eb-9638-f1ee28ff0e48.png">

2. เลือก Open Form จากส่วน Advanced Connection Setting 

<img width="461" alt="2021-03-23_21-45-06" src="https://user-images.githubusercontent.com/85179/112165916-c1503280-8c21-11eb-9244-b0b9b6e1f77d.png">


## 6.กรอกรายละเอียดการเชื่อมต่อ MongoDB Container

<img width="604" alt="2021-03-23_21-45-35" src="https://user-images.githubusercontent.com/85179/112165931-c44b2300-8c21-11eb-9574-f9e324367416.png">


1. เลือก General
2. Connection Type: Standalone
3. Hostname: localhost
4. Port: 27017
5. Authentication: None (ถ้ามี ให้เลือกกรอกให้เรียบร้อย)
6. กดปุ่ม Connect


