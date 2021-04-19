# วิธีติดตั้ง Node.js บน Ubuntu 20.04

## วิธีที่ 1. ติดตั้ง Node.js ด้วย `apt` จาก Default Repositories 
ขั้นแรกต้องอัพเดท Ubuntu20.04
```bash
sudo apt update
```
จากนั้นทำการติดตั้ง node.js ได้เลย
```bash
sudo apt install nodejs
```
เมื่อทำการติดตั้งเรียบ สามารถตรวจสอบการทำงานได้ด้วย
```bash
nodejs -v
```
ระบบจะแสดงผลลัพธ์ต่อไปนี้ เป็นอันเส็จสิ้นการติดตั้ง
```
v10.19.0
```
ในการใช้งาน nodejs จำเป็นต้องใช้งาน `npm` ในการติดตั้ง package ต่างๆเราต้องทำการิดตั้ง npm ด้วย สามารถติดตั้งได้ด้วยคำสั่งต่อไปนี้
```bash
sudo apt install npm
```
ปัจจุบันหลายๆคนชอบใช้ yarn ในการใช้งาน node package เราสามารถใช้ npm ติดตั้ง yarn ได้ด้วยคำสั่งต่อไปนี้
```bash
npm install -g yarn
```
ตรวจสอบ yarn version ได้โดย
```bash
yarn -v
```

## วิธีที่ 2. ติดตั้งด้วย apt จาก PPA ของ node.js
เริ่มจากคำสั่ง
```bash
cd ~
curl -sL https://deb.nodesource.com/setup_14.x -o nodesource_setup.sh
```
เพื่อทำการดาวน์โหลดไฟล์ `nodesource_setup.sh` มาเพื่อทำการติดตั้งต่อไป
สามารแก้ไขข้อมูลการติดตั้งด้วย `nano` 
```bash
nano nodesource_setup.sh
```
จากนั้นทำการติดตั้งด้วยคำสั่ง
```bash
sudo bash nodesource_setup.sh
```
เมื่อติดตั้งเสร็จเรียบร้อย สามารถตรวจสอบการทำงานของ nodejs ด้วยคำสั่ง
```bash
node -v
```

## วิธีที่ 3. ติดตั้งโดยใช้ `NVM` ในการเลือกติดตั้งแต่ละ version ได้
ทำการดาวน์โหลดไฟล์ติดตั้ง
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
```
เมื่อดาวน์โหลดไฟล์ดังกล่าวเรียบร้อยแล้วให้ทำการติดตั้งได้เลยด้วยคำสั่ง
```bash
source ~/.bashrc
```
เมื่อติดตั้งเรียบร้อยเราสามารถเรียกดู version ต่างๆของ node.js ที่ต้องการติดตั้งได้ด้วยคำสั่ง
```bash
nvm list-remote
```
ระบบจะแสดงตัวอย่างดังนี้
```
. . .
       v12.13.0   (LTS: Erbium)
       v12.13.1   (LTS: Erbium)
       v12.14.0   (LTS: Erbium)
       v12.14.1   (LTS: Erbium)
       v12.15.0   (LTS: Erbium)
       v12.16.0   (LTS: Erbium)
       v12.16.1   (LTS: Erbium)
       v12.16.2   (LTS: Erbium)
       v12.16.3   (Latest LTS: Erbium)
        v13.0.0
        v13.0.1
        v13.1.0
        v13.2.0
        v13.3.0
        v13.4.0
        v13.5.0
        v13.6.0
        v13.7.0
        v13.8.0
        v13.9.0
       v13.10.0
       v13.10.1
       v13.11.0
       v13.12.0
       v13.13.0
       v13.14.0
        v14.0.0
        v14.1.0
        v14.2.0
```
กรณีต้องการติดตั้ง version ใด่ ให้ใช้คำสั่งต่อไปนี้
```bash
nvm install v13.6.0
```
ตรวจสอบ version ปัจจุบันได้ด้วย
```bash
nvm list
```
ระบบจะแสดงข้อมูลต่อไปนี้
```
->      v13.6.0
default -> v13.6.0
node -> stable (-> v13.6.0) (default)
stable -> 13.6 (-> v13.6.0) (default)
. . .
```
ถ้าปรากฏดังตัวอย่างแสดงว่าติดตั้งเสร็จเรียบร้อย

ถ้าต้องการติดตั้งตัว LTS ของ node.js version 12 สามารถทำได้ด้วยวิธี
```bash
nvm install lts/erbium
```
ระบบจะทำการดาวน์โหลด version LTS มาให้และทำการติดตั้ง
```
Downloading and installing node v12.16.3...
. . .
Now using node v12.16.3 (npm v6.14.4)
```

กรณีต้องการเปลี่ยนจาก version ปัจจุบันเป็น version ที่ต้องการด้วยคำสั่ง
```bash
nvm use v13.6.0
```
```
Now using node v13.6.0 (npm v6.13.4)
```
สามารถตรวจสอบ version ปัจจุบันได้ด้วย
```bash
node -v
```

## ที่มา
- [How To Install Node.js on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-20-04)



