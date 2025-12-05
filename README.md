# Arduino Medicine Reminder System

## Project Overview
This project is a Medicine Reminder System using Arduino, DS3231 RTC, LCD, buttons, buzzer, and LED. The user can set alarm hours and minutes, view current time, and receive a reminder when it's time to take medicine.

---

## Features
- Set alarm hour and minute using buttons  
- Display real-time clock from DS3231  
- Display alarm time  
- Alarm notification with buzzer + LED  
- Stop alarm using button  
- Alarm resets after one minute  

---

## Pin Configuration

| Component | Pin |
|----------|-----|
| LCD RS | 7 |
| LCD EN | 6 |
| LCD D4 | 5 |
| LCD D5 | 4 |
| LCD D6 | 3 |
| LCD D7 | 2 |
| Hour Button | 10 |
| Minute Button | 11 |
| Alarm Set Button | 8 |
| Stop Button | 13 |
| Buzzer | 9 |
| LED | 12 |

---

## Source Code

```cpp
#include <LiquidCrystal.h>
#include <Wire.h>
#include <RTClib.h>

LiquidCrystal lcd(7, 6, 5, 4, 3, 2);
RTC_DS3231 rtc;

int ahours = 0;
int amins = 0;
bool alarmTriggered = false;

void setup() {
 lcd.begin(16, 2);
 lcd.clear();
 Serial.begin(9600);

 Wire.begin();
 if (!rtc.begin()) {
   lcd.print("Couldn't find RTC");
   while (1);
 }

 pinMode(13, INPUT_PULLUP);
 pinMode(11, INPUT); digitalWrite(11, HIGH);
 pinMode(10, INPUT); digitalWrite(10, HIGH);
 pinMode(8, INPUT);  digitalWrite(8, HIGH);

 pinMode(A0, OUTPUT); digitalWrite(A0, HIGH);

 pinMode(9, OUTPUT);
 pinMode(12, OUTPUT);
}

void loop() {
 DateTime now = rtc.now();

 while (digitalRead(8) == LOW) {
   lcd.clear();
   lcd.setCursor(0, 0);
   lcd.print("Alarm : ");

   if (digitalRead(11) == LOW) {
     amins++; delay(200);
   }
   else if (digitalRead(10) == LOW) {
     ahours++; delay(200);
   }

   if (amins > 59) { amins = 0; ahours++; }
   if (ahours > 23) ahours = 0;

   lcd.setCursor(6, 0);
   if (ahours < 10) lcd.print("0");
   lcd.print(ahours);
   lcd.print(":");
   if (amins < 10) lcd.print("0");
   lcd.print(amins);

   delay(500);
 }

 lcd.setCursor(0, 0);
 lcd.print("Time: ");
 if (now.hour() < 10) lcd.print("0");
 lcd.print(now.hour());
 lcd.print(":");
 if (now.minute() < 10) lcd.print("0");
 lcd.print(now.minute());
 lcd.print(":");
 if (now.second() < 10) lcd.print("0");
 lcd.print(now.second());

 lcd.setCursor(0, 1);
 lcd.print("Alarm: ");
 if (ahours < 10) lcd.print("0");
 lcd.print(ahours);
 lcd.print(":");
 if (amins < 10) lcd.print("0");
 lcd.print(amins);

 if (now.hour() == ahours && now.minute() == amins && !alarmTriggered) {
   alarmTriggered = true;

   while (true) {
     lcd.clear();
     lcd.setCursor(0, 0);
     lcd.print("Time to take your");
     lcd.setCursor(0, 1);
     lcd.print("Meds :)");

     digitalWrite(12, HIGH);
     tone(9, 1000);
     delay(500);
     noTone(9);
     digitalWrite(12, LOW);
     delay(500);

     if (digitalRead(13) == LOW) {
       noTone(9);
       digitalWrite(12, LOW);
       lcd.clear();
       delay(500);
       break;
     }
   }
 }

 if (now.minute() != amins) alarmTriggered = false;

 Serial.print("Alarm Time: ");
 Serial.print(ahours); Serial.print(":");
 Serial.println(amins);

 Serial.print("Current Time: ");
 Serial.print(now.hour()); Serial.print(":");
 Serial.println(now.minute());

 delay(500);
}
