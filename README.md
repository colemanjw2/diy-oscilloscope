#  DIY Cathode-Ray Tube Oscilloscope (2AP1A)

A fully discrete, high-voltage, electrostatic CRT oscilloscope built from first principles.

This project recreates the fundamental operation of early oscilloscopes using a vacuum tube, analog deflection amplifiers, and a high-voltage supply — with no digital processing, sampling, or abstraction.

It is based on the designs found here:

https://web.archive.org/web/20120718013731/http://mysite.du.edu/~etuttle/electron/elecindx.htm

And it is specifically this project:

https://web.archive.org/web/20120714102433/http://mysite.du.edu/~etuttle/electron/elect29.htm

Because the college that once hosted this site has decided to no longer do so, one must use WayBack Machine to view but I have also put the full webpage in a folder inside of this repo. 

---

## Overview

This oscilloscope is based around the **2AP1A cathode-ray tube**, a small electrostatic CRT that allows direct visualization of electrical signals through electron beam deflection.

Unlike modern oscilloscopes:
- No ADCs  
- No memory  
- No triggering system  

The display is a **real-time physical representation of voltage**.

---

##  System Architecture

The build consists of three primary subsystems:

### 1. CRT (Display Device)
- 2AP1A electrostatic CRT
- ~2" phosphor screen (P1 green, medium persistence)
- Electrostatic deflection plates (X/Y)

---

### 2. Deflection Amplifiers
- High-voltage analog amplifiers (~150–200 Vpp output)
- Drive the deflection plates directly
- Configurable for:
  - single-axis waveform display  
  - X-Y (Lissajous) mode  

---

### 3. High Voltage Power Supply
- ~700–800 V DC supply
- Low current (~1 mA total load)
- Resistive divider network for:
  - cathode bias  
  - grid control  
  - focusing  
  - anode voltages  

---

## CRT Operation (2AP1A)

Electron beam flow:

```

Cathode → Grid 1 → Anode 1 → Grid 2 → Anode 2 → Deflection Plates → Screen

```

### Functional Breakdown

| Element            | Function                          |
|------------------|----------------------------------|
| Cathode          | Thermionic electron emission     |
| Grid 1           | Intensity (beam current control) |
| Anode 1          | Pre-acceleration + beam shaping  |
| Grid 2           | Focus control (electrostatic lens) |
| Anode 2          | Main acceleration (~700–1000 V)  |
| Deflection Plates| Signal-driven beam steering      |
| Screen           | Phosphor emission                |

---

## 📐 Deflection Physics

Electron acceleration:

```

½mv² = eV

```

Beam deflection:

```

D = S · V_d

```

Where:
- **D** = deflection (mm)  
- **V_d** = voltage difference across plates  
- **S** = sensitivity (mm/V)  

---

### Measured Performance

- Deflection sensitivity:  
```

S ≈ 0.23 mm/V

```

- Example:
- 145 Vpp → ~33 mm deflection

- Full screen (~44 mm):
```

≈ 190 V required

```

---

### Key Insight

The CRT does not "measure" signals digitally.

The signal is **applied directly to the deflection plates**, creating an electric field:

```

V_d = V₁ - V₂

```

That field physically steers the electron beam in real time.

---

## Lissajous Mode (X-Y Operation)

When two signals are applied:

- X-axis → horizontal deflection  
- Y-axis → vertical deflection  

The CRT draws the relationship between them.

### Example

- X = 1000 Hz  
- Y = 999 Hz  

Result:
- Slowly rotating pattern  
- Drift rate = **1 Hz difference**

---

## Voltage Distribution (Typical)

- Cathode: ~ -700 V  
- Grid 1: ~ -30 to -90 V (cutoff region)  
- Anode 1: intermediate voltage  
- Grid 2: ~140–300 V (focus adjustment)  
- Anode 2: ~700–1000 V  
- Deflection plates: near ground + signal  

---

## ⚠️ Safety

This project involves **lethal high voltage**.

- 700–1000 V DC present  
- Capacitors retain charge after power-off  

### Recommendations:
- Use the one-hand rule when probing  
- Verify discharge before handling  
- Use properly rated components  
- Do not modify wiring while powered  

---

## Experiments Enabled

- Basic waveform visualization (no timebase)  
- X-Y plotting  
- Lissajous frequency comparison  
- Beam focusing and intensity control   

---

##  Build Notes

- Derived from classic oscilloscope circuits (ARRL-era designs)
- Uses modern components where practical
- CRT mounted with custom mechanical support
- Deflection plates AC-coupled for signal input

---

##  Media

_Add photos here:_

- Full build  
- Internal wiring  
- CRT trace  
- Lissajous figures  

---

##  Project Video

_Add link here_

---

##  Purpose

This project is not about performance.

It is about understanding:

- how electrons behave in electric fields  
- how analog systems represent signals  
- how early instrumentation worked  

---

## Key Idea

```

Voltage → electric field → force → motion → visible trace

```

---

##  Future Work

- Add triggered sweep (timebase)  
- Improve amplifier bandwidth  
- Shielding and noise reduction  
- Calibration scaling  
