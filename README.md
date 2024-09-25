const int ledPin = 9;
// LED state
int ledState = LOW;
// time since last LED was on
unsigned long previousMillis = 0;
// LED flashing interval
const long interval = 1000;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  unsigned long currentMillis = millis();

  if (currentMillis - previousMillis >= interval) {
    previousMillis = currentMillis;

    if (ledState == LOW) {
      ledState = HIGH;
    } else {
      ledState = LOW;
    }

    // set LED state:
    digitalWrite(ledPin, ledState);
  }
}

