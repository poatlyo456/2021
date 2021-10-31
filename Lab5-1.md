# Lab 5-1 請使用兩個伺服馬達同步從 0 度逐步掃描到 180 度之後再逐步掃描回0度, 每步的間隔時間為50ms (0.05秒), 細節請參考以下Demo.

## 電路圖 
![image](https://user-images.githubusercontent.com/89329121/139566544-359670d8-7f14-4e58-9ada-0867486940f7.png)

## 程式碼

````c
#include <Servo.h>

int pos = 0;

Servo servo_9;
Servo servo_8;
void setup()
{
  servo_9.attach(9, 500, 2500);
  servo_8.attach(8, 500, 2500);  
}

void loop()
{
// 從 0 到 180 度逐步掃描伺服, 1度/步
  for (pos = 0; pos <= 180; pos += 1) {

    servo_9.write(pos);
    servo_8.write(pos);       

    delay(50); // 等50ms (0.05秒)
  }
  
  for (pos = 180; pos >= 0; pos -= 1) {
// 從 180 到 0 度逐步掃描伺服, 1度/步
    servo_9.write(pos);
    servo_8.write(pos);        

    delay(50); // 等50ms (0.05秒)
  }
}
````
