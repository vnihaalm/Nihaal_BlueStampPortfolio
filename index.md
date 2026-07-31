
# Third Eye for the Blind
The goal of this project is to help blind people know what road dangers are around them. It uses AI algorithms to detect potholes and speed bumps with a high accuracy. Some of the biggest challenges I faced when working on this project involved soldering issues and that the RAM on the Raspberry Pi is not enough to support the AI models that I was making.

You should comment out all portions of your portfolio that you have not completed yet, as well as any instructions:
```HTML 
<!--- This is an HTML comment in Markdown -->
<!--- Anything between these symbols will not render on the published site -->
```

| **Name** | **School** | **Area of Intrerest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Nihaal M | Thornton Middle School | Mechanical Engineering | 7

**<img width="4284" height="3000" alt="Nihaal M" src="https://github.com/user-attachments/assets/125e3f95-cc14-459f-a89d-2ea083d5b3c2" />

# Demo Night Presentation

<iframe width="964" height="542" src="https://www.youtube.com/embed/-F_jg9R8UUs" title="Nihaal M. Demo Night Presentation" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

# Final Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE



# Second Milestone

In the first milestone I used an ultrasonic sensor to detect walls and other obstructions along the way. This time for my second milestone, I decided to detect faces using a Raspberry Pi and a camera. When the camera detects a face, it draws a blue rectangle around the face and orange rectangles around the eyes. This module uses the K - means algorithm which finds similarities of the picture you give it and the pictures it was trained using. Some challenges included messy wiring and it was hard to get a camera up and working. Some next steps might include detecting potholes and speed bumps using the camera

<iframe width="962" height="541" src="https://www.youtube.com/embed/_X6za709OiI" title="Nihaal M. Milestone 2" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


# First Milestone

My project is called the Third Eye for the Blind. For this milestone, I made an ultrasonic sensor module that can detect walls and other surfaces and alert the person using a buzzer. I started by using a breadboard first, to ensure that all the connections are correct. Some next steps would be to solder all of these connections on to a PERF board to make it look much cleaner and simpler.

<iframe width="909" height="511" src="https://www.youtube.com/embed/degugbqGLYA" title="Nihaal M. Milestone 1" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


# Schematics 
<img width="952" height="536" alt="Screenshot 2026-07-16 at 1 49 37 PM" src="https://github.com/user-attachments/assets/ccf8aaf7-d4f2-4a4e-905c-b0c9325e5787" />

# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

c++
//VISIT : www.robotechmaker.com
  const int pingTrigPin = 7; //Trigger connected to PIN 7   
  const int pingEchoPin = 6; //Echo connected yo PIN 6   
  int buz= A4; //Buzzer to PIN 4   
  void setup() {   
    Serial.begin(9600);   
    pinMode(buz, OUTPUT);   
  }   
  void loop()   
  {  
  //digitalWrite(buz, HIGH); 
  long duration, cm;   
  pinMode(pingTrigPin, OUTPUT);   
  digitalWrite(pingTrigPin, LOW);   
  delayMicroseconds(2);   
  digitalWrite(pingTrigPin, HIGH);   
  delayMicroseconds(5);   
  digitalWrite(pingTrigPin, LOW);   
  pinMode(pingEchoPin, INPUT);   
  duration = pulseIn(pingEchoPin, HIGH);   
  cm = microsecondsToCentimeters(duration);   
  if(cm<=20 && cm>0)   
  {   
  int d= map(cm, 1, 100, 20, 2000);   
  digitalWrite(buz, HIGH);   
  delay(100);   
  digitalWrite(buz, LOW);   
  delay(d);  
  }   
  Serial.print(cm);    
  Serial.print("cm");   
  Serial.println();   
  delay(100);   
  }   
  long microsecondsToCentimeters(long microseconds)   
  {   
  return microseconds / 29 / 2;   
  }

# Bill of Materials
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Raspberry Pi | Control Hub | $123 | <a href="[https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/](https://www.amazon.com/Raspberry-Model-2019-Quad-Bluetooth/dp/B07TC2BK1X)"> Link </a> |
|  | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |

# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.
