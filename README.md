---

# Smart Home Automation with ESP32 🏠✨

This project demonstrates a Smart Home Automation system using the ESP32 microcontroller. It allows for manual control of various household devices like lights, fans, and more through both physical switches and a web interface. The system is designed to automate and remotely control a house's appliances while monitoring environmental conditions using sensors. ⚡💻

---

## Project Features 🌟

- **Control via Web Interface**: Users can control appliances such as lights, fans, and TVs through a simple and intuitive web-based dashboard. 📱💡
- **Manual Switch Control**: Physical switches are still available for manual control of connected devices. 🖱️🔌
- **DHT11 Temperature and Humidity Monitoring**: The system monitors and displays real-time temperature and humidity levels in the kitchen. 🌡️🍲
- **PIR Motion Detection**: Automatically detects motion in the bathroom and turns on the lights accordingly. 🚶💡
- **Fire Detection (Future)**: A fire detection system is planned for future updates to improve safety. 🔥🚨

---

## How It Works ⚙️

The system is built using the following components:

- **ESP32 Microcontroller**: Handles the logic and web server. 🔋🧠
- **DHT11 Sensor**: Measures temperature and humidity. 🌡️💧
- **PIR Motion Sensor**: Detects motion in the bathroom. 🚶🚪
- **Relays**: Controls the electrical appliances (lights, fans, TV, etc.). 💡🔌
- **Web Dashboard**: Allows users to control devices remotely through a Wi-Fi connection. 🌐📱

---

## Project Structure 📂

- `index.html`: The front-end web dashboard for controlling devices and monitoring sensor data. 💻
- `BasicCodeWorking`: Initial working code for testing ESP32 with basic functionalities. 🛠️
- `FinalWorking`: The final code with fully functional features including sensor integration and device control. ✅
- `AddRoom.txt`: Instructions for adding rooms and customizing device control. 📝🏠
- `QR_Repo.png`: QR code linking to the GitHub repository. 📷📁

---

## Installation 🛠️

1. Clone the repository:
    ```bash
    git clone https://github.com/Vipulraj0152/SmartHome.git
    ```
2. Open the Arduino IDE and upload the code to your ESP32. 🖥️

3. Connect the ESP32 to your Wi-Fi network by editing the following lines in the code:
    ```cpp
    const char* ssid = "YourSSID";
    const char* password = "YourPassword";
    ```

4. Open the IP address assigned to the ESP32 in your web browser to access the Smart Home dashboard. 🌐🏡

---

## Contributors 👥

- **Vipul Raj (1NH22CD139)** 📘
- **Harsh Kumar (1NH22CD034)** 📗

We are both students at New Horizon College of Engineering, working together to build a robust and intelligent Smart Home Automation system for easy, intuitive control of household devices. 🎓🏫

---

## Future Enhancements 🔮

- Integration with voice assistants (Alexa, Google Assistant). 🎙️🤖
- Fire detection using temperature and gas sensors. 🔥🌡️
- Power consumption tracking for individual devices. ⚡📊

---

## License 📜

This project is open-source and available under the MIT License. 🌍✔️

---
