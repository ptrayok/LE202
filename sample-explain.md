# อธิบายการทดลอง
### Example 01 Serial Monitor
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
![image](https://user-images.githubusercontent.com/98943439/153911472-055e4ae9-5eb3-4a7f-aa76-db88485742d7.png)

WiFi.mode(WIFI_STA) --> การตั้งค่า Wifi เป็นโหมด AP

WiFi.disconnect() --> คำสั่งตัดการเชื่อมต่อกับ Wifi อื่นๆ

ในที่นี้ กำหนดการทำงานของการค้นหา เป็นลูปค้นหาไปเรื่อยๆ และแสดงผลออกมาเรื่อยๆ

serial.println() --> แสดงผลข้อมูลออกมา และทำการขึ้นบรรทัดใหม่

WiFi.scanNetworks() --> ทำการค้นหาสัญญาณ Wifi 

WiFi.SSID() --> ดึงค่า SSID และทำการแสดงผลชื่อสัญญาณ

WiFi.RSSI() --> ดึงค่าความแรงสัญญาณ และแสดงผลค่าความแรงสัญญาณ

WiFi.channel(i) -->  ดึงค่า channel ของสัญญาณ และแสดงผลช่องสัญญาณ
