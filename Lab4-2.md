## Lab 4-2 如下圖的Demo, 用七段顯示器, 顯示 . →1→ ... → 9 → 0 → 全滅, 狀態改變的間隔時間為0.5秒
### 電路圖
![image](https://user-images.githubusercontent.com/89329121/137610514-0c867eb0-157d-4842-ba11-da718ed502fc.png)
### 程式
````C
// C++ code
//
void setup()
{
for(int x = 1; x < 9; x++) {
pinMode(x,OUTPUT);
}
}

void seg71(int a, int b, int c, int d, int e, int f, int g, int h)
{
digitalWrite(1, a);
digitalWrite(2, b);
digitalWrite(3, c);
digitalWrite(4, d);
digitalWrite(5, e);
digitalWrite(6, f);
digitalWrite(7, g);
digitalWrite(8, h);
delay(500);
}

void loop()
{
//    a, b, c, d, e, f, g, h
  seg71(0, 0, 0, 0, 0, 0, 0, 0); // OFF
  seg71(0, 0, 0, 0, 0, 0, 0, 1); // DF
  seg71(0, 1, 1, 0, 0, 0, 0, 1); //1
  seg71(1, 1, 0, 1, 1, 0, 1, 1); //2
  seg71(1, 1, 1, 1, 0, 0, 1, 1); //3
  seg71(0, 1, 1, 0, 0, 1, 1, 1); //4
  seg71(1, 0, 1, 1, 0, 1, 1, 1); //5
  seg71(1, 0, 1, 1, 1, 1, 1, 1); //6
  seg71(1, 1, 1, 0, 0, 0, 0, 1); //7
  seg71(1, 1, 1, 1, 1, 1, 1, 1); //8
  seg71(1, 1, 1, 1, 0, 1, 1, 1); //9
  seg71(1, 1, 1, 1, 1, 1, 0, 1); //0
}
````
