ในหน้าControl
-เพิ่ม mornitoring ทางขวาแสดงค่าgood wp, ng wp แล้วก็ค่าที่รับมาจากsetpoint(wp set)ที่สามารถแสดงผลแบบreal time 
-good wp DB1 ofset4.0
-ng wp DB1 ofset 6.0
-wp set DB1 ofset 2.0

Monitoring ในหน้า Control แสดงค่าล่าสุดที่ได้รับจาก Node-RED โดยส่ง `msg.payload` เป็น object รูปแบบนี้:

```js
{ goodWp: 0, ngWp: 0, setpoint: 0 }
```

ส่งค่าแยกทีละรายการได้โดยใช้ `msg.topic` เป็น `goodWp`, `ngWp` หรือ `setpoint` และ `msg.payload` เป็นค่าตัวเลข

| ค่า | Address ที่แสดง | ชนิดข้อมูล |
| --- | --- | --- |
| GOOD WP | DB1.DBW4 | INT |
| NG WP | DB1.DBW6 | INT |
| WP SET | DB1.DBW2 | INT |