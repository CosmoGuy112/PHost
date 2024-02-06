# Host Configuration

Host บน Linux มีบทบาทและหน้าที่หลากหลายที่สำคัญต่อการทำงานของระบบปฏิบัติการและการเชื่อมต่อในเครือข่าย ดังนี้:

- ชื่อโฮสต์ (Hostname):
ชื่อโฮสต์เป็นตัวแทนของเครื่องในเครือข่าย มันช่วยให้คนหรือระบบอื่น ๆ สามารถระบุและเชื่อมต่อกับเครื่องของเราได้
การตั้งค่าชื่อโฮสต์ใน Linux เป็นส่วนหนึ่งของการกำหนดค่าระบบ และสามารถทำผ่านคำสั่ง hostname หรือการแก้ไขไฟล์ /etc/hostname และ /etc/hosts

- การกำหนดค่าเครือข่าย (Network Configuration):
Host ต้องมีการกำหนดค่าเครือข่ายให้เหมาะสม เพื่อให้สามารถเชื่อมต่อกับเครือข่ายได้ถูกต้อง
การตั้งค่า IP address, netmask, gateway, DNS server และการกำหนดค่าอื่น ๆ สามารถทำผ่านไฟล์ /etc/network/interfaces หรือไฟล์ที่เกี่ยวข้องกับเครือข่าย

- การกำหนดค่าความปลอดภัย (Security Configuration):
Host ต้องมีการกำหนดค่าความปลอดภัยเพื่อป้องกันการเข้าถึงไม่จำเป็นและการโจมตี.
การใช้ไฟร์วอลล์ (firewall) เพื่อควบคุมการเข้าถึง, การปิดใช้งานบริการที่ไม่จำเป็น, การตั้งค่าการให้สิทธิ์ผู้ใช้ และการดูแลรักษาความปลอดภัยทั่วไป

- การกำหนดค่าผู้ใช้ (User Configuration):
Host ต้องมีการจัดการผู้ใช้งานที่เข้าถึงระบบ
การสร้าง, แก้ไข, และลบผู้ใช้งาน, การกำหนดรหัสผ่าน, และการจัดการสิทธิ์ผู้ใช้โดยใช้ไฟล์ /etc/passwd, /etc/shadow, และ /etc/group

- การกำหนดค่าเวลา (Time Configuration):
Host ต้องมีการกำหนดค่าเวลาให้ถูกต้อง เพื่อป้องกันปัญหาการทำงานและการเชื่อมต่อในเครือข่าย
การใช้คำสั่ง timedatectl เพื่อตั้งค่าเวลาและโซนเวลา, การใช้ NTP (Network Time Protocol) เพื่อซิงโครไนส์เวลากับเซิร์ฟเวอร์ NTP

- การจัดการแพ็กเกจ (Package Management):
Host ต้องมีการจัดการแพ็กเกจที่ติดตั้งบนระบบ เพื่อให้ระบบปฏิบัติการมีความเสถียรและปลอดภัย
การใช้ package manager เช่น apt, yum, หรือ zypper เพื่อติดตั้ง, อัปเดต, และลบแพ็กเกจ
การจัดการ Host บน Linux เป็นส่วนสำคัญของการบริหารระบบและรักษาความปลอดภัยของระบบทั้งหมดในเครือข่าย



## หลักการทำงานของ Host Configuration 

Host Configuration file จะให้บริการการตั้งค่าและจัดการการแปลงชื่อ host เป็น IP ท้องถิ่น และการแทนที่การแก้ไข DNS บนระบบ Linux  โดย path คือ /etc/hosts และไฟล์ข้อความธรรมดาที่แมปชื่อ host กับที่อยู่ IP ที่เป็นไฟล์ระบบและต้องใช้สิทธ์ root หรือสิทธิ์ผู้ดูแลระบบเพื่อทำการปรับเปลี่ยน 

ไฟล์ช่วยให้เรากำหนดค่าแมปชื่อโฮสต์เป็นไอพีที่กำหนดเองสำหรับระบบท้องถิ่นของเราแต่ละบรรทัดในไฟล์ hosts จะปฏิบัติตามรูปแบบที่เฉพาะเจาะจง ประกอบด้วยที่อยู่ไอพีที่ตามด้วยชื่อโฮสต์หนึ่งหรือมากกว่าที่แยกด้วยช่องว่าง ที่อยู่ไอพีมักจะตามด้วยชื่อโฮสต์ที่เกี่ยวข้อง 

ไฟล์ hosts ยังสามารถจัดการที่อยู่ไอพีเวอร์ชัน 6 และที่อยู่ไอพีเวอร์ชัน 4 ได้เช่นกัน


## Hostname
Configure a static hostname:
คือการเปลี่ยนชื่อ hostname ของเครื่องเราโดยที่ถ้าเรา reboot ใหม่ ชื่อจะคืนค่ากลับมาเป็นเหมือนเดิม
โดยการระบุของ hostname ของเราจะสามารถใช้คำสั่งได้ดังนี้ :

```
$ hostname
```

และในการ Configure hostname แบบ static จะสามารถใช้คำสั่งได้ดังนี้ :
โดยจะลองเปลี่ยนเป็น test.example.com

```
$ hostname test.example.com
```
ผลลัพธ์มีดังนี้ :
 
![hostname](https://github.com/CosmoGuy112/PHost/assets/112687431/74739192-08f6-4fc6-932c-c96b6bb56e95)


Configure a persistent hostname
คือ การเปลี่ยนชื่อ hostname ของเครื่องเราโดยใน Config ส่วนนี้จะทำการเปลี่ยนค่า default เลย โดยจะเข้าไป config ใน /etc/hostname
โดยคำสั่งในการเปลี่ยนค่า hostname ในส่วนนี้คือ :

```
$ hostnamectl set-hostname test2.example.com
```

โดยจะสามารถเช็คค่า hostname ที่เปลี่ยนไปได้ใน

```
cat /etc/hostname
```

ผลลัพธ์มีดังนี้ :

![Screenshot 2024-02-07 002738](https://github.com/CosmoGuy112/PHost/assets/112687431/9ea4116a-1e0f-443b-bac8-7e5b2284223d)

# References
<li>https://tldp.org/HOWTO/Xterminals/configuration.html</li>
<li>https://www.redhat.com/sysadmin/configure-hostname-linux</li>
<li>https://devconnected.com/how-to-set-date-and-time-on-linux/</li>
<li>https://www.scaler.com/topics/ntp-in-linux/</li>
<li>https://support.huawei.com/enterprise/en/doc/EDOC1100318951/aad02e92/linux-host-security-protection</li>
<li>https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/virtualization_security_guide/chap-virtualization_security_guide-host_security</li>
