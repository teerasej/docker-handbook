
# ดาวน์โหลด และใช้งาน MongoDB ในรูปแบบ Docker

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

image

## 3. รันคำสั่งสร้าง Container จาก Image 

```
docker run -p 80:80 -p 27017:27017 mongo
```

- `-p EXTERNAL_PORT:INTERNAL_PORT`: ทำการจับคู่ port ภายนอก กับหมายเลข port ภายใน container

## 4. เช็คการทำงานของ Container ที่รันทำงาน



**จากส่วนของ Container Panel** เราสามารถ

1. แสดง Log ของ Container ที่ทำงานอยู่ได้
2. เปิด shell ที่เชื่อมต่อเข้าไปภายใน Container
3. หยุดการทำงานของ Container
4. รีสตาร์ทการทำงานของ Container