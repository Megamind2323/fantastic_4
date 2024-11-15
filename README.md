// Motor speed control using PWM on Arduino

const int motorPin = 9; // Pin where the motor driver is connected
int motorSpeed = 0;     // Variable to store the motor speed (0 - 255)

// Setup function to initialize motor pin as output
void setup() {
  pinMode(motorPin, OUTPUT);
  Serial.begin(9600); // Initialize serial communication for monitoring
}

// Loop function to control the motor speed
void loop() {
  // Gradually increase the motor speed
  for (motorSpeed = 0; motorSpeed <= 255; motorSpeed += 5) {
    analogWrite(motorPin, motorSpeed); // Set motor speed
    Serial.print("Motor Speed: ");
    Serial.println(motorSpeed);
    delay(100); // Small delay to observe speed change
  }
  
  delay(1000); // Hold at full speed for a second
  
  // Gradually decrease the motor speed
  for (motorSpeed = 255; motorSpeed >= 0; motorSpeed -= 5) {
    analogWrite(motorPin, motorSpeed); // Set motor speed
    Serial.print("Motor Speed: ");
    Serial.println(motorSpeed);
    delay(100);
  }
  
  delay(1000); // Hold at stop for a second
}
