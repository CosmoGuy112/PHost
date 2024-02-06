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


## Configure Time & Date
ในการตั้งค่า Config วันเละเวลา คำสั่งที่ควรจะรู้คือ :

```
$ timedatectl
```
โดยคำสั่งนี้คือคำสั่งที่จะดูข้อมูลและเวลาปัจจุบันและค่าอื่นๆ

ซึ่งเมื่อพิมพ์คำสั่งจะได้ผลลัพธ์ดังนี้ :

![Screenshot_2024-02-07_003002](https://github.com/CosmoGuy112/PHost/assets/112687431/73464afa-0413-4866-b2c1-32b31566a2a9)

โดย Output ที่แสดงออกมาสามารถบอกได้ดังนี้
- เวลาท้องถิ่น: เวลาที่คอมพิวเตอร์คิดว่าเป็นเวลาตามโซนเวลา (จากรูปเครื่องนี้ local เป็น UTC)
- เวลาสากล: เวลา UTC
- เวลา RTC: เวลาที่ใช้นาฬิกาเรียลไทม์ โดยปกติจะเป็น UTC
- โซนเวลา: ข้อมูลเกี่ยวกับโซนเวลาที่กำหนดค่า
- ซิงโครไนซ์นาฬิการะบบ: ซิงโครไนซ์นาฬิการะบบกับเซิร์ฟเวอร์ NTP หรือไม่
- บริการ NTP: บริการ NTP ของคอมพิวเตอร์ทำงานอยู่หรือไม่
- RTC ใน TZ ท้องถิ่น: ระบุว่านาฬิกาตามเวลาจริงใช้เวลาท้องถิ่นแทน UTC หรือไม่

```
$ timedatectl set-timezone "Asia/Bangkok"
```
โดยคำสั่งนี้คือคำสั่งที่ set timezone ของประเทศไทย

ซึ่งเมื่อพิมพ์คำสั่งจะได้ผลลัพธ์ดังนี้ :

![Screenshot_2024-02-07_003002](https://github.com/CosmoGuy112/PHost/assets/112687431/8338271a-0fc4-4684-9952-396dd91ff917)


```
$ timedatectl set-time "2024-02-02 10:30:00"
```
โดยคำสั่งนี้คือคำสั่งที่สามารถ set เวลาและวันที่ ได้โดยตรงเลยซึ่งต่างกับคำสั่งก่อนหน้าคือเป็นเวลาปัจจุบันของแต่ละ timezone ที่เราจะไปเปลี่ยนแปลง
โดยคำสั่งนี้จะ เรียงตาม "YYYY-MM-DD HH-MM-SS"

ซึ่งเมื่อพิมคำสั่งจะได้ผลลัพธ์ดังนี้ :


![Screenshot 2024-02-07 013217](https://github.com/CosmoGuy112/PHost/assets/112687431/ed62f5c1-8883-467e-bd93-219993c666cf)

โดยก่อนใช้คำสั่ง set-time ได้จะต้องตั้งค่าจะต้องใช้คำสั่ง :

```
sudo systemctl stop systemd-timesyncd.service
```
เพื่อปิดการ Synchronize ของเวลาก็คือให้สามารถ set-time ด้วยตัวเองได้

ส่วนในการเปิด Synchronize ของเวลาจะใช้คำสั่ง :

```
sudo systemctl start systemd-timesyncd.service
```
ซึ่งจะทำให้เวลาคืนค่ามายัง timezone เดิม


# References
<li>https://tldp.org/HOWTO/Xterminals/configuration.html</li>
<li>https://www.redhat.com/sysadmin/configure-hostname-linux</li>
<li>https://devconnected.com/how-to-set-date-and-time-on-linux/</li>
<li>https://www.scaler.com/topics/ntp-in-linux/</li>
<li>https://support.huawei.com/enterprise/en/doc/EDOC1100318951/aad02e92/linux-host-security-protection</li>
<li>https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/virtualization_security_guide/chap-virtualization_security_guide-host_security</li>
<li>https://th.linux-console.net/?p=8474</li>
