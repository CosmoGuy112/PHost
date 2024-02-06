# ProjectComor_Host
## I/O
lsusb เป็นคำสั่งในระบบปฏิบัติการ Linux ที่ใช้สำหรับแสดงรายการของอุปกรณ์ USB ที่เชื่อมต่อกับเครื่องคอมพิวเตอร์ บทบาทที่สำคัญคือ
แสดงรายการอุปกรณ์ USB lsusb สามารถดูรายการของอุปกรณ์ USB ทั้งหมดที่เชื่อมต่อกับเครื่อง Linux รวมถึงรายละเอียดเกี่ยวกับแต่ละอุปกรณ์ เช่น Vendor ID, Product ID, และรุ่นของอุปกรณ์นั้นๆ
คุณส่ง

หลักการทำงานของ lsusb  บน linux เมื่อใช้คำสั่ง lsusb ในเครื่อง Linux, ระบบจะทำการสืบค้น (scan) อุปกรณ์ USB ที่เชื่อมต่อกับเครื่อง lsusb จะอ่านข้อมูลเกี่ยวกับอุปกรณ์ USB จากไดรเวอร์ที่ติดตั้งในระบบปฏิบัติการ Linux lsusb จะแสดงข้อมูลเพิ่มเติมเกี่ยวกับแต่ละอุปกรณ์ USB เช่น Vendor ID, Product ID, และรุ่นของอุปกรณ์นั้นๆ
คุณส่ง

Syntax: $ lsusb 

Output:
Bus 002 Device 004: ID 046d:0a37 Logitech, Inc. USB Headset H540
Bus 002 Device 002: ID 8087:0024 Intel Corp. Integrated Rate Matching Hub
Bus 002 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 001 Device 004: ID 413c:301a Dell Computer Corp.
Bus 001 Device 003: ID c0f4:05e0
Bus 001 Device 002: ID 8087:0024 Intel Corp. Integrated Rate Matching Hub
Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub

ข้อควรระวังในการใช้งาน ในบางกรณี อาจต้องใช้สิทธิ์ root เพื่อเรียกใช้คำสั่ง lsusb เพราะต้องการสิทธิ์สำหรับการอ่านข้อมูลจาก USB หรือการ์ดส่วนเสริม

#
#norgor

คนสวยมาละ

น้องอิ้น

นุกอ

Host Configuration
