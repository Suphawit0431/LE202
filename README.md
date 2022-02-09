# Hello everyone ผมชื่อนายศุภวิชญ์ แสนสุข รหัส6310680431
สำหรับวันนี้ผมจะมาสรุปหัวข้อต่าง ๆ ที่ได้ไปรับชมและรับฟังมาครับ

## Markdown
#### การเขียนหัวข้อของเรื่องที่เราจะเน้นด้วยการใส่#หน้าข้อความที่เป็นหัวข้อ 
#### การเขียนเขียนตัวหนา=>ctrl+B 
#### การเขียนตัวเอียง=>ctrl+I
#### bullet point หน้าข้อความด้วยการใช้ขีดตรง(-) e.g.
- วิชาLE202

## Microcontroller ESP-01
- digital ข้อมูล digital เกิดจากการเอาสัญญาณไฟฟ้ามาใช้งานโดยใช้เลขฐาน2 โดยจะมีแค่0(0v, off), 1(5v, on) 
- voltage คือความต่างศักย์ระหว่างจุด2จุด มี2ประเภทคือ กระแสตรง(AC) e.g.ไฟบ้าน และ กระแสสลับ(DC) e.g.Li-ion battery, ไฟที่ออกมาจากusb
- computer เป็นอุปกรณ์ที่มีหลายขนาดไว้ใช้ในการใช้งานที่ต่างกันออกไป e.g.single board computer โดย computer สามารถ connect กันผ่าน internet ได้ด้วยความเร็วที่สูง
- internet สัญญาณที่สามารถทำให้ทุกสิ่งที่อย่างเชื่อโยงกันได้ทั้งมีสายและไร้สาย
- program lang การพัฒนา software มาใช้ใน computer เพื่อให้ใช้งานได้ง่ายขึ้น
- platformio เป็นการพัฒนา software แบบเปิด โดยใช้การเขียนลง microcontroller ได้หลายแบบ e.g.เขียนแบบ Arduino, ESP8266 Non-OS SDK โดยยังมี board ที่สามามารถนำมาพัฒนาต่อได้ และยังมี Libraries ที่สามารถนำมา adapt ได้ทันที ไม่ต้องเขียนใหม่ทั้งหมด

## สรุปการทดลอง ESP-01 6 การทดลอง
### example 1  
เริ่มโดยเขียน program ลงไปใน mocrocontroller โดยมี2ส่วน คือ setup ซึ่งจะรันแค่ครั้งเดียว และ loop ซึ่งจะรันวน loop เรื่อย ๆ และจะหน่วงเวลา 1 second โดยจะใช้ platformio ซึ่งจะบอกข้อมูลของ program ทั้งหมดที่จะ upload ลงไปใน microcontroller โดยจะต้องกดปุ่ม แล้วเช็คด้วยการกด pio device monitor จะเห็น count เพิ่มขึ้นทีละ 1 every 1 second
### example 2
เมื่อ upload program แล้ว จะมีส่วน setup สำหรับ set wifi โดยส่วน loop ก็จะวน loop เพื่อหา wifi โดยเมื่อได้ wifi ก็จะแสดงผล เมื่อ upload ขึ้นแล้วก็จะเริ่ม scan หา wifi โดยใช้คำสั่ง pio device monitor ก็จะแสดงผล wifi ที่เจอ
### example 3
มี output port และ input port อย่างละ 2 port คือport 0 and port 1 โดยจะเสียบ USB ก่อนแล้วค่อยเสียบ computer ต่อ เมื่อเสียบ io 0 แล้วรัน program จะทำให้ port 0 เป็น output และวน loop every 0.5 second โดยจะเพิ่ม count ไปเรื่อย ๆ ถ้าจำนวนรอบเป็นเลขคี่ให้ on(LED เปิด) ส่วนคู่เป็น off(LED ปิด)
### relay
นำ microcontroller ที่เขียน program ไว้แล้วไปเสียบที่ relay เพื่อให้มีการส่งสัญญาไปที่ control relay เพื่อเอาไว้เปิดและปิด switch
### example 4
มีการนำ input จากภายนอกเข้ามาใน microcontroller set port 0(สีขาว) เป็น input และ port 2(สีเหลือง) เป็น output โดยจะวน loop ถ้า port 0 เป็น 1 จะส่งไป low ไปยัง port 2 ให้ไฟดับ ถ้า port 0 เป็น 0 จะส่ง high ไปยัง port 2 ทำให้ไฟติด
### example 5
ต้องเชื่อมต่อ wifi ซึ่งจะต้องใส่ชื่อและ password ลงไปและยังมี setup ให้เชื่อม wifi โดยเราสามารถเช็คIP addressของ wifi ได้ แล้วทำการทดสอบจากการเข้า web browser
### example 6
จะสร้าง wifi ขึ้นมาเอง โดยต่อจาก mobile phone เมื่อ upload program ลงไปใน microcontroller ก็จะสร้าง wifi ขึ้นมา โดยต้องกำหนดชื่อ, password, IP address, gate way และweb sever เพื่อให้คนมา connectได้  สามารถทดสอบได้ด้วยการใช้ mobile phone เพื่อค้นหา wifi ที่เพิ่งสร้างขึ้นมาได้ 
