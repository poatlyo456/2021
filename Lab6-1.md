# **Lab 6-1 用16X2** LCD 顯示器**來顯示**4X4鍵盤輸入的數字 (0, 1, 2, .., 9), 若輸入的字數≥16則換到下一列, 若兩皆滿, 則清除劃面重新由Row=0, Col=0開始, 細節請參考以下Demo.

## 電路圖
![image](https://user-images.githubusercontent.com/89329121/139566769-8a15a598-2c83-4ead-9365-f6dd043d237b.png)

## 程式碼

````c
#include <Keypad.h>
#include <LiquidCrystal.h>

LiquidCrystal lcd(5, 4, 3, 2, A4, A5);

const byte ROWS = 4; //four rows
const byte COLS = 4; //three columns
char keys[ROWS][COLS] = {
  {'1','2','3','A'},
  {'4','5','6','B'},
  {'7','8','9','C'},
  {'*','0','#','D'}
};
byte rowPins[ROWS] = {A0, A1, 11, 10}; //connect to the row pinouts of the keypad
byte colPins[COLS] = {9, 8, 7, 6}; //connect to the column pinouts of the keypad
int LCDCol = 0;
int LCDRow = 0;

Keypad keypad = Keypad( makeKeymap(keys), rowPins, colPins, ROWS, COLS );


void setup(){
   Serial.begin(9600);
   lcd.begin(16, 2);
   lcd.setCursor(LCDCol, LCDRow);
   }
  
void loop(){
  char key = keypad.getKey();
  
  if (key){
    
    Serial.println(key);
           
    
    if ( LCDCol > 15  )
    {   
     ++LCDRow; // Move to the 2nd row
      
      if (LCDRow>1)
      { LCDRow=0; LCDCol = 0 ;  lcd.clear(); } // clear and move back the 1st row
   
    LCDCol = 0 ;
    }
         
    lcd.setCursor (LCDCol, LCDRow); 
    
       lcd.print(key);
    
    ++LCDCol;
    
  }
}
````
