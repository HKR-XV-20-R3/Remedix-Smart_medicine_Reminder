# Smart Medicine Reminder System

A microcontroller-based embedded healthcare device designed to remind users to take their medication on time using programmable alarms, audio alerts, and visual indicators.

---

## 📌 Project Overview
The Smart Medicine Reminder System helps patients—especially elderly individuals or those with memory difficulties—maintain proper medication schedules.  
It uses an **ATmega32P microcontroller**, **DS1307/DS3231 RTC**, **16x2 LCD**, LEDs, push buttons, and a buzzer to generate timely reminders.

---

## ✨ Features
- Real-time clock display  
- User-settable alarm (hour & minute)  
- Audible buzzer + LED alert  
- “Time to take your Meds :)” display during alarm  
- Alarm auto-stops after 1 minute or via stop button  
- Simple push-button user interface  
- No internet required (fully standalone)

---

## 🎯 Objectives
- Improve medication adherence  
- Build a low-cost embedded reminder system  
- Support independent medicine scheduling  
- Provide both visual and audio alerts  

---

## 🛠 Required Components
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

## ⚙️ Working Principle
1. RTC tracks real-time continuously.  
2. User sets alarm hour & minute.  
3. MCU compares RTC time with alarm time.  
4. When matched → buzzer + LED + LCD reminder.  
5. Alarm stops manually or after timeout.  

---

## 📌 System Workflow
1. Power on → LCD + RTC initialize  
2. Real-time clock displayed  
3. User enters alarm set mode via button  
4. Hour/minute adjusted with buttons  
5. Alarm saved  
6. System checks for match  
7. Alarm triggers  
8. Returns to real-time display  

---

## 🔌 Hardware Connections (Summary)
- LCD (RS, EN, D4–D7 connected to PD pins)  
- RTC via I2C (SDA → A4, SCL → A5)  
- Buzzer connected to PB1  
- Push buttons connected with pull-ups  
- LEDs connected to output pins  
- ATmega32P powered at +5V with 16 MHz crystal  

---

## 💰 Cost Estimation (BDT)
| Component | Qty | Total |
|----------|-----|--------|
| ATmega32P | 1 | 180 |
| RTC Module | 1 | 120 |
| 16x2 LCD | 1 | 150 |
| Push Buttons | 4 | 20 |
| LEDs | 3 | 6 |
| Buzzer | 1 | 20 |
| Breadboard | 1 | 120 |
| Jumper wires | 1 set | 50 |
| Others | — | ~30 |

**Estimated Total Cost:** ~696 BDT

---

## 🧪 Challenges Faced
- RTC I2C communication issues  
- Button bouncing → solved with software debouncing  
- Alarm repeatedly triggering → solved with flags  
- LCD initialization glitches  
- Power stability for ATmega32P  

---

## ✅ Advantages
- Improves medication adherence  
- Easy for elderly patients  
- Low cost and portable  
- Works without internet  
- Provides both audio + visual alerts  

---

## ⚠️ Limitations
- Limited to few alarms  
- No data logging  
- No mobile app / SMS alerts  
- Manual button operation required  
- No MCU battery backup  

---

## 🧾 Conclusion
The Smart Medicine Reminder System successfully delivers a low-cost, reliable, and user-friendly solution to ensure timely medication intake.  
It demonstrates real-world use of microcontroller programming, RTC integration, and user-centric design, while forming a strong base for future upgrades like GSM alerts or smartphone connectivity.

---

## 📎 Project Files
- **Source Code:** `main_code.ino` (or your filename)  
- **Circuit Diagram:** `/images/circuit.png` (add your path)  
- **Flowchart:** `/images/flowchart.png`  

---
