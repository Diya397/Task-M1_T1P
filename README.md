#define PIR_SENSOR 2  // Motion sensor connected to digital pin 2
#define LED 13        // Built-in LED on pin 13

void setup() {
    pinMode(PIR_SENSOR, INPUT);
    pinMode(LED, OUTPUT);
    Serial.begin(9600);
}

void loop() {
    int motion = digitalRead(PIR_SENSOR);  // Read PIR sensor value


    if (motion == HIGH) {  // If motion is detected
        digitalWrite(LED, HIGH);  // Turn built-in LED ON
        Serial.println("Motion detected! LED ON");
    } else {
        digitalWrite(LED, LOW);  // Turn built-in LED OFF
        Serial.println("No motion detected. LED OFF");
    }

    delay(1000);  // Delay for stability
}
