## ความหมายและความสัมพันธ์ของ High level language, Low level language and Machine language

### Machine language
เป็นภาษาที่ประกอบด้วยตัวเลข โดยตัวเลขที่ใช้ก็คือตัวเลขฐาน 2 ซึ่งก็มีแค่ 0 และ 1 ตัว machine language เมื่อป้อนลงใน computer ก็จะทำให้ computer เข้าใจและทำงานได้ทันที แต่การที่ผู้เขียน program จะสามารถเขียนภาษาเครื่องได้ ผู้เขียนจะต้องจำได้ว่าตัวเลขแต่ละชุดแทนคำสั่งอะไร ซึ่งยากต่อการใช้งานและมีโอกาสเกิดความผิดพลาดสูงมาก นอกจากนี้ computer แต่ละรุ่นจะมีรูปแบบ machine language ที่ต่างกันออกไป ทำให้เมื่อเปลี่ยน computer จึงต้องเขียนภาษาเครื่องใหม่ทั้งหมด

### Low level language
มีการพัฒนาขึ้นมาจาก machine language โดยใช้ตัวอักษรภาษาอังกฤษเป็นรหัสในการใช้งาน, การทำงาน และการตั้งชื่อตัวแปรเพื่อจดจำตำแหน่งที่ใช้เก็บค่าข้อมูลต่าง ๆ ตัวอย่าง low level langauge ได้แก่ Assembly มีคำสั่ง เช่น addi หมายถึง บวก, mul หมายถึง คูณ

### Processor
เป็นองค์ประกอบที่สำคัญส่วนหนึ่งของเครื่องคอมพิวเตอร์ทุกประเภทในโลก เปรียบเสมือนกับเป็นมันสมองให้กับคอมพิวเตอร์นั่นเอง ตัวอย่างเช่น RISC-V, ARM และ AVR เป็นต้น

### High level language 
คือ ภาษาที่สร้างขึ้นเพื่อให้มีความสะดวกในการเขียน program โดยคำสั่งส่วนใหญ่จะเป็นภาษาอังกฤษที่ผู้อ่านสามารถเข้าใจความหมายได้ง่าย ตัวอย่างภาษาระดับสูง เช่น Pascal, C และ Java เป็นต้น ซึ่งการเขียน program ด้วย high level language 1 คำสั่ง จะถูกแปลงเป็น machine language หลายคำสั่งอีกที

จากข้างบนเราจะเห็นได้ว่าภาษาที่พัฒนาขึ้นจนมนุษย์เข้าใจได้ง่ายคือ high level language แต่การที่ตัว computer ของเราจะสามารถทำงานได้นั้น computer ต้องแปลง high level เป็น machine language ก่อน ซึ่งจะขอยกตัวอย่างการแปลง high level language เป็น machine language จาก https://godbolt.org


โดยตัว website จะแบ่งเป็นฝั่ง high level language และ low level language
![24F84536-472A-49BB-B1ED-E052B5AE3318](https://user-images.githubusercontent.com/98944255/161790786-8984b090-f41d-4747-a01c-8201d2aa23c9.jpeg)


อีกทั้งเราสามารถเลือกภาษาในฝั่ง high leve(ช่องสีแดง) และ low level(ช่องสีม่วง)
![672AD526-D03B-4421-96F7-0B58260F2DD9](https://user-images.githubusercontent.com/98944255/161793142-f4f4daeb-177c-470b-abc6-ccd37ee7031c.jpeg)


นอกจากนี้ ในฝั่งของ low level เรายังสามารถแปลงเป็น machine language ได้ด้วยการ click Compile to binary ในส่วนของ output 
![1B64D7DA-A6A7-401D-8317-3B24E59F686A](https://user-images.githubusercontent.com/98944255/161794807-603f6051-32c4-4fbd-9c63-5c936f0a5459.jpeg)

