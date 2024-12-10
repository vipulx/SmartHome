To add rooms and sensors to your existing Arduino sketch for your smart home setup,
you'll need to extend both the hardware setup (adding more sensors and devices) and the software
(updating the HTML interface and handling logic for new rooms and sensors).

Here's a structured approach to do this:

Hardware Setup

Define Pins for New Sensors/Devices:
    Decide which GPIO pins on your Arduino board will be used for connecting new sensors and devices. For example, if you're adding a new DHT sensor for another room, determine a new pin assignment.
cpp --------------------------------------------------------------
const int DHTPin2 = 26;  // Example pin for a new DHT sensor
------------------------------------------------------------------



Also, define pins for any additional devices (lights, fans, switches, etc.) you want to control.
cpp -----------------------------------------------------------------
const int newRoomLightPin = 27;
---------------------------------------------------------------------



    Initialize pins for output (devices you can control) and input (sensors detecting events like motion).
cpp ----------------------------------------------------------------
pinMode(newRoomLightPin, OUTPUT);
--------------------------------------------------------------------

Software (Arduino Sketch)


Update HTML Interface (handleRoot function):

Modify the HTML structure to include UI elements for the new rooms and their respective controls.
html ----------------------------------------------
<button onclick="showRoom('newRoom')">New Room</button>
-----------------------------------------------------------

Initialize New Sensors:
    Create instances of new sensors and devices using appropriate libraries (e.g., DHT for temperature/humidity sensors).
cpp -----------------------------------------------------------------
DHT dht2(DHTPin2, DHTTYPE);  // Initialize a new DHT sensor instance
---------------------------------------------------------------------


Add new <div> sections for each room in the handleRoot function to show controls and status for the new sensors/devices.
html ---------------------------------------------------------
<div id="newRoom" class="container" style="display: none;">
  <h2>New Room</h2>
  <!-- Add buttons to control devices in this new room -->
</div>
----------------------------------------------------------------


Update handleToggle function:
    Extend the handleToggle function to handle toggling of devices in the new room.
cpp---------------------------------------------------------------------------
else if (device == "newRoomLight") {
  digitalWrite(newRoomLightPin, !digitalRead(newRoomLightPin));
}
-------------------------------------------------------------------------------

Update handleStatus function:
    Modify handleStatus to include readings from the new sensors (like temperature and humidity) and any additional status information (e.g., motion detection).
cpp -------------------------------------------------------------------------------------------------------------------
float newRoomTemp = dht2.readTemperature();
float newRoomHumidity = dht2.readHumidity();
String json = "{\"newRoomTemp\":" + String(newRoomTemp) + ",\"newRoomHumidity\":" + String(newRoomHumidity) + "}";
----------------------------------------------------------------------------------------------------------------------

  

Update loop function:
    Adjust the loop function to include checking for inputs from new sensors (like motion sensors).
cpp ---------------------------------------------------
if (digitalRead(newRoomMotionPin) == HIGH) {
// Handle motion detection in the new room
}
-------------------------------------------------------



Additional Considerations :-
    Error Handling: Ensure proper error handling and validation for sensor readings and device controls.
    Power Requirements: Verify that adding more sensors and devices doesn't exceed the power capabilities of your Arduino board or power supply.
    Testing: Test each new addition incrementally to ensure it integrates correctly with the existing setup without introducing conflicts or issues.
    By following this approach, you can expand your smart home setup to include additional rooms and sensors, enhancing the functionality and usability of your Arduino-based system.
