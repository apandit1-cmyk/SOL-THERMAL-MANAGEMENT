# 04 Using Serial Monitor & Finishing Up

Now that our Arduino is reading the thermistor, it's time to create our telemetry dashboard! In mission control, engineers don't just look at scrolling numbers; they look at graphs to see how systems behave over time.

We are going to use the **Serial Plotter** to graph our temperature data against a target temperature, creating a visual dashboard just like the one you see here:

![Telemetry Dashboard](image_d2e886.png)

## Writing the Thermostat Code

We are going to combine our LED code and our Thermistor code into one final program. We will also add a simple `if/else` statement. This will act as our spacecraft's thermostat: if the temperature drops below our target, turn the heater (LED) on. If it's above the target, turn it off.

To make the Arduino IDE draw two separate lines on the graph (one for the "Target" and one for the "Thermistor"), we have to format our `Serial.print` statements in a very specific way with commas and labels.

Copy this code into your IDE and **fill in the blanks (`___`)**:

```cpp
// 04: The Complete Thermal Management System

int heaterLED = 4; 
int thermistorPin = A0; 

// Set our target threshold. 
// (Note: We are using raw sensor values here, which range from 0 to 1023)
int targetValue = 500; 

void setup() {
  pinMode(heaterLED, _______);
  Serial.begin(9600); 
}

void loop() {
  int thermistorValue = analogRead(thermistorPin);

  // --- TELEMETRY OUTPUT FOR THE SERIAL PLOTTER ---
  // This specific formatting tells the Plotter to draw two labeled lines.
  Serial.print("Target:");
  Serial.print(targetValue);
  Serial.print(",");
  Serial.print("Thermistor:");
  Serial.println(______________); // Print the actual sensor variable here

  // --- THERMOSTAT LOGIC ---
  // If the sensor reads colder than our target, turn the heater ON!
  if (thermistorValue < targetValue) {
    digitalWrite(heaterLED, ____); 
  } 
  // Otherwise (if it's hot enough), turn the heater OFF!
  else {
    digitalWrite(_________, LOW); 
  }
  
  // A short delay so the graph draws smoothly
  delay(100); 
}
