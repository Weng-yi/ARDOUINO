# ARDOUINO
學習ardouino過程 </p>
void setup(){}--只執行一次,Ardouino的初始設定] </p>
void loop(){}--會重複執行,主程式的位置 </p>
第一個命令 </p>
pinMode(腳位模式, INPUT/OUTPUT) </p>
腳位模式設定:所使用的腳位設定為輸入(INPUT)或輸出(OUTPUT) </p>
腳位INPUT時,初始職狀態為1 </p>
腳位OUTPUT時,初始職狀態為0 </p>
------------------------------------------- </p>
第一個程式:功能LED閃爍0.5秒,暗0.5秒 </p>
電路圖如下: </p>
![image](https://github.com/Weng-yi/ARDOUINO/blob/master/A4BB146F-B086-493C-8548-44850737F47A.jpeg) </p>
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
