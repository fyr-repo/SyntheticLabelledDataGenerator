# Whisper ASR Transcriptor Pipeline for generating Weakly Labelled Training Data
**with Gemini powered Translation, Summarization for Transliteration**

---

Author:
*Fyroz S Dadapeer*       
*MTech CSE (Specialization in AI and DS)*        
*Indian Institute of Information Technology, Kota*

---

The below project does ASR using Multilingual whisper `large-v3` over any audio/video file given as input or a youtube url as input. We then use Google's Gemini API to translate/summarize/question-answering the transcription.

The entire pipeline applies other modules on top of vanilla whisper module such as Faster-whisper (which does inference over CTranslate2) and some audio preprocessing techniques (Audio Normalization, Dynamic Range Compress, Noise Reduce using spectral gating, weiner filter), a speaker diarization pipeline, Silero VAD (to remove noise), Demucs (to isolate voice activity) and Custom prompting in an attempt to improve accuracy of the quality of transcription.

--- 

This pipeline was created on a jupyter notebook to for trying and testing out various iterations and components of the pipeline. The code will be used to develop a library that can be used in big data/ parallel pipelines to generate large amount of synthetic weakly labelled training data for low resource languages. 

The library is currently a work in progress but anyone can go ahead and use the classes and functions to defined in the jupyter notebook.

---

Credits:

1. [Pyannote.audio](https://github.com/pyannote/pyannote-audio) - Speaker Diarization and Speech Segmentation pipeline
2. [Stable-ts Whisper](https://github.com/jianfch/stable-ts) - Wrapper for transcript alignment over OpenAI Whisper
3. [pytube](https://github.com/pytube/pytube) - Library to download video/audio files from youtube to generate the synthetic data over
4. [noisereduce](https://pypi.org/project/noisereduce/) - Preprocessing applied over audio inputs
5. [pydub](https://github.com/jiaaro/pydub) - Numpy based audio manipulation
6. [faster-whisper](https://github.com/SYSTRAN/faster-whisper) - Reimplementation of OpenAI whisper on CTranslate2 faster transformer engine
7. [CTranslate2](https://github.com/OpenNMT/CTranslate2/) - Efficient inference of Transformer Models
8. [demucs](https://github.com/facebookresearch/demucs) - Voice isolation library implemented by stable-ts
