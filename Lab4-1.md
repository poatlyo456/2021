# 嵌入式系統 - 實作4: 七段顯示器, LCD 顯示器 + 超音波感測器

## Lab 4-1 用七段顯示器來顯示數字"8."
### 電路圖
![image](https://user-images.githubusercontent.com/89329121/137610374-5164dd38-00f0-4acc-a8a1-484fcd723f15.png)

### 程式
````c
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
seg71(1, 1, 1, 1, 1, 1, 1, 1); // 8
}
````
