

const int motorPin = 9; 
int motorSpeed = 0;    

void setup() {
  pinMode(motorPin, OUTPUT);
  Serial.begin(9600); // Initialize serial communication for monitoring
}


void loop() {
 
  for (motorSpeed = 0; motorSpeed <= 255; motorSpeed += 5) {
    analogWrite(motorPin, motorSpeed);
    Serial.print("Motor Speed: ");
    Serial.println(motorSpeed);
    delay(100); 
  }
  
  delay(1000);
  
 
  for (motorSpeed = 255; motorSpeed >= 0; motorSpeed -= 5) {
    analogWrite(motorPin, motorSpeed);
    Serial.print("Motor Speed: ");
    Serial.println(motorSpeed);
    delay(100);
  }
  
  delay(1000); 
}
