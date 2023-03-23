# Simon Says Game
In this memory game, the LEDs light up in a random order each round, and the player must recreate that order by pushing the buttons that correspond to each LED.

## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Hardware Design](#hardware-design)
* [Software Design](#software-design)
* [Results](#results)
* [Sources](#sources)


## General Information
When the start button is pressed, the game begins. The LEDs will turn on and off in a random order. The correct LED (green LED) will light up if the corresponding buttons are pressed in the same order. If not, the wrong LED (the red LED) will turn on. The current level will be displayed on the 7-segment display.
<img width="448" alt="Block Diagram 2" src="https://user-images.githubusercontent.com/65070564/227248125-5a774d1b-057e-4e05-8f01-56941fee08b3.png">


## Technologies Used
- Arduino Ide 1.8.19

## Hardware Design
- Arduino Uno 
- breadboard 
- 6 LEDs
- 5 pushbuttons
- buzzer
- 7 segment display
- resistors
- wires


Electric scheme:

<img width="448" alt="Schemael 1" src="https://user-images.githubusercontent.com/65070564/227247850-60f3c739-8a14-4bff-897a-72385bf1f278.jpg">
<img width="448" alt="Schemael 1" src="https://user-images.githubusercontent.com/65070564/227247874-490c1b3a-dd50-4ad5-a613-3c31ffeb082b.jpg">

## Software Design
A random sequence is established as the game begins. The LEDs are flashed in the order prescribed by the sequence at each level, and the player input is compared to the sequence. The level increases if the order is accurate; otherwise, the level is repeated. The current level is displayed on the 7-segment display. The LEDs are accompanied by a buzzer that plays distinct noises for each of them, as well as a winning and a losing sound. Each level increases the challenge by increasing the pace of the flashing LEDs and the number of LEDs that light up.

## Results
<img width="448" alt="Circuit 1" src="https://user-images.githubusercontent.com/65070564/227247091-148da2c3-b49f-486d-9649-a59965017f3d.jpg">
<img width="448" alt="Circuit 2" src="https://user-images.githubusercontent.com/65070564/227247109-8eaf291a-c458-468c-a56b-a16fb6ce75f1.jpg">
<img width="448" alt="Circuit 3" src="https://user-images.githubusercontent.com/65070564/227247126-6c2c3ee4-4437-4733-acf6-38fb597f360a.jpg">

## Sources
- [Laboratory](https://ocw.cs.pub.ro/courses/pm/lab/lab1-2022)
- [7 Segment Display](https://create.arduino.cc/projecthub/aboda243/get-started-with-seven-segment-c73200)
- [Buzzer](https://create.arduino.cc/projecthub/SURYATEJA/use-a-buzzer-module-piezo-speaker-using-arduino-uno-89df45)
