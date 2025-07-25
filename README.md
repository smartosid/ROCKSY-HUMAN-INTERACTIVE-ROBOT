# ROCKSY-HUMAN-INTERACTIVE-ROBOT

ROCKSY, a smart surveillance robot powered by a Raspberry
Pi. ROCKSY integrates multiple technologies—computer vision, speech-based AI, web
scraping, and IoT device management—into a single, compact platform. Unlike traditional
systems dependent on cloud infrastructure, ROCKSY leverages edge computing to ensure
mobility, privacy, and real-time responsiveness.
ROCKSY bridges critical gaps in conventional home security solutions through features such as
autonomous navigation, human posture recognition, and an intuitive voice interface. It functions
not only as a security monitor but also as a real-time assistant capable of controlling smart
devices, retrieving useful information, and responding promptly to emergencies. As the concept
of smart living continues to progress, context-aware and interactive robots are becoming
essential components of future homes. ROCKSY exemplifies how powerful, edge-based AI
solutions can be made accessible and practical, shaping the future of home automation and
digital companionship.


##🧠 SOFTWARE DESCRIPTION

###🔧 Arduino IDE
The Arduino IDE is used to program the hardware components of the robot. The Arduino Mega board handles body and chassis control, reading data from sensors like gas, temperature, fire, and motion sensors. The ESP8266 Wi-Fi module is also programmed using Arduino IDE to send data to Firebase and receive control commands from mobile apps like Blynk. Overall, Arduino IDE is the foundation for embedded system development and real-time sensor control.

Features:

Sensor Integration: Reads data from gas, fire, temperature, and PIR sensors using analog/digital pins.

Actuator Control: Controls motors for chassis movement via L298N motor driver.

IoT Communication: ESP8266 connects to Wi-Fi and communicates with Firebase and Blynk.

Serial Monitoring: Monitors real-time outputs from sensors for debugging.

Multi-Board Programming: Used to program both Arduino Mega and ESP8266.

##💻 Visual Studio Code

Visual Studio Code is the main development environment for the MERN stack (MongoDB, Express.js, React, Node.js) used to build the robot’s control dashboard and handle backend services. It’s also used to develop Python scripts on Raspberry Pi for AI and camera functionalities.

Features:

React Frontend: Displays alerts, camera feeds, and IoT controls on a web dashboard.

Node.js Backend: Interfaces with Firebase and Raspberry Pi APIs.

MongoDB Database: Stores logs such as gas leak alerts and motion detection.

Live Data Fetching: Pulls real-time data from Firebase to update the UI.

REST APIs: Supports emergency call triggers and on-demand sensor data fetch.

###☁️ Firebase
Firebase is used as the cloud backend for storing sensor data and sending real-time alerts. It enables the mobile/web dashboard to monitor the robot remotely and supports push notifications during emergencies like gas leaks or fire detection.

Features:

Live Sensor Data Logging: Continuously updates sensor values from Arduino/ESP8266 to Firebase Realtime Database.

Alert Management: Sends alerts via Firebase Cloud Messaging (FCM) when thresholds are exceeded.

Authentication (Optional): Can be used to secure access via login.

Auto Sync: Instantly syncs data between devices and dashboard.

###📱 Blynk
Blynk enables wireless monitoring and control of the robot via a mobile app. It is linked to the ESP8266 and allows real-time updates and commands from anywhere with an internet connection.

Features:

Sensor Monitoring: Live readings (gas, fire, temperature) are displayed on the mobile app.

Device Control: Remote control of fans, lights, and alarms.

Push Notifications: Sends alerts from ESP8266 or Firebase to the phone.

Mode Switching: Change robot modes (e.g., Surveillance or Assistant) from the app.

###🐍 PyCharm
PyCharm is used to write and test all Python-based functionalities, especially those on Raspberry Pi. This includes AI modules, voice interaction, image tracking, and real-time data handling.

Features:

Voice Interaction: Uses SpeechRecognition and pyttsx3 for voice-based commands and responses.

Image Tracking (OpenCV): Tracks objects/people using Haar cascades with bounding boxes.

Sensor Monitoring Logic: Reads from Firebase or serial ports and acts on triggers.

Camera Feed Processing: Streams and analyzes Pi camera feed in real time.

###🔬 Google Colab
Google Colab is used for developing and training machine learning and computer vision models before deploying them to Raspberry Pi.

Features:

Model Training: Trains object/person detection models on COCO/custom datasets.

Testing: Validates model accuracy and logic before deployment.

Visualization: Plots graphs and outputs for model evaluation.

Collaboration: Easy sharing and prototyping of notebooks.

###🛠️ Fusion 360
Fusion 360 is used to design the complete mechanical structure of the robot, including head, body, chassis, and mounting areas for controllers, sensors, and batteries. It helps visualize and plan the physical layout before fabrication.

Features:

Chassis Design: Mounts Arduino, motor driver, and battery.

Head Assembly: Holds Pi camera, ultrasonic sensors, and LEDs.

Body Frame: Vertical frame for positioning sensors at optimal heights.

Controller Mount: Holds Raspberry Pi, Arduino Mega, and power supply.

#🔩 HARDWARE IMPLEMENTATION
###🖥️ OLED 0.96" Display (I2C)
A compact 128x64 pixel screen used for displaying sensor values, alerts, and statuses. Communicates via I2C, requiring only two pins (SCL and SDA), making it ideal for microcontroller use.

###📡 Ultrasonic Sensor (HC-SR04)
Measures distance using ultrasonic waves. Ideal for obstacle detection and navigation, with a range of 2 cm to 400 cm.

###🛢️ MQ2 Gas Sensor
Detects gases like LPG, methane, propane, and smoke. Offers both analog and digital outputs, making it useful for gas leak alerts.

###🔥 Flame Sensor
Detects flames or fires using infrared light. Can trigger alerts using digital or analog outputs when fire is detected.

###🖼️ TFT Display (1.8" SPI)
Color display that connects via SPI. Used to show richer visuals such as camera previews, UI elements, and voice feedback.

###🌈 RGB LED Strip
Displays colors to indicate robot modes (e.g., standby, alert). Controlled via digital pins using FastLED or NeoPixel libraries.

###⚙️ Motor Driver (L329D)
Controls DC motors (forward, reverse, speed) and acts as an interface between microcontroller and motors.

###🔋 Li-Po Battery (3.7V x 3 Cells)
Three-cell battery pack provides power to motors and electronics. Lightweight and rechargeable with protection circuits for safety.

###🚗 Gear Motor
DC gear motors provide controlled torque for smooth movement. Drive the robot’s chassis via motor drivers.

###🎛️ Arduino Mega
ATmega2560-based board with 54 digital I/O pins and 16 analog inputs. Handles all core control, sensor integration, and motor functions.

###🎤 MAX4466 Microphone
Electret mic with adjustable gain used for voice commands and ambient sound detection.

###📶 HC-05 Bluetooth Module
Used for Bluetooth-based communication, supporting both master/slave modes. Configured using AT commands.
