## สวัสดีครับ วันนี้จะมาอธิบายโปรแกรมในวิชาLE202 ใน part ของ microcontroller

### Example 1
มี2ส่วน คือ setup ซึ่งจะรันแค่ครั้งเดียว และ loop ซึ่งจะรันวน loop เรื่อย ๆ และจะ delay 1 second สามารถ reset เพื่อให้โปรแกรม count ใหม่ได้ด้วยการกดปุ่มบน microcontroller

### Example 2
จะมีส่วน setup สำหรับ set wifi โดยส่วน loop ก็จะวน loop เพื่อหา wifi โดยเมื่อได้ wifi ก็จะแสดงผล หากต้องการเริ่มโปรแกรมใหม่ก็จะสามารถกดปุ่ม reset บน microcontroller ได้

### Example 3
วน loop every 0.5 second โดยจะเพิ่ม count ไปเรื่อย ๆ โดยถ้า count เป็นเลขคี่ให้ on(LED เปิด) ส่วนคู่เป็น off(LED ปิด) ส่งผลให้ LED ในการทดลองนี้สว่างและดับสลับกันไปเรื่อย ๆ

### Example 4
set port 0 เป็น input และ port 2 เป็น output โดยจะวน loop ถ้า port 0 เป็น 1 จะส่งไป low ไปยัง port 2 ให้ไฟดับ ถ้า port 0 เป็น 0 จะส่ง high ไปยัง port 2 ทำให้ไฟติด

### Example 5
มี setup ให้เชื่อม wifi โดยเราสามารถเช็ค IP addressของ wifi ได้ แล้วทำการทดสอบจากการเข้า web browser

### Example 6
upload program ลงไปใน microcontroller ก็จะสร้าง wifi ขึ้นมา โดยต้องกำหนดชื่อ, password, IP address, gate way และweb sever เพื่อให้คนมา connectได้ 
