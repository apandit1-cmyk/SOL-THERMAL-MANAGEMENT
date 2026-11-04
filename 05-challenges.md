# 05 Challenges - For Nerds

Congratulations! You have successfully built a functional Thermal Management System prototype for the SunbYte mission. 

If you have finished early, here are a few advanced challenges to test your new hardware and coding skills. You will have to research and experiment to solve these!

## Challenge 1: The "Flicker" Problem (Hysteresis)
If you watch your LED closely when the temperature is *exactly* at your target value, you might notice it flickering on and off very rapidly. In a real spacecraft, turning a heater on and off 50 times a second would break the electronics!

**The Goal:** Modify your code so that the heater turns ON when the value drops below `490`, but doesn't turn OFF until the value rises above `510`. This creates a "buffer zone" (called hysteresis). 

## Challenge 2: Actual Degrees Celsius
Right now, your Serial Plotter is showing raw sensor values between `0` and `1023`. While useful, mission control usually prefers to read actual temperatures in Degrees Celsius.

**The Goal:** Convert your raw analog reading into a real temperature. 
*Hint:* You will need to use a bit of math. Search the internet for "Arduino Thermistor Steinhart-Hart equation" or look for a simple thermistor conversion formula. You will need to know the fixed resistor value (10,000 ohms).

## Challenge 3: Multi-Stage Heating
In extreme environments, sometimes one heater isn't enough.

**The Goal:** Add a second LED (and its resistor) to your breadboard and connect it to a new digital pin. Update your code so that:
1. If the temperature is just *slightly* below the target, turn on **one** LED.
2. If the temperature drops *drastically* below the target (e.g., an emergency freeze), turn on **both** LEDs!

## Challenge 4: Manual Override
Spacecraft always have physical overrides in case the automatic sensors fail.

**The Goal:** Ask an organizer for a push-button. Wire it up to your breadboard and a new digital pin. Change your code so that pressing and holding the button forces the LED to turn ON, regardless of what the thermistor is reading.

---
*Once you are done, please let someone form our team know and you can move onto the next activity!*
