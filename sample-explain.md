# อธิบายการทดลอง
### Example 01 Serial Monitor
โปรแกรม Run เป็น Loop เพื่อนับค่าตัวแปร โดยการหน่วงเวลาระหว่างการรับ 1000ms 
![image](https://user-images.githubusercontent.com/98943439/153910068-b5ee7572-0ad9-44f9-a059-2368111f49ea.png)

#include --> การเรียกฟังก์ชันที่มีการกำหนดไว้แล้ว

int cnt = 0 --> การกำหนดตัวแปรนับ เป็น cnt มีค่าเริ่มต้น = 0

void setup() --> ฟังก์ชั่นที่ run รอบเดียว

Serial.begin() --> การตั้งความเร็วการสื่อสาร bit/s

void loop() --> ฟังก์ชั่น run วนลูปไปเรื่อยๆ

cnt++ --> นับตัวแปร cnt เพิ่มทีละ 1

serial.printf --> การแสดงผลค่าตัวแปร

delay(1000) --> การหน่วงเวลา 1000ms ต่อการวน 1 ลูป

### Example 02 Scan Wifi
โปรแกรมการค้นหาสัญญาณ Wifi โดยยกเลิกการเชื่อมต่อก่อนหน้า และค้นหาวนลูปไปเรื่อยๆ
![image](https://user-images.githubusercontent.com/98943439/153911472-055e4ae9-5eb3-4a7f-aa76-db88485742d7.png)

WiFi.mode(WIFI_STA) --> การตั้งค่า Wifi เป็นโหมด AP

WiFi.disconnect() --> คำสั่งตัดการเชื่อมต่อกับ Wifi อื่นๆ

ในที่นี้ กำหนดการทำงานของการค้นหา เป็นลูปค้นหาไปเรื่อยๆ และแสดงผลออกมาเรื่อยๆ

serial.println() --> แสดงผลข้อมูลออกมา และทำการขึ้นบรรทัดใหม่

WiFi.scanNetworks() --> ทำการค้นหาสัญญาณ Wifi 

WiFi.SSID() --> ดึงค่า SSID และทำการแสดงผลชื่อสัญญาณ

WiFi.RSSI() --> ดึงค่าความแรงสัญญาณ และแสดงผลค่าความแรงสัญญาณ

WiFi.channel(i) -->  ดึงค่า channel ของสัญญาณ และแสดงผลช่องสัญญาณ

### Example 03 Output Port
ส่งสัญญาณออกมาตามที่กำหนด โดย High เป็น On Low เป็น Off
![image](https://user-images.githubusercontent.com/98943439/153913488-93105ca2-7fb7-4c1a-bb41-ad3216bf7ad8.png)

pinMode() --> กำหนดการทำงานของแต่ละ pin

difitalWrite() -->  สั่งงานให้ output ค่า HIGH/LOW ที่ขา digital output ของบอร์ด

### Example 04 Input Port
รับค่า Input มาตรวจสอบ เพื่อส่งสัญญาณ Output ออกไป
![image](https://user-images.githubusercontent.com/98943439/153914168-4ea505ce-a232-4554-a8fe-683d3fea946c.png)

digitalRead() --> คำสั่งอ่านค่าสถานะของ input pin

digitalWrite() --> คำสั่งเขียนค่า HIGH/LOW ไปยัง Output pin

### Example 05 Wifi Web Sever
เชื่อมต่อเข้ากับสัญญาณ Wifi และทำการสร้าง Websever จากนั้นทำการตรวจสอบผู้มาเชื่อมต่อ Websever
![image](https://user-images.githubusercontent.com/98943439/153914433-9993f7b5-c1f2-44ce-a740-73c08ca02ea1.png)

const char* ssid = "Username" --> กำหนดตัวแปรเก็บ ssid ของ Wifi

cons char* password = "Password" --> กำหนดตัวแปรเก็บ password ของ Wifi

ESP8266WebSever sever(80) --> เปิด Websever ที่ Port 80

WiFi.mode(WIFI_STA) --> ตั้งค่า wifi เป็นโหมดสถานี

WiFi.begin(ssid,password) --> สำหรับเชื่อมต่อสัญญาณ

### Example 06 Wifi AP Web Sever
สร้าง Wifi Access Point โดยการกำหนดชื่อ และรหัสผ่าน จากนั้นทำการตรวจสอบเครื่องลูกข่ายที่มาเชื่อมต่อ
![image](https://user-images.githubusercontent.com/98943439/153914582-e634ab03-3384-48fa-ae4a-976243912d9d.png)

locap_ip --> สำหรับตั้ง IP ของ AP

gateway --> สำหรับตั้ง IP ของ Gateway

subnet --> สำหรับตั้ง subnet mark ของ Wifi

WiFi.softAP(ssid,password) --> ตั้งค่า wifi ในโหมด Access point 

WiFi.softAPConfig(IP,gateway,subnet); --> การตั้งค่า IP gateway subnet ตามค่าที่ใส่ไว้

sever.on --> การเริ่มต้นปล่อยสัญญาณ  Wifi
