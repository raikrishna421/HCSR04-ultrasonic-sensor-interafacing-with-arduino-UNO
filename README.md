# HCSR04-ultrasonic-sensor-interafacing-with-arduino-UNO
//Measurement of distance using ultrasonic sensor
int trig=3;
int echo=2;
long duration,distance;
void setup()
{
  pinMode(trig,OUTPUT);
  pinMode(echo,INPUT);
  Serial.begin(9600);
  pinMode(4,OUTPUT);
}
void loop()
{
  digitalWrite(trig,HIGH);
  delayMicroseconds(10);
  digitalWrite(trig,LOW);
  delayMicroseconds(10);
  duration=pulseIn(echo,HIGH);
  distance=(0.0343*(duration/2));
  Serial.println(distance);
  if(distance<20)
  {
    digitalWrite(4,HIGH);
  }
  else
  {
    digitalWrite(4,LOW);
  }
}
  
