```


int led = D6;
int boardLed = D7;


void setup() 
{

  pinMode(led,OUTPUT); 
  pinMode(boardLed,OUTPUT); 
  
  Particle.subscribe("Deakin_RIOT_SIT210_Photon_Buddy", myHandler);

}


void loop() 
{
    

}


void myHandler(const char *event, const char *data)
{
  
  if (strcmp(data,"wave")==0)   // if wave data is received, blinks the red LED 3 times
  {
    
    digitalWrite(led, HIGH);
    delay(500);
    digitalWrite(led, LOW);
    delay(1000);
    digitalWrite(led, HIGH);
    delay(500);
    digitalWrite(led, LOW);
    delay(1000);
    digitalWrite(led, HIGH);
    delay(500);
    digitalWrite(led, LOW);
    delay(1000);
  }
  else if (strcmp(data,"pat")==0)   // If pat data is received, blinks the built-in led 3 times
  {

    digitalWrite(boardLed,HIGH);
    delay(500);
    digitalWrite(boardLed,LOW);
    delay(1000);
    digitalWrite(boardLed,HIGH);
    delay(500);
    digitalWrite(boardLed,LOW);
    delay(1000);
    digitalWrite(boardLed,HIGH);
    delay(500);
    digitalWrite(boardLed,LOW);
    delay(1000);
    
  }
  else 
  {

  }
}

```
