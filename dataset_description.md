# LUMO Multilingual Speech Dataset — Dataset Description

## Overview

The **LUMO Multilingual Speech Dataset** is a custom speech corpus collected to support the evaluation of offline Automatic Speech Recognition (ASR) systems and privacy-preserving voice assistants running on edge devices. The dataset was developed as part of the research project **"LUMO: A Privacy-Preserving Offline Voice Assistant"** at Jatiya Kabi Kazi Nazrul Islam University (JKKNIU), Bangladesh.

The dataset focuses on short, command-style utterances typical of voice assistant interaction systems, recorded in two languages: **English** and **Bangla**.

---

## Purpose

This dataset was created to:

- Evaluate offline ASR performance under varying noise conditions on a Raspberry Pi 5
- Benchmark multilingual (English + Bangla) speech recognition for low-resource settings
- Support research on privacy-preserving voice assistants operating without cloud connectivity
- Enable reproducible evaluation of the LUMO system pipeline (VAD → STT → LLM → TTS)

---

## Collection Methodology

### Recording Environment
Recordings were captured in controlled indoor environments across three noise conditions:

| Condition          | Noise Level | Notes                        |
|--------------------|-------------|------------------------------|
| Quiet              | < 30 dB     | Silent indoor room           |
| Moderate (Office)  | 45–60 dB    | Typical office background    |
| High (Public)      | 70–75 dB    | Crowded/public area noise    |

### Recording Device
- **Microphone:** USB Condenser Microphone
- **Sampling Rate:** 16 kHz
- **Channels:** Mono
- **Format:** WAV (16-bit PCM)

### Speakers
- **Total Speakers:** 20 (10 English + 10 Bangla)
- **Demographics:** Mixed male and female participants
- **Background:** University students and staff

---

## Dataset Statistics

| Attribute              | Details                        |
|------------------------|--------------------------------|
| Total Utterances       | 1,000                          |
| English Utterances     | 500 (from 10 speakers)         |
| Bangla Utterances      | 500 (from 10 speakers)         |
| Utterances per Speaker | ~50                            |
| Utterance Length       | 3–10 words                     |
| Total Duration         | ~60 minutes (approx.)          |

---

## File Naming Convention

### English
```
eng_001.wav, eng_002.wav, ..., eng_050.wav
```

### Bangla
```
ban_001.wav, ban_002.wav, ..., ban_050.wav
```

Files are numbered sequentially and correspond line-by-line to entries in `transcripts/transcripts.txt` and `metadata.csv`.

---

## File Descriptions

| File | Description |
|------|-------------|
| `dataset/english/speaker*/eng_*.wav` | English speech recordings |
| `dataset/bangla/speaker*/ban_*.wav`  | Bangla speech recordings  |
| `transcripts/transcripts.txt`        | Ground-truth transcriptions in `filename\|transcription` format |
| `metadata.csv`                       | Speaker and language metadata per recording |
| `README.md`                          | Repository overview and citation info |

---

## Transcription Format

The `transcripts/transcripts.txt` file uses pipe-delimited format:

```
eng_001.wav|Hello Lumo
eng_002.wav|Hi Lumo
eng_003.wav|How are you
...
```

The `metadata.csv` file uses comma-separated format:

```csv
filename,language,speaker,transcript
eng_001.wav,english,speaker01,Hello Lumo
eng_002.wav,english,speaker01,Hi Lumo
...
```

---

## ASR Evaluation Results

The dataset was used to evaluate the VOSK offline ASR engine as part of the LUMO system:

| Language | Avg. Utterance Length | WER (%)  |
|----------|-----------------------|----------|
| English  | 3–5 words             | 6.8      |
| Bangla   | 3–5 words             | 9.9      |

WER results are for moderate noise (office, ~50 dB) conditions.

---

## License

This dataset is released under the [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) license. You are free to use, share, and adapt the material for any purpose, provided appropriate credit is given.

---

## Citation

If you use this dataset, please cite:

```bibtex
@misc{naeem2025lumo,
  title        = {LUMO: A Privacy-Preserving Offline Voice Assistant},
  author       = {Naeem, Md. Mehedi Hasan and Ruma, Mst. Kamrunnahar and
                  Anjum, Nafiza and Sultana, Shakila and Ali, Md. Sujan},
  year         = {2025},
  howpublished = {Department of Computer Science and Engineering,
                  Jatiya Kabi Kazi Nazrul Islam University, Bangladesh},
  note         = {Research project paper}
}
```

---

## Contact

For questions or collaboration, please reach out to any of the authors:

| Name | Role | Email |
|------|------|-------|
| Md. Mehedi Hasan Naeem | Author | mehedinaeem00@gmail.com |
| Mst. Kamrunnahar Ruma | Author | kamrunnaharruma242@gmail.com |
| Nafiza Anjum | Author | nafizaanjum.2002@gmail.com |
| Shakila Sultana | Author | shakila161470@gmail.com |
| Md. Sujan Ali | Supervisor | sujan_cse@jkkniu.edu.bd |

All authors are affiliated with:

> **Department of Computer Science & Engineering**  
> Jatiya Kabi Kazi Nazrul Islam University (JKKNIU)  
> Mymensingh, Bangladesh
