# Control-4-DC-Motors-Using-L293D-and-Arduino

## *Project Description*
This project demonstrates how to control 4 DC motors using the L293D motor driver and Arduino. The motors can move forward, backward, and rotate right or left according to programmed commands.

---

## *Requirements*

### *Hardware:*
1. Arduino UNO  
2. L293D motor driver IC  
3. 4 DC motors  
4. External battery (9V or 12V)  
5. Connecting wires  
6. Breadboard  

### *Software:*
1. Arduino IDE  
2. GitHub for creating and sharing the repository  

---

## *Circuit Setup*

### *1. External Battery (9V):*
- *Positive terminal (+):* Connect to *VSS (Pin 8)* on the L293D.  
- *Negative terminal (-):* Connect to *GND (Pin 4, 5)* of the L293D and Arduino.

### *2. Arduino to L293D:*
- Connect the Arduino PWM pins (D3, D5, D6, D9) to the enable pins of the L293D (ENA, ENB, ENC, END).  
- Connect control pins (IN1 to IN8) to corresponding digital pins on the Arduino.

### *3. L293D to Motors:*
- Connect the output pins (OUT1 to OUT8) of the L293D to the motors.

### *4. Power Supply:*
- *VCC (Pin 16):* Connect to the 5V pin of the Arduino to power the L293D.  
- Ensure all grounds (GND) are connected to a common ground for proper operation.

---

## *Steps to Run the Project*

1. *Clone the Repository:*  
   Use the following command to clone the project:  
   bash
   git clone https://github.com/yourusername/your-repository.git
   

2. *Upload the Code to Arduino:*  
   - Open the Arduino IDE.  
   - Copy and paste the code provided below.  
   - Connect the Arduino to your computer using a USB cable.  
   - Select the correct port and click *Upload*.  

3. *Assemble the Circuit:*  
   - Connect the hardware as described in the "Circuit Setup" section.  

4. *Power On:*  
   - Use the 9V battery to power the motors.  
   - Ensure all connections are secure.

---

## *Code*
cpp
#define ENA 3
#define ENB 5
#define ENC 6
#define END 9

#define IN1 8
#define IN2 7
#define IN3 10
#define IN4 11
#define IN5 12
#define IN6 13
#define IN7 4
#define IN8 2

void setup() {
  pinMode(ENA, OUTPUT);
  pinMode(ENB, OUTPUT);
  pinMode(ENC, OUTPUT);
  pinMode(END, OUTPUT);

  pinMode(IN1, OUTPUT);
  pinMode(IN2, OUTPUT);
  pinMode(IN3, OUTPUT);
  pinMode(IN4, OUTPUT);
  pinMode(IN5, OUTPUT);
  pinMode(IN6, OUTPUT);
  pinMode(IN7, OUTPUT);
  pinMode(IN8, OUTPUT);
}

void loop() {
  moveForward();
  delay(30000);

  moveBackward();
  delay(60000);

  turnRight();
  delay(3000);

  turnLeft();
  delay(3000);
}

void moveForward() {
  digitalWrite(IN1, HIGH);
  digitalWrite(IN2, LOW);
  analogWrite(ENA, 255);

  digitalWrite(IN3, HIGH);
  digitalWrite(IN4, LOW);
  analogWrite(ENB, 255);

  digitalWrite(IN5, HIGH);
  digitalWrite(IN6, LOW);
  analogWrite(ENC, 255);

  digitalWrite(IN7, HIGH);
  digitalWrite(IN8, LOW);
  analogWrite(END, 255);
}

void moveBackward() {
  digitalWrite(IN1, LOW);
  digitalWrite(IN2, HIGH);
  analogWrite(ENA, 255);

  digitalWrite(IN3, LOW);
  digitalWrite(IN4, HIGH);
  analogWrite(ENB, 255);

  digitalWrite(IN5, LOW);
  digitalWrite(IN6, HIGH);
  analogWrite(ENC, 255);

  digitalWrite(IN7, LOW);
  digitalWrite(IN8, HIGH);
  analogWrite(END, 255);
}

void turnRight() {
  digitalWrite(IN1, HIGH);
  digitalWrite(IN2, LOW);
  analogWrite(ENA, 255);

  digitalWrite(IN3, HIGH);
  digitalWrite(IN4, LOW);
  analogWrite(ENB, 255);

  digitalWrite(IN5, LOW);
  digitalWrite(IN6, LOW);
  analogWrite(ENC, 0);

  digitalWrite(IN7, LOW);
  digitalWrite(IN8, LOW);
  analogWrite(END, 0);
}

void turnLeft() {
  digitalWrite(IN1, LOW);
  digitalWrite(IN2, LOW);
  analogWrite(ENA, 0);

  digitalWrite(IN3, LOW);
  digitalWrite(IN4, LOW);
  analogWrite(ENB, 0);

  digitalWrite(IN5, HIGH);
  digitalWrite(IN6, LOW);
  analogWrite(ENC, 255);

  digitalWrite(IN7, HIGH);
  digitalWrite(IN8, LOW);
  analogWrite(END, 255);
}


---

## *Output*
1. The motors will move *forward* for 30 seconds.  
2. The motors will move *backward* for 60 seconds.  
3. The system will rotate *right* for 3 seconds.  
4. The system will rotate *left* for 3 seconds.  

---

## * Link to tinkercad*
https://www.tinkercad.com/things/1TI1mmpRrLH-cool-crift-bojo?sharecode=oNcr5fh04OcAckUrzDE9iKwzdpTiKnW9T1KCg1p6P7Y
