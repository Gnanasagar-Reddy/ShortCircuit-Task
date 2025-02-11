# ShortCircuit-Task
TINKERCAD LINK - https://www.tinkercad.com/things/9ngiPqEItmP-shortcircuittask/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard&sharecode=ZxXSt5S-Gx5bj6PQF2Hb4Gw560-5CPMM5_-ngR4ES5w 

code for tinkercad -

    // C++ code
    //
    int led1 = 9;
    int led2 = 10;
    int led3 = 11;
    int push = 2;
    unsigned long interval = 5000;
    unsigned long interval1 = 7000;
    unsigned long interval2 = 12000;
    unsigned long start = 0;
    int k = 0;



    void setup()
    {
     pinMode(led1, OUTPUT);
     pinMode(led2, OUTPUT);
     pinMode(led3, OUTPUT);
     pinMode(push, INPUT);
  
    }

    void loop()
    {
    if(digitalRead(push)==HIGH){
     
    digitalWrite(led1,LOW);
     digitalWrite(led2,LOW);
      digitalWrite(led3,HIGH); 
     delay(3000); // 3 SEC for pedesttian crossing
    k=0;
    }
     // cycle is like green(5 sec) --> yellow(2 sec) ---> red(5 sec)
    else if(k==0){  
      start = millis();
    if(millis() - start<=interval){
    digitalWrite(led1,HIGH);
     digitalWrite(led2,LOW);
     digitalWrite(led3,LOW);
      k=1;}
     }
        
    else if(k==1){  
    if (millis() - start >=interval && millis()- start <= interval1)
    { digitalWrite(led1,LOW);
    digitalWrite(led2,HIGH);
    digitalWrite(led3,LOW);
    k=2;}
       }
    else  if(k==2){
    if(millis() - start >= interval1 && millis() - start <=interval2){
    digitalWrite(led1,LOW);
      digitalWrite(led2,LOW);
    digitalWrite(led3,HIGH);
     k=3;
    }}
    else if (k==3){
    if( millis() - start >= interval2){
      k=0;}}
  
    }
  
