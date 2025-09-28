Even though there are certain gaps when it comes to ASR for Urdu via Whisper alone, in this particular folder, we will only focus on identifying,
addressing, and tuning decision boundaries related to Acoustic & Signaling challenges.

Acoustic Challenges are caused by environment or speaker characteristics. These include Reverberation/Echo, Background Noise, Overlapping Speech, 
Speaker Variability, Prosody & Speaking Rate, and Microphone Distance & Placement. 

Signal Challenges, on the other hand, are caused by recording quality, hardware, and preprocessing. These include Low Signal-to-Noise-Ratio (SNR), Clipping & Distortion, Dynamic Range Compression, Sampling Rate Mismatch, Bitrate & Encoding Artifacts, Channel Effects, Phase & Synchronization Errors.

While we do agree that not every single aspect can be fixed/worked on/improved, we will try to tackle the most common and most pressing issues that can be tackled. 

Let's look into each of these separately:
We will take each Acoustic Challenge one by one first and break it into:
1. What it means
2. What measurable audio feature/code metric indicates it
3. Decision rule → discard, preprocess, or pass directly

1. Background Noise
Example: Traffic, 
