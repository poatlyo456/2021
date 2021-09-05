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



