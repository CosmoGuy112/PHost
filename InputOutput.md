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
![2024-02-06 (2)](https://github.com/CosmoGuy112/PHost/assets/112687372/ba698f94-a334-4a2f-9d2f-2c4acbcf6371)

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
![2024-02-06 (4)](https://github.com/CosmoGuy112/PHost/assets/112687372/c24c3366-b697-4e4e-ab42-3a0a10ea31d5)

ข้อควรระวังในการใช้งาน<br>
ในกรณีที่จะทำการดำเนินการอะไรกับการ์ด PCMCIA ที่แสดงใน lspcmcia ควรทำการสำรองข้อมูลก่อนเพื่อป้องกันการสูญเสียข้อมูล<br><br>

<div align="center">  lsdev
</div>
บทบาทหน้าที่ของ lsdev<br>
เป็นคำสั่งที่ใช้สำหรับแสดงรายการของอุปกรณ์ที่เชื่อมต่อกับระบบปฏิบัติการ Linux ซึ่งรวมถึงอุปกรณ์ที่เชื่อมต่อผ่านพอร์ต หรือโมดูลของคอมพิวเตอร์เช่น USB, PCI, และอุปกรณ์ต่างๆที่ติดตั้งในระบบ<br><br>

หลักการทำงานของ lspcmcia<br>
lsdev จะสแกนระบบเพื่อตรวจสอบอุปกรณ์ที่เชื่อมต่อทั้งหมด แล้วจะแสดงรายการของอุปกรณ์ทั้งหมดที่พบในระบบ รวมถึงรายละเอียดเกี่ยวกับแต่ละอุปกรณ์<br><br>

Syntax :$ lsdev<br>

Output:<br>
class          type           subclass   description<br>
logical_volume vgtype         vgsubclass Volume group<br>
logical_volume lvtype         lvsubclass Logical volume<br>
lvm            lvdd           lvm        LVM Device Driver<br>
posix_aio      posix_aio      node       Posix Asynchronous I/O<br>
aio            aio            node       Asynchronous I/O (Legacy)<br>
pty            pty            pty        Asynchronous Pseudo-Terminal<br>
mouse          030102         usbif      USB mouse<br>
keyboard       030101         usbif      USB keyboard<br>
.<br>
.<br>
.<br>
disk           540mb2         scsi       540 MB SCSI Disk Drive<br>
disk           540mb3         scsi       540 MB SCSI Disk Drive<br>
disk           540mb4         scsi       540 MB SCSI Disk Drive<br>
disk           540mb5         scsi       540 MB SCSI Disk Drive<br>
disk           730mb2         scsi       730 MB SCSI Disk Drive<br>
disk           810mb          scsi       810 MB SCSI Disk Drive<br>
disk           810mb2         scsi       810 MB SCSI Disk Drive<br>
bus            pcic           pci        PCI Bus<br>
bus            isac           pci        ISA Bus<br>
adapter        df1000f9       pci        FC Adapter<br>
adapter        df1000f7       pci        FC Adapter<br>
driver         efscsi         iocb       FC SCSI I/O Controller Protocol Device<br>
adapter        c1110358       pci        USB OHCI Adapter (c1110358)<br>
adapter        ad100501       pci        ATA/IDE Controller Device<br>
adapter        4f111100       pci        IBM 8-Port EIA-232/RS-422A (PCI) Adapter<br>
adapter        ccm            pci        Name of the Common Character Mode device driver<br>
driver         hdlc           331121b9   IBM HDLC Network Device Driver<br>
adapter        331121b9       pci        IBM 2-Port Multiprotocol Adapter (331121b9)<br>
adapter        2b102005       pci        GXT130P Graphics Adapter<br>
adapter        2b101a05       pci        GXT120P Graphics Adapter<br>
adapter        23100020       pci        IBM 10/100 Mbps Ethernet PCI Adapter (23100020)<br>
.<br>
.<br>
.<br>
if             tr             TR         Token Ring Network Interface<br>
if             vi             VI         Virtual IP Address Network Interface<br>
if             xt             XT         X.25 Network Interface<br>
tcpip          inet           TCPIP      Internet Network Extension<br>
swap           paging         nfs        NFS Swap DEVICE<br>
drawer         media1         media      SCSI Device Drawer<br>
drawer         scsi1          dasd       SCSI DASD Drawer<br>
adapter        4f111b00       pci        IBM 128-Port Async (PCI) Adapter<br>
concentrator   16c232         sync_pci   16-Port RAN EIA-232 for 128-Port Adapter<br>
concentrator   16e232         sync_pci   16-Port Enhanced RAN EIA-232 for 128-Port Adapter<br>
concentrator   16e422         sync_pci   16-Port Enhanced RAN RS-422 for 128-Port Adapter<br>
if             at             AT         ATM Network Interface<br>
adapter        14105300       pci        IBM PCI 25MBPS ATM Adapter (14105300)<br>

ข้อควรระวังในการใช้งาน<br>
อาจแสดงข้อมูลที่มีรายละเอียดมากเกินไปหรือที่ไม่จำเป็นต่อการใช้งาน และอาจทำให้ยุ่งยากในการอ่านและการทำงาน ควรพิจารณาเฉพาะข้อมูลที่เป็นประโยชน์และสำคัญสำหรับงานที่คุณกำลังดำเนินการ<br><br>

<div align="center">  lspci
</div>
บทบาทหน้าที่ของ lsdev<br>
lsusb เป็นคำสั่งที่ใช้ เพื่อแสดงรายการของอุปกรณ์ที่เชื่อมต่อผ่านช่องเชื่อมต่อ USB กับคอมพิวเตอร์<br><br>

หลักการทำงานของ lspcmcia<br>
หลักการทำงาน lsusb จะดึงข้อมูลที่เกี่ยวข้องกับอุปกรณ์ USB ที่ตรวจพบ รวมถึง Vendor ID, Device ID, และข้อมูลอื่นๆ แล้วจะแสดงรายการของอุปกรณ์ USB ที่ตรวจพบ
<br><br>

Syntax:# lspci<br>

Output:<br>
00:00.0 Host bridge: Intel Corporation 5500 I/O Hub to ESI Port (rev 13)<br>
00:01.0 PCI bridge: Intel Corporation 5520/5500/X58 I/O Hub PCI Express Root Port 1 (rev 13)<br>
00:09.0 PCI bridge: Intel Corporation 7500/5520/5500/X58 I/O Hub PCI Express Root Port 9 (rev 13)<br>
00:14.0 PIC: Intel Corporation 7500/5520/5500/X58 I/O Hub System Management Registers (rev 13)<br>
00:14.1 PIC: Intel Corporation 7500/5520/5500/X58 I/O Hub GPIO and Scratch Pad Registers (rev 13)<br>
00:14.2 PIC: Intel Corporation 7500/5520/5500/X58 I/O Hub Control Status and RAS Registers (rev 13)<br>
00:1a.0 USB controller: Intel Corporation 82801I (ICH9 Family) USB UHCI Controller #4 (rev 02)<br>
00:1c.0 PCI bridge: Intel Corporation 82801I (ICH9 Family) PCI Express Port 1 (rev 02)<br>
00:1d.0 USB controller: Intel Corporation 82801I (ICH9 Family) USB UHCI Controller #1 (rev 02)<br>
00:1e.0 PCI bridge: Intel Corporation 82801 PCI Bridge (rev 92)<br>
00:1f.0 ISA bridge: Intel Corporation 82801IB (ICH9) LPC Interface Controller (rev 02)<br>
00:1f.2 IDE interface: Intel Corporation 82801IB (ICH9) 2 port SATA Controller [IDE mode] (rev 02)<br>
01:00.0 Ethernet controller: Broadcom Corporation NetXtreme II BCM5709 Gigabit Ethernet (rev 20)<br>
01:00.1 Ethernet controller: Broadcom Corporation NetXtreme II BCM5709 Gigabit Ethernet (rev 20)<br>
03:00.0 RAID bus controller: LSI Logic / Symbios Logic MegaRAID SAS 2108 [Liberator] (rev 05)<br>
06:03.0 VGA compatible controller: Matrox Electronics Systems Ltd. MGA G200eW WPCM450 (rev 0a)<br>

ข้อควรระวังในการใช้งาน<br>
บางครั้งการเรียกใช้ lsusb อาจต้องใช้สิทธิ์ของผู้ใช้ root เพื่อแสดงข้อมูลที่เชื่อถึงอุปกรณ์ USB ได้เต็มที่ หากไม่ได้ใช้สิทธิ์นี้<br><br>

บทบาทหน้าที่ของ lsblk
lsblk เป็นยูทิลิตี้บรรทัดคำสั่งที่ใช้สำหรับแสดงรายการอุปกรณ์บล็อกบนระบบ Linux อุปกรณ์บล็อกประกอบด้วยอุปกรณ์เก็บข้อมูลที่เก็บข้อมูลในรูปแบบของบล็อก ซึ่งโดยทั่วไปคือฮาร์ดดิสก์ไดรฟ์ (HDD) หรือไดรฟ์โซลิดสเทต (SSD)<br><br>

หลักการทำงานของ lsblk
หลักการทำงานของ lsblk คือการสแกนและแสดงข้อมูลเกี่ยวกับอุปกรณ์บันทึกข้อมูลทั้งหมดที่เชื่อมต่อกับระบบ Linux เพื่อให้ผู้ใช้สามารถเข้าใจโครงสร้างของระบบสําหรับการจัดเก็บข้อมูลได้ง่ายขึ้น และจัดการกับพาร์ติชันและอุปกรณ์เกี่ยวกับการเก็บข้อมูลได้อย่างมีประสิทธิภาพ<br><br>

Syntax: $ lsblk <br><br>
Output:<br>
![lsblk](https://github.com/CosmoGuy112/PHost/assets/109953192/7cc0830d-a1b4-4644-9cb8-90c22117ee30)
