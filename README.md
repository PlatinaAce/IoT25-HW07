# IoT25-HW07
25-1 Introduction to Internet of Things (IoT) Assignment #7

## Project Objective
This project aimed to develop a BLE-based distance estimation system using two ESP32 microcontrollers. By leveraging the Received Signal Strength Indicator (RSSI) and txPower values from BLE signals, we estimated the distance between two ESP32 devices in real time.

## Implementation Details
### Hardware Setup
Two ESP32 development boards were used: one as a BLE Server (advertiser), the other as a BLE Client (scanner).

### Software Approach
The BLE Server periodically broadcasted advertising packets.
The BLE Client scanned for these packets and retrieved the RSSI values using built-in functions (e.g., getRSSI()).
A path-loss model was applied to estimate the distance: distance (m) = 10 ^ ((txPower - RSSI) / (10 * n))
where n is the path-loss exponent, determined experimentally.
The estimated distance was printed in real time on the ESP32 Client’s serial monitor.

### Experimental Method
Measurements were taken at fixed intervals: 0.5m, 1.0m, 2.0m, 3.0m, and 4.0m.
Results were visualized both in a table and a bar chart, comparing actual and measured distances.

## Results
![Photo](Assignment7-Chart.png)
![Photo](Assignment7-Table.png)

### Performance Analysis
The system showed high accuracy at short distances (0.5–2.0m), with errors mostly within 0.1m.
At longer distances (3.0–4.0m), the error increased slightly, up to 0.36m.
The results are consistent with typical BLE-based distance estimation error margins reported in literature.
Main sources of error included environmental noise, multipath effects, and RSSI fluctuations.

## Photos/videos of the experiment
![Video](Assignment7.GIF)
![Video](Assignment7_Advanced1.GIF)
![Video](Assignment7_Advanced2.GIF)
