# Gyro_Aim
A Embedded project mimicking the apache gun system.

## 🛠 Project Description
This project uses an MPU6050 gyroscope module connected to an ESP32 to capture motion data in real-time. The processed angular data (pitch and yaw) is wirelessly transmitted using the ESP-NOW protocol to another ESP32, which controls two servo motors to adjust orientation accordingly.

##  Key Features
- Real-time gesture-based control
- Wireless communication using ESP-NOW
- Dual-axis servo movement (X and Z)
- Calibration for accurate angle mapping
- Laser pointer integration for aiming indication

##  Hardware Used
- ESP32 (2x)  
- MPU6050 Gyroscope  
- Servo Motor (2x)  
- Laser Module (VCC + GND)  
- Jumper Wires, Breadboard  

##  Pin Connections

### Transmitter (ESP32 + MPU6050)
| Component    | ESP32 Pin |
|--------------|------------|
| MPU6050 SDA  | GPIO 21    |
| MPU6050 SCL  | GPIO 22    |
| VCC          | 3.3V       |
| GND          | GND        |

### Receiver (ESP32 + Servos + Laser)
| Component       | ESP32 Pin |
|------------------|-----------|
| Servo (Yaw)      | GPIO 12   |
| Servo (Pitch)    | GPIO 13   |
| Laser Module VCC | 3.3V      |
| Laser Module GND | GND       |

##  Working Principle

1. **Gyro Data Acquisition**  
   The MPU6050 provides gyroscopic data for pitch (x-axis) and yaw (z-axis) rotation.

2. **Data Processing**  
   Raw gyro values are filtered and integrated over time to calculate angles in degrees:
   angle += (gyro - bias) / sensitivity * dt
  
3. **Wireless Transmission**  
The angle data is sent to the receiver ESP32 via ESP-NOW.

4. **Servo Control**  
The receiver ESP32 maps the angle values to PWM duty cycles to control servo angles (0–180°).

##  Results & Observations
- Achieved smooth, real-time servo movement in response to hand gestures.
- Effective wireless range up to 20m indoors.
- Calibration reduced gyro drift significantly for stable angle tracking.


## 🔮 Future Enhancements
- Add camera for visual targeting
- Integrate haptic feedback for immersive control
- Use Wi-Fi mesh or LoRa for extended range

## 📄 License
This project is open-source and available under the MIT License.
 
