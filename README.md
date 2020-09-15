# ARDOUINO
學習ardouino過程
void setup(){}--只執行一次,Ardouino的初始設定]
void loop(){}--會重複執行,主程式的位置
第一個命令
pinMode(腳位模式, INPUT/OUTPUT)
腳位模式設定:所使用的腳位設定為輸入(INPUT)或輸出(OUTPUT)
腳位INPUT時,初始職狀態為1
腳位OUTPUT時,初始職狀態為0
-------------------------------------------
第一個程式:功能LED閃爍0.5秒,暗0.5秒
電路圖如下:
！[image] (https://github.com/Weng-yi/ARDOUINO/blob/master/A4BB146F-B086-493C-8548-44850737F47A.jpeg) </p>
```C++
int LED=9;
void setup() {
 
  for (int i=2 ;i<10;i++)
   pinMode(i,OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
  for(int i=10;i>1; i--)
    digitalWrite(i,HIGH);
   if (LED>=2)
      digitalWrite(LED,LOW);
   else
      LED=10;
  LED--;  


delay(500);
}


```
