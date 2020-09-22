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

```
第三個程式 功能LED由左至右逐一亮滅,功能如下</p>
初始狀態 ○○○○</p>
STEP1   ●○○○</p>
STEP2   ○●○○</p>
STEP3   ○○●○</p>
STEP4   ○○○●</p>
程式碼如下:
```C++
 int LED=9;
void setup() {
 
  for (int i=2 ;i<6;i++)
   pinMode(i,OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
  for(int i=6;i>1; i--)
    digitalWrite(i,HIGH);
   if (LED>=2)
      digitalWrite(LED,LOW);
   else
      LED=6;
  LED--;  


delay(100);
}
```

第四個程式 功能LED由左至右逐一亮滅,功能如下</p>
初始狀態 ○○○○○○○○</p>
STEP1   ●○○○○○○○</p>
STEP2   ○●○○○○○○</p> 
STEP3   ○○●○○○○○</p>
STEP4   ○○○●○○○○</p>
STEP5   ○○○○●○○○</p>
STEP6   ○○○○○●○○</p>
STEP7   ○○○○○○●○</p>
STEP8   ○○○○○○○●</p>
STEP9 回到初始值狀態
程式碼如下:
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
---
電路配置圖如下:
![image](https://github.com/Weng-yi/ARDOUINO/blob/master/5AFD3FC0-DE91-446C-A8E5-BE80FF31FE46.jpeg) </p>

加分題目 初始狀態○○○○○○○○</p>
STEP1   ○○○○○○○●</p>
STEP2   ○○○○○○●○</p> 
STEP3   ○○○○○●○○</p>
STEP4   ○○○○●○○○</p>
STEP5   ○○○●○○○○</p>
STEP6   ○○●○○○○○</p>
STEP7   ○●○○○○○○</p>
STEP8   ●○○○○○○○</p>
STEP9 回到初始值狀態
程式碼如下:
```C++
 int LED=1;
void setup() {
 
  for (int i=2 ;i<10;i++)
 {
   pinMode(i,OUTPUT);
   digitalWrite(i,1);
}
}


void loop() {
  // put your main code here, to run repeatedly:
  for(int i=1;i<10; i++)
{
    digitalWrite(i,0);
   delay(100);
      digitalWrite(i,1);
}
```
類比輸出的方式為analogWRITE(角位,值)</p>
腳位必須是要有在Arduino UNO版上有"~"符號</p>
值可填入0-255</p>
請實作出呼吸燈的程式</p>
呼吸燈的功能從暗到亮在到暗的循環 每隔100mS變換亮度
程式碼如下:
```C++
 int value=255; int x=-15;
void setup() {
   //put your setup code here, to run once:
 pinMode(3,OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
if (value<=0|| value>=255) x=-x;
analogWrite(3,value);
delay(30);
value=value-x; 
}
```
電路配置圖如下:
![image]() </p>

第五個程式:

程式碼如下:
```C++
void setup() {
  // put your setup code here, to run once:
  pinMode(2,INPUT);
  pinMode(3,OUTPUT);
  digitalWrite(3,HIGH);
  

}

void loop() {
  // put your main code here, to run repeatedly:
if(digitalRead(2)==0)
digitalWrite(3,LOW);
}
```
電路配置圖如下:
![image]() </p>

第六個程式:

程式碼如下:
```C++
int a=0;
void setup() {
  // put your setup code here, to run once:
  pinMode(2,INPUT);
  pinMode(3,OUTPUT);
  digitalWrite(3, HIGH);
  //Serial.begin(9600);
}

void loop(){
  //put your code here, to run repeatedly:

if(digitalRead(2)==0);
{
  while (digitalRead(2)==0);
  //Serial.print(digitalRead(2));
  a=(a+1)%2;
}
  //Serial.print(digitalRead(2));
  //Serial.print(a);
  switch(a)
  {case 1:
  {digitalWrite(3,HIGH);}
  case 0:
  {digitalWrite(3,HIGH);}}
}
```
電路配置圖如下:
![image]() </p>
int value=0;
void setup() 
{  // put your setup code here, to run once:
  pinMode(2,INPUT);
  pinMode(3,OUTPUT);
  digitalWrite(3, HIGH);
  
}

void loop(){
  
if(digitalRead(2)==0);
{
  while (digitalRead(2)==0){
 delay(30);//Wait for 20 millisecond(s)
  }
 if(value==0){
  value=1;
  digitalWrite(3,LOW);
 }else{
  value=0;
  digitalWrite(3,HIGH);
 }
}
}
 
