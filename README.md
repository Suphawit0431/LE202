# Hello everyone ผมชื่อนายศุภวิชญ์ แสนสุข รหัส6310680431
สำหรับวันนี้ผมจะมาสรุปหัวข้อต่าง ๆ ที่ได้ไปรับชมและรับฟังมาครับ

## Microcontroller ESP-01
- digital ข้อมูล digital เกิดจากการเอาสัญญาณไฟฟ้ามาใช้งานโดยใช้เลขฐาน2 โดยจะมีแค่0(0v,off),1(5v,on) 
- voltage คือความต่างศักย์ระหว่างจุด2จุด มี2ประเภทคือ กระแสตรง(AC) e.g.ไฟบ้าน และ กระแสสลับ(DC) e.g.Li-ion battery,ไฟที่ออกมาจากusb
- computer เป็นอุปกรณ์ที่มีหลายขนาดไว้ใช้ในการใช้งานที่ต่างกันออกไป e.g.single board computer โดยcomputerสามารถconnectกันผ่านinternetไดด้วยความเร็วที่สูง
- internet สัญญาณที่สามารถทำให้ทุกสิ่งที่อย่างเชื่อโยงกันได้ทั้งมีสายและไร้สาย
- program lang การพัฒนาsoftwareมาใช้ในcomputer เพื่อให้ใช้งานได้ง่ายขึ้น
- platformio เป็นการพัฒนาsoftwareแบบเปิด โดยใช้การเขียนลงmicrocontrollerได้หลายแบบ e.g.เขียนแบบ Arduino,ESP8266 Non-OS SDK โดยยังมีboardที่สามามารถนำมาพัฒนาต่อได้ และยังมี Libraries ที่สามารถนำมาadaptได้ทันที ไม่ต้องเขียนใหม่ทั้งหมด

## สรุปการทดลอง ESP-01 6 การทดลอง
### example 1  
เริ่มโดยเขียนprogramลงไปในmocrocontroller โดยมี2ส่วน คือ setup ซึ่งจะรันแค่ครั้งเดียว และ loop ซึ่งจะรันวน loop เรื่อย ๆ และจะหน่วงเวลา 1 second โดยจะใช้platformio ซึ่งจะบอกข้อมูลของprogramทั้งหมดที่จะ uploadลงไปในmicrocontroller โดยจะต้องกดปุ่ม แล้วเช็คด้วยการกด pio device monitor จะเห็นcount เพิ่มขึ้นทีละ 1 every 1 second
### example 2
เมื่อupload programแล้ว จะมีส่วนsetup สำหรับ set wifi โดยส่วนloopก็จะวนloopเพื่อหาwifi โดยเมื่อได้wifiก็จะแสดงผล เมื่อuploadขึ้นแล้วก็จะเริ่มscanหาwifiโดยใช้คำสั่งpio device monitor ก็จะแสดงผล wifi ที่เจอ
### example 3
มีoutput port และ input port อย่างละ 2 port คือport 0 and port 1 โดยจะเสียบUSBก่อนแล้วค่อยเสียบcomputerต่อ เมื่อเสียบ io 0 แล้วรันprogram จะทำให้port 0 เป็นoutput และวนloop every 0.5 second โดยจะเพิ่มcountไปเรื่อย ๆ ถ้าจำนวนรอบเป็นเลขคี่ให้ on(LED เปิด) ส่วนคู่เป็นoff(LED ปิด)
### relay
นำ microcontroller ที่เขียน program ไว้แล้วไปเสียบที่ relay เพื่อให้มีการส่งสัญญาไปที่ control relay เพื่อเอาไว้เปิดและปิด switch
### example 4
มีการนำ input จากภายนอกเข้ามาใน microcontroller set port 0(สีขาว) เป็น input และ port 2(สีเหลือง) เป็น output โดยจะวน loop ถ้า port 0 เป็น 1 จะส่งไป low ไปยัง port 2 ให้ไฟดับ ถ้า port 0 เป็น 0 จะส่ง high ไปยัง port 2 ทำให้ไฟติด
### example 5
ต้องเชื่อมต่อ wifi 
### example 6
