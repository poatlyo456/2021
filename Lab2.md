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
int R = 9;
int G = 10;
int B = 11;

int DR = 2;
int DG = 4;
int DB = 7;

void setup()
{
  pinMode(13, OUTPUT); // pin 13
  
  pinMode(R, OUTPUT);
  pinMode(G, OUTPUT);
  pinMode(B, OUTPUT);  
  
  pinMode(DR, OUTPUT);
  pinMode(DG, OUTPUT);
  pinMode(DB, OUTPUT);   
}

void loop()
{
  // digitalWrite: 2 state (i.e., 0, 1) Only
  digitalWrite(13, 1); // LED @ pin 13, ON
  
  delay(1000); 
  
  digitalWrite(DR, 1);
  digitalWrite(DG, 0);
  digitalWrite(DB, 0);
  delay(1000);
  digitalWrite(DR, 0);
  digitalWrite(DG, 1);
  digitalWrite(DB, 0);  
  delay(1000);
  digitalWrite(DR, 0);
  digitalWrite(DG, 0);
  digitalWrite(DB, 1);  
  delay(1000);

  digitalWrite(13, 0); // OFF
  digitalWrite(DR, 0); // OFF
  digitalWrite(DG, 0); // OFF
  digitalWrite(DB, 0); // OFF  
  delay(1000);
  
  // analogWrite: The brightness can be adjusted with 256 levels
  for (int i = 0; i<= 255; i++)
  {
  	analogWrite(R, i);
		analogWrite(G, 0);
		analogWrite(B, 0);
    delay(10);
  } // from dark to bright 

  for (int i = 255; i>= 0; i--)
  {
  	analogWrite(R, i);
		analogWrite(G, 0);
		analogWrite(B, 0);
    delay(10); // 10ms = 0.01s
  }  // from bright to dark
  delay(1000);
}

````



