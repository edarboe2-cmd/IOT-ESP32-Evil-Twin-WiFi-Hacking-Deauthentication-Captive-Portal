EBRIMA DARBOE : NOTES FOR CSN150
This section documents my setup, process, challenges, and final results for the ESP32‑CAM Evil Twin / Captive Portal assignment.
This project was completed for educational and cybersecurity awareness purposes only.

Equipment Used
ESP32‑CAM (AI Thinker module)

FTDI USB‑to‑Serial Programmer

Jumper wires (female‑to‑female)

Windows laptop

USB cable

Wi‑Fi‑enabled phone/laptop for testing

Tools Used
Arduino IDE

GitHub (forking, editing README, uploading screenshots)

Serial Monitor

Web browser (for captive portal testing)

GPT‑x (for documentation assistance)

Steps I Followed
Forked the GitHub Repository  
I forked the project:
https://github.com/aadesh0706/IOT-ESP32-Evil-Twin-WiFi-Hacking-Deauthentication-Captive-Portal

Downloaded the ZIP and Extracted the Project  
I downloaded the repository ZIP file and extracted it on my computer.

Opened the Project in Arduino IDE  
I loaded the .ino sketch into Arduino IDE and selected the correct board:
AI Thinker ESP32‑CAM

Wired the ESP32‑CAM to the FTDI Programmer

5V → 5V

GND → GND

U0R → TX

U0T → RX

IO0 → GND (for upload mode)

Uploaded the Sketch  
I uploaded the sketch to the ESP32‑CAM.
The Serial Monitor showed the device starting an Access Point.

Observed the “BAD” Output  
When using the NetworkDeAuth.ino sketch, the Serial Monitor repeatedly printed “BAD”.
This is expected because the ESP32‑CAM does not support monitor mode or packet injection.

Continued With the Evil Twin / Captive Portal Simulation  
Even though the deauth portion cannot run on ESP32‑CAM, the Access Point + Captive Portal portion works correctly.
I connected to the ESP32 Wi‑Fi network and accessed the webpage at 192.168.4.1.

Captured Screenshots  
I took screenshots of:

Arduino IDE

Serial Monitor output

ESP32 Wi‑Fi network

Captive portal webpage

My GitHub repo

Updated README and Uploaded Screenshots  
I added this documentation and uploaded my images to the /images/ folder.

Problems / Solutions
Problem 1: Serial Monitor printing “BAD” repeatedly
Cause:  
The ESP32‑CAM does not support Wi‑Fi monitor mode or packet injection, which the deauth sketch requires.
Because of this hardware limitation, the deauth code cannot run.

Solution:  
I continued with the Evil Twin / Captive Portal portion of the project, which works correctly on the ESP32‑CAM and fulfills the assignment requirements.

Problem 2: ESP32‑CAM not uploading at first
Cause:  
IO0 was not grounded during upload.

Solution:  
Grounded IO0 → Upload succeeded.

Problem 3: No Wi‑Fi network showing at first
Cause:  
ESP32‑CAM needed a reset after upload.

Solution:  
Pressed the reset button → AP appeared.

Final Report
This project demonstrated how an Evil Twin Wi‑Fi attack works in theory and how a captive portal can be used to mimic a legitimate network.
The ESP32‑CAM successfully created a fake Wi‑Fi access point and hosted a webpage at 192.168.4.1.
The deauthentication portion of the project could not run due to hardware limitations, but the Evil Twin simulation worked as expected.

This assignment helped me understand:

How Wi‑Fi access points are created

How captive portals work

Why insecure networks are dangerous

The importance of cybersecurity awareness

All testing was done in a controlled environment for educational purposes only.
