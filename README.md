# My Lab 🧪
**An Interactive Explorer for Hexadecimal, Binary, and Network Logic**

**My Lab** is a high-performance web application designed to visualize the relationship between human-readable data (Decimal/IPs) and machine-level representation (Hex/Binary). 

Developed by **Rwin**.

## 🚀 Live Demo
[Click here to open My Lab](https://rwin13.github.io/my-lab/)

---

## ✨ Features
* **Real-time Multibase Synchronization:** Instantly converts between Decimal (Base 10), Hexadecimal (Base 16), and Binary (Base 2).
* **Network Engineer's Toolkit:** A dedicated IPv4 parser that converts dotted-decimal IP addresses into 32-bit integers and calculates the **CIDR notation** (Subnet Mask length).
* **Color Laboratory:** * Dynamic Color Picker integration.
    * Natural Language search (e.g., typing "Crimson" translates to Hex via DOM-calculated values).
    * **Complementary Color Harmony:** Automatically calculates the mathematical opposite of any color.
* **Persistent Dark Mode:** A toggleable interface optimized for high-contrast visibility.
* **Activity History:** A live log of every conversion made during the session.

---

## 🧠 The Math & Logic Behind the Code
This project demonstrates advanced manipulation of bits and bytes. Below is the technical breakdown of the operations used:

### 1. Bitwise Channel Extraction (RGB)
In a 24-bit color system, the first 8 bits represent **Red**, the next 8 represent **Green**, and the last 8 represent **Blue**. To extract these, we use **Bitwise Right Shifts** ($>>$) and the **AND Mask** ($255$ or $0xFF$).



* **Red:** `(val >> 16) & 255`  
    * *Logic:* Shifts the bits 16 places to the right to move the Red byte to the front, then masks out everything else.
* **Green:** `(val >> 8) & 255`  
    * *Logic:* Shifts 8 places to isolate the middle byte.
* **Blue:** `val & 255`  
    * *Logic:* Simply masks the last 8 bits.

### 2. IPv4 to 32-bit Integer Conversion
A standard IP (like `192.168.1.1`) is actually a single 32-bit number. To reconstruct it, we use **Bitwise Left Shifts** ($<<$):
* **Formula:** `(Octet1 << 24) + (Octet2 << 16) + (Octet3 << 8) + Octet4`
* This places each 8-bit number into its correct "slot" within the 32-bit block.



### 3. CIDR Calculation
The CIDR notation (e.g., `/24`) is determined by analyzing the binary string. The code identifies the length of the leading "1"s before the first "0" occurs. This is the fundamental way routers determine network boundaries.

### 4. Color Inversion (Complementary Colors)
The app calculates the **Complementary Color** using the **Bitwise NOT** logic or simple subtraction:
* `Complementary_Red = 255 - Current_Red`
* This creates a 180-degree shift on the color wheel, providing perfect visual opposites.

---

## 🛠️ Technical Stack
* **HTML5/CSS3:** Utilizes CSS Variables (`:root`) for the Dark Mode theme engine.
* **JavaScript (ES6+):** Uses the **Unsigned Right Shift operator** (`>>> 0`) to ensure 32-bit values stay positive in the JavaScript engine.

## 👤 Author
* **Rwin** - Lead Developer & Architect

---
*Created for educational purposes to bridge the gap between human-readable numbers and machine code.*
