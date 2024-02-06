## I/O
<div align="center"> lsusb
</div>
บทบาทหน้าที่ของ lsusb<br>
lsusb เป็นคำสั่งในระบบปฏิบัติการ Linux ที่ใช้สำหรับแสดงรายการของอุปกรณ์ USB ที่เชื่อมต่อกับเครื่องคอมพิวเตอร์ บทบาทที่สำคัญคือ
แสดงรายการอุปกรณ์ USB lsusb สามารถดูรายการของอุปกรณ์ USB ทั้งหมดที่เชื่อมต่อกับเครื่อง Linux รวมถึงรายละเอียดเกี่ยวกับแต่ละอุปกรณ์ เช่น Vendor ID, Product ID, และรุ่นของอุปกรณ์นั้นๆ<br><br>

หลักการทำงานของ lsusb<br>
บน linux เมื่อใช้คำสั่ง lsusb ในเครื่อง Linux, ระบบจะทำการสืบค้น (scan) อุปกรณ์ USB ที่เชื่อมต่อกับเครื่อง lsusb จะอ่านข้อมูลเกี่ยวกับอุปกรณ์ USB จากไดรเวอร์ที่ติดตั้งในระบบปฏิบัติการ Linux lsusb จะแสดงข้อมูลเพิ่มเติมเกี่ยวกับแต่ละอุปกรณ์ USB เช่น Vendor ID, Product ID, และรุ่นของอุปกรณ์นั้นๆ<br><br>

Syntax: $ lsusb <br>

Output:<br>
![]
ข้อควรระวังในการใช้งาน<br>
ในบางกรณี อาจต้องใช้สิทธิ์ root เพื่อเรียกใช้คำสั่ง lsusb เพราะต้องการสิทธิ์สำหรับการอ่านข้อมูลจาก USB หรือการ์ดส่วนเสริม <br><br>

<div align="center">  lspcmcia
</div>
บทบาทหน้าที่ของ lspcmcia<br>
เป็นคำสั่งในระบบปฏิบัติการ Linux ที่ใช้สำหรับแสดงข้อมูลเกี่ยวกับการต่อการ์ด PCMCIA (Personal Computer Memory Card International Association) ที่เชื่อมต่อกับเครื่องคอมพิวเตอร์ สามารถดูรายการของการ์ด PCMCIA ที่เชื่อมต่อกับเครื่อง Linux ได้ รวมถึงรายละเอียดเกี่ยวกับแต่ละการ์ด เช่น ชื่อของการ์ด, รุ่น, และสถานะของการ์ดนั้นๆ<br><br>

หลักการทำงานของ lspcmcia<br>
บน linux เมื่อใช้คำสั่ง lspcmcia ระบบจะทำการสร้างข้อมูลเกี่ยวกับการ์ด PCMCIA ที่เชื่อมต่อกับเครื่อง<br><br>

Syntax: $ lspcmcia <br>

Output:<br>
Socket 0 Bridge:        [yenta_cardbus]           (bus ID: 0000:02:04.0)<br>
Configuration:	 state: on<br>
Socket 0 Device 0:	[serial_cs]              (bus ID: 0.0)<br>
Configuration:	state: on<br>
Product Name:	Some Serial Device<br>
Identification:	serial_cs<br>
Manufacturer:	Some Manufacturer<br>
Product:	Some Serial Device<br>
Release:	2.6.32-042stab139.1<br>
