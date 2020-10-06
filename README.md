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
程式碼如下:</p>
```C++
oid setup() {
  // put your setup code here, to run once:
PinMode(3,OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
digitalWrite(3,LOW);
delay(500);
digitalWrite(3,HIGH);
delay(500);
}

```
電路圖如下: </p>
![image]() </p>

第二個程式:</p>
程式碼如下:</p>
```C++
int LED=6;
void setup() {
  for (int i=2 ;i<6;i++)
  pinMode (i, OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
  for (int i=5; i>1; i--)
    digitalWrite(i,HIGH);
  if (LED>=2)
    digitalWrite(LED,LOW);
  else
    LED=6;
  LED--;

 delay (500);
}
void loop() {
  // put your main code here, to run repeatedly:
  for (int i=5; i>1; i--)
    digitalWrite(i,HIGH);
  if (LED>=2)
    digitalWrite(LED,LOW);
  else
    LED=6;
  LED--;
 delay (500);
}
```


第三個程式: 功能LED由左至右逐一亮滅</p>
功能如下:</p>
初始狀態 ○○○○</p>
STEP1   ●○○○</p>
STEP2   ○●○○</p>
STEP3   ○○●○</p>
STEP4   ○○○●</p>
程式碼如下:</p>
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
電路配置圖如下:</p>
！[image] (https://github.com/Weng-yi/ARDOUINO/commit/d3faad3cdbbbc82409c1ad8766360640079e5b9a) </ p>
第四個程序功能LED由左至右逐一亮滅</ p>
功能如下:</p>
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
程式碼如下:</p>
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

電路配置圖如下:
![image](https://github.com/Weng-yi/ARDOUINO/blob/master/5AFD3FC0-DE91-446C-A8E5-BE80FF31FE46.jpeg) </p>

加分題目:</p>
初始狀態○○○○○○○○</p>
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
 
第六個程式:
```C++
int tig = 0;
int i = 0;
int s1 = 0;

void setup()
{
  pinMode(2, INPUT);
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(6, OUTPUT);
  pinMode(7, OUTPUT);
  pinMode(8, OUTPUT);
  pinMode(9, OUTPUT);
  pinMode(10, OUTPUT);
  for (i = 3; i <= 10; i += 1) {
      digitalWrite(i, HIGH);
    }
}
void loop()
{
  if (tig == 0) {

      for (i = 3; i <= 10; i += 1) {
        digitalWrite(i, LOW);
        delay(500);
        digitalWrite(i, HIGH);
        subd( ) ;
      }
    
  }
  if (tig == 1) {
 
      for (i = 10; i >= 3; i -= 1) {
        digitalWrite(i, LOW);
        delay(500);
        digitalWrite(i, HIGH);
        subd( ) ;
      }
    
  }
  if (tig == 2) {
   
    for (i = 3; i <= 10; i += 1) {
      digitalWrite(i, HIGH);
      subd( ) ;
    }
  }
  subd( ) ;
}

void subd( ){
    while (digitalRead(2) == 0) {
      while (digitalRead(2) == 0) {
        delay(40); 
      }
      tig += 1;
      if (tig >= 3) {
        tig = 0;
      }
    } 
 }
```
```C++
int tig=0;
void setup() {
  // put your setup code here, to run once:
  pinMode(2,INPUT);

}

void loop() {
  // put your main code here, to run repeatedly:
sub();
if(tig==0){
  red();
  }
  if(tig==1){
    green();
  }
if(tig==2){
  blue();
 }
}
void sub(){
  while(digitalRead(2)==0){
    while(digitalRead(2)==0){
      delay(20);
    }
    tig+=1;
    if(tig>=3){
      tig=0;
    }
  }
}
void red(){
  for(int i=0;i<=255;i+=1){
    analogWrite(0,i);
    analogWrite(1,0);
    analogWrite(2,0);
    sub();
    delay(100);
  }
}
void green(){
  analogWrite(0,0);
  analogWrite(1,255);
   analogWrite(2,0);
   sub();
}
void blue(){
  analogWrite(0,0);
  analogWrite(1,0);
  analogWrite(2,255);
  sub();
}
```
