Thermometer
===========
//For Arduino Start kit 
//Compatible with all Arduino version 
//Last updated 2011-1-13 
//www.dfrobot.com  
int a=7; 
int b=6; 
int c=5; 
int d=11; 
int e=10; 
int f=8; 
int g=9; 
int dp=4; 
void setup() 
{ 
  int i;//Set Pin Mode as output 
  for(i=4;i<=11;i++) 
  pinMode(i,OUTPUT); 
} 
 
void loop() 
{ 

  int z; 
  while(1) 
  { 
    z=analogRead(0);//Read temperature on Analog 0 
    if(z>30&&z<35)//if the temperature is between 20-23 
    {       
        unsigned char j; 
        digitalWrite(c,LOW);//Set C Segment to low which lights this segment 
        digitalWrite(b,LOW);//Set B Segment to low which lights this segment 
        for(j=7;j<=11;j++)//Set the rest Segments to high which turn off this segment.    ###################    1
        digitalWrite(j,HIGH); 
        digitalWrite(dp,HIGH);//Turn off DP segment (the little dot on the right down part) 
    } 
    else if(z>=35&&z<40)//if the temperature is between 23~25 
    { 
        unsigned char j; 
        digitalWrite(b,LOW); 
        digitalWrite(a,LOW); 
        for(j=9;j<=11;j++) 
        digitalWrite(j,LOW);                                                              
        digitalWrite(dp,HIGH); 
        digitalWrite(c,HIGH); 
        digitalWrite(f,HIGH); 
    } 
    else if(z>=40&&z<45)//if the temperature is between 25~28 
    { 
        unsigned char j; 
        digitalWrite(g,LOW); 
        digitalWrite(d,LOW); 
        for(j=5;j<=7;j++) 
        digitalWrite(j,LOW); 
        digitalWrite(dp,HIGH); 
        digitalWrite(f,HIGH); 
        digitalWrite(e,HIGH); 
    } 
    else if(z>=45&&z<50)//if the temperature is between 28~30 
    { 
        digitalWrite(c,LOW); 
        digitalWrite(b,LOW); 
        digitalWrite(f,LOW); 
        digitalWrite(g,LOW); 
        digitalWrite(dp,HIGH); 
        digitalWrite(a,HIGH); 
        digitalWrite(e,HIGH); 
        digitalWrite(d,HIGH);    
    } 
    else if(z>=50&&z<55)//if the temperature is between 30~33 
    { 
        unsigned char j; 
        for(j=7;j<=9;j++) 
        digitalWrite(j,LOW); 
        digitalWrite(c,LOW); 
        digitalWrite(d,LOW); 
        digitalWrite(dp,HIGH); 
        digitalWrite(b,HIGH); 
        digitalWrite(e,HIGH);   
    } 
    else if(z>=55&&z<60)//if the temperature is between 33~35 
    { 
        unsigned char j; 
        for(j=7;j<=11;j++) 
        digitalWrite(j,LOW); 
        digitalWrite(c,LOW); 
        digitalWrite(dp,HIGH); 
        digitalWrite(b,HIGH);    
    } 
    else if(z>=60&&z<65)//if the temperature is between 35-48 
    { 
        unsigned char j; 
        for(j=5;j<=7;j++) 
        digitalWrite(j,LOW); 
        digitalWrite(dp,HIGH); 
        for(j=8;j<=11;j++) 
        digitalWrite(j,HIGH); 
    } 
    else if(z>=65&&z<70)//if the temperature is between 38-40 
    { 
        unsigned char j; 
        for(j=5;j<=11;j++)     
        digitalWrite(j,LOW); 
        digitalWrite(dp,HIGH); 
    } 

  } 
}