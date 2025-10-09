#define TRIG1 2
#define ECHO1 3
#define TRIG2 4
#define ECHO2 5

long lastValidDistance1 = -1; // Stores last valid reading for sensor 1
long lastValidDistance2 = -1; // Stores last valid reading for sensor 2

void setup() {
  Serial.begin(9600);   // Debugging via USB
  Serial1.begin(9600);  // UART for ESP32

  pinMode(TRIG1, OUTPUT);
  pinMode(ECHO1, INPUT);
  pinMode(TRIG2, OUTPUT);
  pinMode(ECHO2, INPUT);
}

// Function to read distance from ultrasonic
long readUltrasonic(int trigPin, int echoPin) {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  long duration = pulseIn(echoPin, HIGH, 30000); // 30ms timeout
  long distance = duration * 0.034 / 2;
  if (distance == 0 || distance > 400) return -1; // invalid
  return distance;
}

// Basic validation: check if distance is within realistic range
bool isValidDistance(long distance) {
  return (distance > 0 && distance <= 400);
}

// Advanced validation: ignore spikes, keep last valid
long getValidatedDistance(long newReading, long &lastValid) {
  if (isValidDistance(newReading)) {
    lastValid = newReading; // Update last valid
    return newReading;
  } else {
    return lastValid;       // Keep previous valid reading
  }
}

void loop() {
  long rawDistance1 = readUltrasonic(TRIG1, ECHO1);
  long rawDistance2 = readUltrasonic(TRIG2, ECHO2);

  // Apply validation
  long distance1 = getValidatedDistance(rawDistance1, lastValidDistance1);
  long distance2 = getValidatedDistance(rawDistance2, lastValidDistance2);

  // Send validated data to ESP32
  Serial1.print("D1:");
  Serial1.print(distance1);
  Serial1.print("cm, D2:");
  Serial1.print(distance2);
  Serial1.println("cm");

  // Debugging output
  Serial.print("Sensor1: ");
  Serial.print(distance1);
  Serial.print(" cm | Sensor2: ");
  Serial.print(distance2);
  Serial.println(" cm");

  delay(500); // half-second update
