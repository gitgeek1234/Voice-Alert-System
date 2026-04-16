# Voice-Alert-System

🛡️ AI-Based Voice Recognition Alert System
Real-Time Safety Monitoring via Spectral Fingerprinting
Developed between Oct 2024 – Jan 2025, this project is a specialized feature designed for integration into Women’s Safety Applications. It utilizes digital signal processing (DSP) and machine learning techniques to identify specific distress phrases (e.g., "Help!", "Emergency") in real-time, even under noisy environmental conditions.

🚀 Key Features
- Real-Time Keyword Spotting (KWS): Continuous audio monitoring with sub-100ms processing latency.
- Noise Robustness: Optimized signal preprocessing and threshold tuning to reduce false positives in public spaces.
- Dynamic Pattern Matching: Uses Dynamic Time Warping (DTW) to account for variations in speech speed and tone.
- Lightweight Architecture: Designed for mobile/edge deployment, requiring minimal computational overhead compared to heavy Deep Learning models.

The system identifies voice patterns by extracting unique "fingerprints" from audio signals.
1. Feature Extraction (MFCC)
The raw audio is converted into Mel-Frequency Cepstral Coefficients (MFCCs). This represents the power spectrum of the sound based on the human ear's perception (the Mel Scale).
The conversion from frequency ($f$) to mels ($m$) is defined by:
$$m = 2595 \log_{10}\left(1 + \frac{f}{700}\right)$$

2. Pattern Comparison (DTW)
To compare a "live" phrase against a "saved" phrase, we use Dynamic Time Warping. This algorithm finds the optimal alignment between two sequences, calculating a similarity score. An alert is triggered if:
 Score < Threshold
