# Smart Medicine Reminder System

A microcontroller-based embedded healthcare device designed to remind users to take their medication on time using programmable alarms, audio alerts, and visual indicators.

---

## Project Overview
The Smart Medicine Reminder System helps patients—especially elderly individuals or those with memory difficulties—maintain proper medication schedules.  
It uses an **ATmega32P microcontroller**, **DS1307/DS3231 RTC**, **16x2 LCD**, LEDs, push buttons, and a buzzer to generate timely reminders.

---

## Features
- Real-time clock display  
- User-settable alarm (hour & minute)  
- Audible buzzer + LED alert  
- “Time to take your Meds :)” display during alarm  
- Alarm auto-stops after 1 minute or via stop button  
- Simple push-button user interface  
- No internet required (fully standalone)

---

## Objectives
- Improve medication adherence  
- Build a low-cost embedded reminder system  
- Support independent medicine scheduling  
- Provide both visual and audio alerts  

---

## Required Components
- ATmega32P Microcontroller  
- DS1307 / DS3231 RTC Module  
- 16x2 LCD Display  
- Push Buttons ×4  
- Buzzer  
- LEDs (Red, Yellow, Green)  
- 10kΩ Resistors  
- 16 MHz Crystal + 22pF Capacitors  
- Jumper Wires, Breadboard/PCB  
- 5V Power Supply  

---

## Circuit Diagram

<p align="center">
<img alt="Circuit Diagram" src="https://github.com/HKR-XV-20-R3/Remedix-Smart_medicine_Reminder/blob/main/Images/Simulation.png">
</p>

---

## Working Principle
1. RTC tracks real-time continuously.  
2. User sets alarm hour & minute.  
3. MCU compares RTC time with alarm time.  
4. When matched → buzzer + LED + LCD reminder.  
5. Alarm stops manually or after timeout.  

---

## System Workflow
1. Power on → LCD + RTC initialize  
2. Real-time clock displayed  
3. User enters alarm set mode via button  
4. Hour/minute adjusted with buttons  
5. Alarm saved  
6. System checks for match  
7. Alarm triggers  
8. Returns to real-time display
- **Flowchart:**
<p align="center">
<img alt="Flow Chart" src="https://github.com/HKR-XV-20-R3/Remedix-Smart_medicine_Reminder/blob/main/Images/Flow%20Chart.png">
</p>

---

## Conclusion
The Smart Medicine Reminder System successfully delivers a low-cost, reliable, and user-friendly solution to ensure timely medication intake.  
It demonstrates real-world use of microcontroller programming, RTC integration, and user-centric design, while forming a strong base for future upgrades like GSM alerts or smartphone connectivity.

---

## Project Files
- **Source Code:** [Click here!](https://github.com/HKR-XV-20-R3/Remedix-Smart_medicine_Reminder/blob/main/codes.cpp)
- **Project Report:** **[Download Full Report](https://github.com/HKR-XV-20-R3/Remedix-Smart_medicine_Reminder/blob/main/Project%20report/Smart%20Medicine%20Reminder_2110004_2110015.pdf)**  

---

**Md. Humayun Khalid**

Student
