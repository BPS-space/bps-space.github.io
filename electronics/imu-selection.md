---
parent: Electronics
---

# _How to choose an IMU_

-   Don't consider price as your main deciding factor, the cheapest option might
    still have the worst price/performance.- Consider expected G loads, then
    double or triple for safety margins.
-   Lower drift figures are usually better but be wary of incorrectly reported
    measurements.
-   Bosch and ST have FAR better sensing topology than Invensense almost as a rule
-   Note that the BNO055 has onboard sensor processing you pay extra for that
    will NOT work in a rocket context, buy the BMX055.
-   Spending that bit extra on a better sensor will help alleviate pain down the
    line as you don't have to fight it as much
-   Consider ditching breakout boards, instead design your own integration on
    board, follow the datasheet recommended schematic and layout.
-   Breakouts being attached to your board can lead to sensor decoupling sensed
    motion from your airframe due to waffling around which is why we don't really
    recommend using them even though it seems easier. SMD soldering is a useful
    skill and opens the door to much more accurate sensor implementations.

## IMU Suggestions

**DO NOT USE THE MPU SERIES**. Their sensing technology is ancient, drifts more
than Initial D, has incorrect datasheet representation, and useless DMP.

Supply your sensors with a clean, quiet, and correct voltage reference for best
results

**A** = Accelerometer
**G** = Gyroscope
**M** = Magnetometer

| Name      | Price    | [DOF]     | Ranges                   | Precision           | Drift figures                 | Library? | Recommended                                                                                    |
| --------- | -------- | --------- | ------------------------ | ------------------- | ----------------------------- | -------- | ---------------------------------------------------------------------------------------------- |
| MPU6050   | $2 (EOL) | 6 (A+G)   | ±16g ±2000°/sec          | 16Bit               | ±50mg(up to ±80mg) ±20º/s     | Many     | Bad drift, bad lifetime, **do not use**                                                        |
| MPU9250   | $3 (EOL) | 9 (A+G+M) | ±16g ±2000°/sec          | 16Bit               | ±50mg(up to ±80mg) ±20º/s     | Many     | Same sensors as `6050`, **do not use**                                                         |
| LSM9DS1   | $6.70    | 9 (A+G+M) | ±16g ±2000°/sec ±16gauss | 16Bit               | ±90mg(stable) ±30º/s ±1 gauss | Many     | Yes, good drift figures and a proven architecture                                              |
| LSM6DS0   | $5.25    | 6 (A+G)   | ±16g ±2000°/sec          | 16Bit               | ±20mg ±1º/s                   | Some     | Maybe, really recommend the LSM9DS1 a bit more due to it being proven out and better supported |
| LSM6DS032 | $3.79    | 6 (A+G)   | ±32g ±2000°/sec          | 16Bit               | ±20mg ±0.5º/s                 | One      | Maybe, a newer sensor with support from adafruit                                               |
| BNO055    | $11.16   | 9 (A+G+M) | ±16g ±2000°/sec ±13gauss | 16Bit(G/M) 14bit(A) | ±80mg ±2º/s ±.04 gauss        | Many     | No, built-in sensor fusion fails under flight loads                                            |
| BMI055    | $7.27    | 9 (A+G+M) | ±16g ±2000°/sec ±13gauss | 16Bit(G/M) 14bit(A) | ±80mg ±2º/s ±.04 gauss        | None     | Yes, same sensors as the BNO but without the processor                                         |
| BMX055    | $6.00    | 6 (A+G)   | ±16g ±2000°/sec          | 16Bit               | ±80mg ±2º/s                   | None     | Yes, same sensors as BNO minus magnetometer and processor                                      |
| BMI088    | $7.30    | 6 (A+G)   | ±24g ±2000°/sec          | 16Bit               | ±20mg ±1º/s                   | One      | Yes, best choice, a good newer sensor with lower drift figures than others                     |

[dof]: https://en.wikipedia.org/wiki/Degrees_of_freedom "Degrees of freedom"

There are literally hundreds of IMU's out there to choose from. Make sure you
do your research and follow this guide to find the best one for your project.
Keep in mind, once you receive your IMU, you have a lot of software to write to
pull orientation out of it. There is no simple way to do this, just do your
research and work through it bit by bit.
