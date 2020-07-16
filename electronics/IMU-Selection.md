---
title: IMU Selection Guide
parent: Electronics
---

# *How to choose an IMU* 
* Please for the love of god don't use a sensor just because it's cheap 
* Consider expected G loads, then double or triple for safety margins 
* Lower drift figures are usually better but watch out for best case scenario lies (lookin at you invensense)
* Bosch and ST have FAR better sensing topology than Invensense almost as a rule
* Note that the BNO055 has onboard sensor processing you pay extra for that will NOT work in a rocket context, buy the BMX055. 
* Spending that bit extra on a better sensor will help alleviate pain down the line as you don't have to fight it as much
* Don't bother with breakouts on flight hardware, design your own integration on the flight board, follow the datasheet's recommended layout and circuits, maybe add a bit of extra decoupling, as a treat. 
* Breakouts being attached to your board can lead to sensor decoupling sensed motion from your airframe due to waffling around which is why we don't really recommend using them even though it seems easier. SMD soldering is not that hard and saves you money and pain 


## **DO NOT USE THE MPU SERIES, Their sensing technology is ancient, driftier than InitialD, total BS in the datasheet, and the DMP is useless** 

## Supply your sensors with a clean, solid and quiet voltage rail for best results

| IMU Name | Price | DOF | Ranges | Precision | Drift figures | Library? | Recommended|
| ---      | ---   |---  |---      |---        |---            |---       |---|   
| MPU6050 | $2 (EOL) | 6 (Acc/Gy) | ±16g  ±2000°/sec | 16Bit | ±50mg(up to ±80mg) ±20º/s | Multiple libraries | HELL NO USE SOMETHING ELSE| 
| MPU9250 | $3 (EOL) | 9 (Acc/Gy/Mag) | ±16g  ±2000°/sec | 16Bit | ±50mg(up to ±80mg) ±20º/s | Multiple libraries | LITERALLY A 6050 WITH A MAG TAPED ON| 
| LSM9DS1 | $6.70 |  9 (Acc/Gy/Mag) | ±16g  ±2000°/sec ±16gauss | 16Bit | ±90mg(stable) ±30º/s ±1 gauss| Multiple libraries | Yes, a good sensor that doesn't have wildly wandering drift values | 
| LSM6DS0 | $5.25 |  6 (Acc/Gy/) | ±16g  ±2000°/sec  | 16Bit | ±20mg ±1º/s | A few | Kinda, really recommend the LSM9DS1 a bit more due to it being proven out and better libraries | 
| LSM6DS032 | $3.79 |  6 (Acc/Gy/) | ±32g  ±2000°/sec  | 16Bit | ±20mg ±0.5º/s | None | Not yet, brand new sensor and is untested with no libraries | 
| BNO055 | $11.16 |  9 (Acc/Gy/Mag) | ±16g  ±2000°/sec ±13gauss | 16Bit(gyro/mag) 14bit(acc) | ±80mg ±2º/s ±.04 gauss| Multiple libraries | No, you're paying more for an onboard processor that doesn't work with rocket g-loads |
| BMI055 | $6.61 |  9 (Acc/Gy/Mag) | ±16g  ±2000°/sec ±13gauss | 16Bit(gyro/mag) 14bit(acc) | ±80mg ±2º/s ±.04 gauss| No | Yes, same sensors as the BNO but without the processor |
| BMX055 | $7.99|  6 (Acc/Gy) | ±16g  ±2000°/sec  | 16Bit | ±80mg ±2º/s | No | Yes, same sensors as BNO minus magnetometer and processor |
| BMI088 | $7.87 |  6 (Acc/Gy) | ±24g  ±2000°/sec | 16Bit | ±20mg ±1º/s | One | Yes, good newer sensors with lower drift figures and stable readings|

There is litererally hundreds of IMU's out there to choose from. Make sure you do your research and follow this guide to find the best one for your project. Keep in mind, once you receive your IMU, you have a lot of software to write to pull orientation out of it. There is no simple way to do this, just do your research and work through it bit by bit. 
