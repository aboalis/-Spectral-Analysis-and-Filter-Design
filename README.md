# DSP Audio Filtering Project

Digital Signal Processing project implementing spectral estimation and digital filtering techniques to remove sinusoidal interference from audio signals.

![MATLAB](https://img.shields.io/badge/MATLAB-R2024b-orange.svg)
![DSP](https://img.shields.io/badge/DSP-Audio%20Processing-blue.svg)

## 📝 Project Description

This MATLAB implementation demonstrates:
- **Spectral Analysis** using Welch's Power Spectral Density (PSD) estimation
- **Digital Filter Design** using three different FIR filter methods
- **Multi-Criteria Decision Analysis** for optimal filter selection
- **Audio Processing** to remove 15.2 kHz interference from audio signals

**Course:** CIE 247 - Digital Signal Processing  
**Author:** Mohammed Ali Sadek (202200594)  
**Institution:** Zewail City of Science and Technology

## 🎯 Key Features

### Part 1: Spectral Estimation
- Welch's method parameter analysis (window type, FFT size, overlap, etc.)
- Visual comparison of different PSD estimation parameters
- Interference detection at 15.2 kHz

### Part 2: Digital Filter Design
- **Filter 1:** Equiripple Low-Pass (Parks-McClellan) - Order 170
- **Filter 2:** Least-Squares Low-Pass - Order 200 ✓ **Selected**
- **Filter 3:** Blackman Window Band-Stop - Order 250
- Automated decision matrix for filter selection
- Before/after PSD comparison for verification

## 🚀 Quick Start

### Prerequisites
- MATLAB R2020b or later
- DSP System Toolbox
- Signal Processing Toolbox

### Installation & Usage

1. **Clone or download** this repository

2. **Add your audio file** to the same directory as the code:
   - The code expects `music_test_fayrouz.mp3`
   - Or modify line 21 to use your own audio file:
     ```matlab
     [Y, Fs] = audioread("your_audio_file.mp3");
     ```

3. **Run the complete script:**
   ```matlab
   DSP_Audio_Filtering_Complete
   ```

4. **View results:**
   - Multiple figures showing spectral analysis
   - Filter frequency responses
   - Before/after filtering comparison
   - Console output with filter decision matrix

5. **Listen to results** (uncomment in code):
   ```matlab
   sound(signal, Fs)          % Original signal
   sound(sig_total, Fs)       % With interference
   sound(signalFiltered, Fs)  % After filtering
   ```

## 📊 Results Summary

### Filter Performance Comparison

| Filter | Order | Attenuation @ 15.2kHz | Passband Ripple | Utility Score |
|--------|-------|----------------------|-----------------|---------------|
| Equiripple LPF | 170 | 60.98 dB | 0.70 dB | 0.458 |
| **Least-Squares LPF** ✓ | **200** | **100.65 dB** | **0.44 dB** | **0.825** |
| Blackman BSF | 250 | 72.80 dB | 5.96 dB | 0.234 |

**Selected Filter:** Least-Squares Low-Pass Filter
- Highest attenuation at interference frequency (100.65 dB)
- Lowest passband ripple (0.44 dB)
- Best overall utility score (0.825)

### Spectral Analysis Findings

| Parameter | Effect |
|-----------|--------|
| **FFT Size** | Higher → Better frequency resolution |
| **Window Size** | Larger → Better freq. resolution, worse time localization |
| **Window Type** | Blackman: Best sidelobe suppression |
| **Overlap** | Higher → Smoother spectrum, lower variance |

## 📁 Project Structure

```
DSP-Audio-Filtering/
│
├── DSP_Audio_Filtering_Complete.m    # Main script (all-in-one)
├── music_test_fayrouz.mp3            # Audio file (user-provided)
├── filtered_audio.wav                # Output (generated)
└── README.md                         # This file
```

## 🔬 Technical Details

**Interference Specifications:**
- Frequency: 15.2 kHz
- Amplitude: 1.8
- Type: Sinusoidal

**Filter Design Constraints:**
- Maximum Order: 300
- Stopband Attenuation: ≥ 60 dB
- Passband Ripple: ≤ 1.0 dB
- Sampling Frequency: 32 kHz

**Decision Criteria Weights:**
- Attenuation (45%) - Most critical
- Passband Ripple (25%)
- Filter Order (20%)
- Preserved Bandwidth (10%)

## 📈 Output Files

The script generates:
- **Multiple figures** - Spectral analysis and filter responses
- **filtered_audio.wav** - Cleaned audio output
- **Console output** - Detailed filter comparison and decision matrix

## 🎓 Learning Outcomes

This project demonstrates:
- Advanced spectral analysis with Welch's method
- FIR filter design using multiple techniques
- Multi-criteria decision making for engineering solutions
- MATLAB DSP Toolbox proficiency
- Audio signal processing fundamentals

## 📝 License

MIT License - See LICENSE file for details

## 👤 Author

**Mohammed Ali Sadek**  
Communication & Information Engineering Student  
Zewail City of Science and Technology

[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/mohammed-ali-456101255)
[![GitHub](https://img.shields.io/badge/-GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/aboalis)

## 🙏 Acknowledgments

- Course: CIE 247 - Digital Signal Processing
- Zewail City of Science and Technology
- MATLAB & DSP System Toolbox

---

**Project Date:** May 2025  
**Last Updated:** January 2025
