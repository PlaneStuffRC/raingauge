# DIY Inductive Rain Gauge

An open-source tipping bucket rain gauge featuring a **Microchip LX3302A inductive position sensor** instead of a traditional reed switch or Hall sensor.

![Rain Gauge](rain-gauge.png)

---

## Features

- No reed switch
- No magnets
- Contactless measurement
- High reliability
- Weather resistant
- High resolution bucket angle measurement
- ESPHome integration
- Home Assistant ready

---

## How it Works

The rain gauge uses a standard tipping bucket mechanism.

As rain fills one side of the bucket, it tips and empties while the opposite side begins collecting water.

Instead of detecting the tip with a reed switch, the bucket position is continuously measured using the **Microchip LX3302A inductive position sensor**.

The sensor measures the angular position of a simple metal target mounted on the bucket pivot.

Advantages:

- No mechanical wear
- Immune to magnetic fields
- No bouncing contacts
- Detects complete bucket movement
- Can measure bucket angle, not only the tipping event

---

## Inductive Position Sensor

The LX3302A works by generating a high-frequency magnetic field using PCB coils.

A moving metal target changes the magnetic coupling between the transmitter and receiver coils.

The chip generates **SIN** and **COS** signals and calculates the position using:

```
Angle = atan2(SIN, COS)
```

No magnets are required.

---

## Hardware

- ESP32
- Microchip LX3302A
- Custom PCB
- 3D printed tipping bucket
- Stainless steel shaft
- PCB target

---

## Software

- ESPHome
- Home Assistant

Features include:

- Rain accumulation
- Rain rate (mm/h)
- Daily rainfall
- Automatic midnight reset
- Boot recovery
- Bucket direction detection

---

## Calibration

The funnel diameter and bucket volume determine the rainfall resolution.

Calibration is straightforward and only requires a known volume of water.

1. Pour a fixed amount of water (for example, 500 mL) into the funnel at a steady rate.
2. Count the total number of bucket tips (turns).
3. Repeat the test 10 times and calculate the average number of tips.
4. Calculate the rainfall per tip using the funnel collection area and the average tip count.
5. Adjust the bucket if necessary and repeat until the desired resolution (e.g. 0.2 mm per tip) is achieved.

Repeating the test multiple times minimizes measurement errors and ensures consistent calibration across the full tipping range.

The bucket volume can be adjusted to achieve the desired resolution (typically 0.2 mm/tip).

---

## 3D Printed Parts

- Funnel
- Bucket
- Housing
- Sensor mount
- Electronics enclosure

---

## Future Improvements

- Automatic self-calibration
- Temperature compensation
- Wind shield
- Battery-powered LoRa version

---

## License

GNU GPL v3
