# 嵌入式系統 - 實作2: 會呼吸的RGB LED,  按鍵控制, 狀態輸出

## 實作2-1, analogWrite(): 並且觀查LED亮度變化是否有像"呼吸的效果"和示波器的波形有什麼關連性?

### 電路圖
![image](https://user-images.githubusercontent.com/89329121/132114965-6f607ad8-67fe-4a3a-80b0-ab1924f5bfed.png)
### 程式
````c
// C++ code
//

int brightness =0;

void setup()
{
  pinMode(9, OUTPUT);
}

void loop()
{
  for (brightness =0; brightness <=255; brightness +=5){
    analogWrite(9,brightness);
    delay(30);
  }
  for (brightness =255; brightness <=0; brightness -=5){
    analogWrite(9,brightness);
    delay(30);
  }
}

````

## 實作2-2, RGB LED燈全彩模組, 分別讓LED輪流表現正紅、正綠、正藍，三個顏色，時間間隔1秒鐘。並且觀查LED顏色和波形或是電壓有什麼關連性? 可將個人說明在更新GitHub時一起加入.

### 電路圖
![image](https://user-images.githubusercontent.com/89329121/132115004-4d4a66ae-c4e1-4df8-bcb2-107fcc422f0a.png)
### 程式

````c
// C++ code
//
int R = 9;
int G = 10;
int B = 11;

void setup()
{
  pinMode(R, OUTPUT);
  pinMode(G, OUTPUT);
  pinMode(B, OUTPUT);  
}

void loop()
{
	analogWrite(R, 255);
	analogWrite(G, 0);
	analogWrite(B, 0);
  	delay(1000);
	analogWrite(R, 0);
	analogWrite(G, 255);
	analogWrite(B, 0);
  	delay(1000);
	analogWrite(R, 0);
	analogWrite(G, 0);
	analogWrite(B, 255);
  	delay(1000);  
````

## 實作2-3, 讓你的RGB LED燈全彩模組也可會"呼吸", LED顏色變化是否有像"呼吸的效果"和示波器的波形有什麼關連性?

### 電路圖
![image](https://user-images.githubusercontent.com/89329121/132971143-7c7aac2a-918c-4184-8edc-1b57b7f671b5.png)

### 程式

````c
int brightness = 0;
int Red = 9;
int Green = 10;
int Blue = 11;
int number = 5;
void setup()
{
  pinMode(Red, OUTPUT);
  pinMode(Green, OUTPUT);
  pinMode(Blue, OUTPUT);
}

void loop()
{
//Red
  for ( brightness = 0 ; brightness <=255 ; brightness +=number){
  	analogWrite(Red,brightness);
    delay(50);
  }
  
  for ( brightness = 255 ; brightness >=0 ; brightness -=number){
  	analogWrite(Red,brightness);
    delay(50);
  }
  delay(500);
//Green
  for ( brightness = 0 ; brightness <=255 ; brightness +=number){
  	analogWrite(Green,brightness);
    delay(50);
  }
  
  for ( brightness = 255 ; brightness >=0 ; brightness -=number){
  	analogWrite(Green,brightness);
    delay(50);
  }
  delay(500);
//Blue
  for ( brightness = 0 ; brightness <=255 ; brightness +=number){
    analogWrite(Blue,brightness);
    delay(50);
  }

  for ( brightness = 255 ; brightness >=0 ; brightness -=number){
    analogWrite(Blue,brightness);
    delay(50);
  }
  delay(500);
}

````

## 實作2-4 analogRead(), 1024解析度 (i.e.,10-bit): 可變電阻 + 序列監視器與輸出; 當你改變可變電阻的阻值(e.g., 10K-ohm)時，序列監視器輸出的數值有什麼改變? 數值又有什麼意義呢?
<analogRead(A0), 10-bit: 0 ~ 1023

### 電路圖
![image](https://user-images.githubusercontent.com/89329121/132971515-6a058446-0786-489e-8873-a01ef7fda452.png)

### 程式

````c
// C++ code
//
int sensorValue = 0;

void setup()
{
  pinMode(A0, INPUT);
  Serial.begin(9600);

}

void loop()
{
  // read the input on analog pin 0:
  sensorValue = analogRead(A0);
  // print out the value you read:
  Serial.println(sensorValue);
  delay(10); 
}
````

<digitalRead(): 按鍵 + 序列監視器與輸出說明與介紹

### 電路圖
![image](https://user-images.githubusercontent.com/89329121/132971719-f826f77f-f4b5-4918-be42-4c26d9d61e89.png)

### 程式
````c
// C++ code
//
int sensorValue = 0;

void setup()
{
  pinMode(A0, INPUT);
  Serial.begin(9600);

}

void loop()
{
  // read the input on analog pin 0:
  sensorValue = analogRead(A0);
  // print out the value you read:
  Serial.println(sensorValue);
  delay(10); 
}
````



