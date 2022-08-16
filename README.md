Motor-And-Servo-Driver-HAT from seengreat:www.seengreat.com
 ==========================================
# Instructions
## 1.1、Overview
    Motor And Servo Driver HAT is an module of  DC motor and servo driver specially designed for Raspberry Pi. This module can drive 2 channels of DC motors and 6 channels of servos at the same time. It can make the desired function come true only through the I2C protocol control register<br>
## 1.2、Parameters
Supply Voltage：6V~12V(VIN terminal or pin)<br>
Logic Voltage：3.3V<br>
PWM Driver Chip：PCA9685<br>
Interface Protocol：I2C<br>
Motor Driver Chip：TB6612FNG<br>
# Usage
## 2.1、Instructions of Hardware Interface Configuration
Motor And Servo Driver HAT has designed a separate power switch. After power on, the POWER needs to be turned to the ON position. In addition, all the address lines of I2C are led out, and the address can be set by means of the DIP switch. The demo codes we provide are set the address to 0X7F, and the DIP switch settings are as follows:<br>
 * Hardware Connection :Switch<br>
 *          A0 -> OFF                   A1 -> OFF<br>
 *          A2 -> OFF                   A3 -> OFF<br>
 *          A4 -> OFF                   A5 -> OFF<br>
## 2.2、Demo Codes
wiringpi Libraries Installation：<br>
sudo apt-get install wiringpi<br>
wget https://project-downloads.drogon.net/wiringpi-latest.deb  # Raspberry Pi 4B version upgrade<br>
sudo dpkg -i wiringpi-latest.deb<br>
gpio -v # If version 2.52 appears, it means that the installation has been successful<br>

_1、I2C Configuration of Raspberry Pi_
Start the system configuration of Raspberry Pi：<br>
sudo raspi-config<br>
Enable I2C Interface：<br>
Interfacing Options -> I2C -> Yes<br>
sudo reboot<br>
Check the enabled I2C devices：<br>
ls /dev/i2c*   # at this time it will print：“/dev/i2c-1”<br>
Install the I2C libraries：<br>
sudo apt install i2c-tools <br>
Install python's smbus：<br>
sudo apt install python-smbus <br>
Test the device address mounted on the I2C bus:<br>
sudo i2cdetect -y -a 1<br>

_2、Execute the demo codes_
Python:<br>
Access the directory of python：<br>
cd /home/pi/Motor And Servo Driver HAT/raspberry pi/python<br>
Execute：<br>
sudo python3 pca9685.py<br>
C:<br>
Access the directory of C：<br>
cd /home/pi/Motor And Servo Driver HAT/raspberry pi/c<br>
Execute：<br>
make clean<br>
make<br>
sudo ./main<br>

__Thank you for choosing the products of Shengui Technology Co.,Ltd. For more details about this product, please visit:
www.seengreat.com__
