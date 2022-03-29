# RISC-V 
#### RISV-V in EmulsiV มีหน้าตาโปรแกรม ประมาณนี้

![image](https://user-images.githubusercontent.com/98944255/160632913-fd9434f6-8d3b-434c-bb05-887050db197a.png)
### จาก program ภาษา Assembly ใน EmulsiV จะมีส่วนที่น่าสนใจ คือ Memory ซึ่งจะบรรจุตัวเลขฐาน 16 อยู่และจะมีส่วนคำสั่งอยู่ด้วย , Genaral-purpose register, แถบ Input/Output
ซึ่งคำสั่งต่าง ๆ จะถูกสั่งจาก list box ใน Memory
### คำสั่งเบื้องต้น
- addi(add immediate) คือ การบวก โดยจะอ่านจากขวาไปซ้าย ตัวอย่างเช่น addi x1, x0, 32 จะมีความหมายว่า นำ 32(แปลงเป็นเลขฐาน 16 ก่อน) ไปบวก x0(00000000) แล้วนำผลลัพธ์ไปใส่ใน x1
 
 ![image](https://user-images.githubusercontent.com/98944255/160643734-44ee1d25-70fe-4a0e-8735-5505f404ab25.png)
 
 ![image](https://user-images.githubusercontent.com/98944255/160644110-f171595c-a3e3-431c-911f-2e1b38cc8fa2.png) 

- lui(load upper immediate) คือ เอาค่า 20 bit แรกของ word ที่มีไปใส่ memory ใน Genaral-purpose ที่ต้องการ ตัวอย่างเช่น lui x2, x0c0000000 จะมีความหมายว่านำ c00000 ไปใส่ใน 20 bit แรกของ x2

 ![image](https://user-images.githubusercontent.com/98944255/160644937-7db0124f-804a-4525-b397-ca3e43103a57.png)

- lbu(load byte unsigned) คือ ดึงค่าใน General-purpose rigister มาแล้วทำค่าที่ได้ไประบุ Address บน Memory สุดท้ายนำไปใส่ใน Memory ที่กำหนด ตัวอย่างเช่น lbu x3, 0(x1) 
จะมีความหมายว่า นำค่าที่อยู่ใน x1  มาระบุ Address บน Memory และดึง 1 byte ใน Address นั้นมาใส่ลงใน x3
 
 ![image](https://user-images.githubusercontent.com/98944255/160648124-e5ea1aa5-cd37-4736-8253-01b20065e687.png)
 
 ![image](https://user-images.githubusercontent.com/98944255/160648302-14feb04c-0b71-4835-8878-558b7116ae32.png)


- beq(branch on equal) คือ การเช็คว่าเท่ากันหรือเปล่า ถ้าเท่ากันก็จะกระโดดไปยัง Address ที่ต้องการ ตัวอย่างเช่น beq x3, x0, +16 จะหมายถึง เช็คว่า x3 กับ x1 มีค่าเท่ากันหรือเปล่า ถ้าเท่าก็จะกระโดดไป 10 address(แปลง 16 ฐาน 10 เป็น เลขฐาน 16) กรณีในตัวอย่างจะเห็นว่าได้ค่าเป็น false ซึ่งก็คือ x1 กับ x3 นั้นไม่เท่ากัน 
 
 ![image](https://user-images.githubusercontent.com/98944255/160648760-27a756c6-6582-4e5f-8f28-690292c00378.png)

- sb(store byte) คือ นำข้อมูลที่สนใจใน Genaral-purpose register ไปใส่ใน Address ที่ต้องการ ซึ่งถ้าเป็นในกรณี program ใน EmulsiV จะเป็นการบอกถึง Data ที่ออกมาในบริเวณ Output ซึ่งในส่วนของค่าที่ออกมาจะต้องไปแปลงด้วยการใช้ตาราง Ascii (เลขฐาน 16) ดังในตัวอย่างที่ได้ค่า 53 (S in ASCII table)

 ![image](https://user-images.githubusercontent.com/98944255/160649309-066f1885-9355-455b-95b6-60e64b077532.png)

- jal(jump and link) คือ กระโดดไปตามที่กำหนด ตัวอย่างเช่น jal x0, -16 จะหมายถึง ลดจากตำแหน่งปัจจุบันไป 10address(แปลง 16 ฐาน 10 เป็น 10 ฐาน 16) ซึ่งจากรูปข้างล่างคำสั่ง jal จะทำให้กระโดดไปที่ Address 08
![image](https://user-images.githubusercontent.com/98944255/160649800-3a6277e0-e97f-41e5-93d7-bcf0d401dd0a.png)

แล้วโปรแกรมก็จะ run ไปเรื่อย ๆ ตามคำสั่งที่มีใน box

#### ASCII TABLE
 
 ![image](https://user-images.githubusercontent.com/98944255/160631589-65ca30ff-cb7b-425d-9b0e-f3fca3559647.png)
 
