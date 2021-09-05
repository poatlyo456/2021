# 嵌入式系統 - 實作1

## 1.1 在TinkerCAD開一個新的Circuit, 加上一個外部的LED, 並且ON (亮) 1秒, OFF(滅) 1秒
### 電路圖
![image](https://user-images.githubusercontent.com/89329121/132114043-b4ddad31-f377-4ebb-8a25-fe008f3b8695.png)
### 程式
````c
// C++ code
//
void setup()
{
  pinMode(13, OUTPUT);
}

void loop()
{
  digitalWrite(13, HIGH);
  delay(1000); // Wait for 1000 millisecond(s)
  digitalWrite(13, LOW);
  delay(1000); // Wait for 1000 millisecond(s)
}
````

## 1.2 在TinkerCAD開一個新的Circuit, 分別使甪R, G, B三種顏色的LED, ON (亮) 0.5秒, OFF(滅) 0.5秒
### 電路圖
![image](https://user-images.githubusercontent.com/89329121/132114187-8609a17f-6ccd-4126-bdcd-a6e12dd91bc1.png)
### 程式
````c
// C++ code
//
void setup()
{
  pinMode(13, OUTPUT);
  pinMode(11, OUTPUT);
  pinMode(9, OUTPUT);  
}

void loop()
{
  // turn the LED on (HIGH is the voltage level)
  digitalWrite(13, HIGH);
  digitalWrite(11, HIGH);
  digitalWrite(9, HIGH);  
  delay(500); // Wait for 1000 millisecond(s)
  // turn the LED off by making the voltage LOW
  digitalWrite(13, LOW);
  digitalWrite(11, LOW);
  digitalWrite(9, LOW);  
  delay(500); // Wait for 1000 millisecond(s)
}
````
## 1-3 在TinkerCAD開一個新的Circuit, 分別使甪R, G, B三種顏色的LED, 讓LED ON, OFF的順序為R >> G >> B >> G >> R .... 無限循環.
### 電路圖
![image](https://user-images.githubusercontent.com/89329121/132114405-f8dbb186-e3d7-41cc-bc48-ccefa1375e3f.png)
### 程式
````C
void setup()
{
  pinMode(13, OUTPUT);
  pinMode(11, OUTPUT);
  pinMode(9, OUTPUT);
}

void loop()
{
  // turn the LED on (HIGH is the voltage level)
  digitalWrite(13, HIGH);
  digitalWrite(11, LOW);
  digitalWrite(9, LOW);
  delay(500); // Wait for 1000 millisecond(s)
  // turn the LED off by making the voltage LOW
  digitalWrite(13, LOW);
  digitalWrite(11, HIGH);
  digitalWrite(9, LOW);
  delay(500); // Wait for 1000 millisecond(s)
  // turn the LED off by making the voltage LOW
  digitalWrite(13, LOW);
  digitalWrite(11, LOW);
  digitalWrite(9, HIGH);
  delay(500); // Wait for 1000 millisecond(s)  
  digitalWrite(13, LOW);
  digitalWrite(11, HIGH);
  digitalWrite(9, LOW);  
  delay(500); // Wait for 1000 millisecond(s)  
}
````
