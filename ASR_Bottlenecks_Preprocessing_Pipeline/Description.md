# Folder Description — *ASR Bottlenecks: Preprocessing Pipeline*

Most research, experiments, and publicly available datasets often assume that the audio data is already clean and well-suited for ASR models. For example, the CSaLT dataset contains short, crisp, and carefully recorded utterances with virtually no background noise. However, most real-world audio rarely looks like that.  

A major bottleneck in our setting is the **limited free-tier GPU resources**. Passing *all* available audio files—including those we can easily judge as “garbage in, garbage out”—is wasteful and results in lost GPU hours.  

Therefore, this problem space focuses on identifying the **specific acoustic and signal challenges** that ASR models are most susceptible to. The goals are:  

- Identify measurable audio features that correlate with WER degradation  
- Automate the categorization of incoming audio files using these features  
- Define the thresholds/ranges of feature values that lead to significant performance drops  

We aim to classify audio into three categories:  

1. **Garbage** — non-salvageable recordings that should be discarded.  
2. **Needs preprocessing** — files with overlap, reverberation, or background noise that can be improved before transcription.  
3. **Clean** — recordings that can be passed directly to the ASR model.  

This balance between **limited GPU resources** and **limited clean data** is especially critical for **low-resource languages such as Urdu**.  

Our work starts with **monologue audio files**. If successful, we plan to extend to:  
- Two-person interviews with minimal overlap  
- Two-person dialogues with overlaps  
- Multi-speaker conversations recorded on a single microphone  

Our initial plan was to use **CSaLT and FLEUR datasets** (already part of our Unsloth fine-tuning pipeline), compute WER per file, analyze feature values, and train a regression model to predict WER from feature values on unseen audio.  

Currently, however, we are beginning with a **lightweight heuristic and rule-based approach** for simplicity and efficiency, before moving to regression or learned models.  
