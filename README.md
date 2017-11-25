# ตรวจหวยออนไลน์ผ่าน API เขียนด้วย NodeJS + MongoDB
ทำ WebScrap จากเว็ปไซต์ [Kapook.com]( http://lottery.kapook.com/history.html) แล้วทำการบันทึกข้อมูลลง MongoDB + NodeJS

ขั้นตอนการทำงานของ WebScrap
- ร้องขอการเชื่อมต่อเว็ปผ่าน Protocal HTTP ด้วย [Requests](https://www.npmjs.com/package/request) (ในไฟล์ scrap.js) 
- ทำการอ่านแท็กต่างๆเพื่อเก็บข้อมูล โดยใช้ [Cheerio](https://github.com/cheeriojs/cheerio) (ในไฟล์ scrap.js)
- บันทึกข้อมูลที่ได้มาลงในฐานข้อมูล MongoDB
- เปิดเซิฟเวอร์และทำการ Routing ผ่านโมดูล [Express](https://www.npmjs.com/package/express)

## เริ่มต้นการใช้งาน
1. ติดตั้ง [NodeJS]( https://nodejs.org/en/) 

- หากเป็น Windows สามารถดาวโหลดมาติดตั้งได้เลย [Download](https://nodejs.org/en/download/)

- หากเป็น Linux Ubuntu เลือกหัวข้อ Debian and Ubuntu based Linux distributions [Download](https://nodejs.org/en/download/package-manager/#arch-linux)

2. ติดตั้ง MongoDB จากนั้นให้ทำการ Set Path mongoDB และทำการเปิดการทำงานของ Server  and Connect Server
			
     ```sh
    Start Server
     $>mongod
    Connect Server
    $>mongo
    ```
- [วิธีติดตั้งแบบเอกสาร](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/)
	
- [ วิธีติดตั้งแบบวิดีโอ](https://www.youtube.com/watch?v=IPV2Z3f-WMk)

3. Clone Project (https://github.com/Party12123/Lotterry.git) จากนั้นให้ทำการรันไฟล์ scrap.js ข้อมูลจะถูกเก็บไว้ที่ document lottery
     ```sh
    คำสั่งที่ใช้ Run scrap.js
     $> node scrap.js
    ```
4. รัน server.js เพื่อดู API จากการดึงข้อมูลจาก MongoDB มาแสดง
     ```sh
    คำสั่งที่ใช้ Run server.js
     $> node server.js
    ```
- Get method http://localhost:8080/{year}/{month}/{date}
- Post method http://localhost:8080/
- สามารถใช้ Robo 3T เป็น  GUI ในการจัดการฐานข้อมูล MongoDB เพื่อความสะดวกต่อการดูข้อมูล [Download](https://robomongo.org/)  [ วิดีโอสอนการติดตั้ง Robo 3T](https://www.youtube.com/watch?v=0cxFyeQ4Vio)
  แนะนำการตรวจสอบการทำงานของ Post method ผ่าน [Postman](https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop?hl=th)
