# 🎙️ Personal Voice Synthesis System

<div align="center">

### Transform text into your own voice with AI-powered speech synthesis

[Demo](https://huggingface.co/spaces/Harshitsoni294/Text-to-speech)
---

</div>

## 🌟 Overview

A cutting-edge Text-to-Speech (TTS) system that clones and synthesizes speech in your unique voice. Built on state-of-the-art deep learning architectures (Tacotron2 + HiFi-GAN), this project enables anyone to convert written text into natural, personalized audio output through an intuitive web interface.

**What makes this special?** Unlike generic TTS systems, this project is trained on your own voice, creating truly personalized speech synthesis that captures your vocal characteristics, intonation, and speaking style.

---

## 🎯 Live Demo

Try it now: **[Text-to-Speech Web App](https://huggingface.co/spaces/Harshitsoni294/Text-to-speech)** 🚀

No installation required - just type and hear your text come to life!

---

## ✨ Features

🎯 **Personalized Voice Cloning** - Train the model on your own voice recordings for authentic speech synthesis

🔊 **High-Fidelity Audio** - Produces clear, natural-sounding speech with HiFi-GAN vocoder

⚡ **Real-Time Synthesis** - Instant text-to-audio conversion through a user-friendly web interface

🎛️ **Customizable Parameters** - Fine-tune various synthesis parameters for optimal output quality

📊 **Visualization Tools** - View Mel spectrograms and attention alignments to understand the synthesis process

🌐 **Web-Based Interface** - No installation needed for end users - just type and listen

---

## 🏗️ Architecture

The system follows a two-stage neural architecture:

```
Input Text → Tacotron2 (Encoder-Decoder) → Mel Spectrogram → HiFi-GAN (Vocoder) → Audio Waveform
```

### Pipeline Flow

1. **Text Processing** - Input text is converted to phonetic representations using ARPAbet dictionary
2. **Mel Spectrogram Generation** - Tacotron2 encoder-decoder network generates Mel spectrograms
3. **Audio Synthesis** - HiFi-GAN vocoder converts spectrograms into high-quality audio waveforms
4. **Real-Time Playback** - Generated audio is immediately available for playback

---

## 📦 Installation

### Prerequisites

- Python 3.8+
- CUDA-compatible GPU (recommended for training)
- Google Drive account (for dataset storage)

### Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/Harshitsoni294/Speech-synthesis.git
   cd Speech-synthesis
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Prepare your dataset**
   ```bash
   python loadingdataset.py
   ```
   > 💡 **Tip**: For best results, record 200+ clear audio samples (10-15 seconds each) in a quiet environment

4. **Upload transcription metadata**
   ```bash
   python uploadtranscript.py
   ```
   > Ensure your `filelist.txt` contains accurate transcriptions for each audio file

5. **Configure model parameters**
   ```bash
   python modelparameters.py
   ```

6. **Initialize the environment**
   ```bash
   python trainingtacotron2.py
   ```

---

## 🚀 Usage

### Training Your Voice Model

Train the Tacotron2 model on your personal voice dataset:

```bash
python initialisetraining.py
```

⏱️ **Training time**: 10-20 hours depending on dataset size and hardware

### Generating Speech

Once trained, generate audio from text:

```bash
python hifiganaudiooutput.py
```

Then simply type your text in the web interface and click generate!

---

## 📁 Project Structure

```
├── trainingtacotron2.py      # Environment setup and model initialization
├── loadingdataset.py          # Dataset loading and preprocessing utilities
├── uploadtranscript.py        # Transcription file management
├── modelparameters.py         # Model configuration and hyperparameters
├── initialisetraining.py      # Training pipeline orchestration
├── hifiganaudiooutput.py      # Audio synthesis and generation
└── requirements.txt           # Python dependencies
```

### File Descriptions

| File | Purpose |
|------|---------|
| `trainingtacotron2.py` | Entry point - mounts storage, installs dependencies, initializes models |
| `loadingdataset.py` | Processes and loads audio datasets for training |
| `uploadtranscript.py` | Manages metadata and transcription files |
| `modelparameters.py` | Defines Tacotron2 and HiFi-GAN model configurations |
| `initialisetraining.py` | Executes the training loop for voice model |
| `hifiganaudiooutput.py` | Handles inference and audio generation |

---

## 🎓 How It Works

### 1. **Data Preparation**
Record your voice samples and create corresponding transcriptions. The system learns your vocal characteristics from this training data.

### 2. **Training Phase**
The Tacotron2 model learns to convert text to Mel spectrograms that represent your voice's acoustic features. This process captures:
- Pitch and tone
- Speaking rhythm
- Voice timbre
- Pronunciation patterns

### 3. **Synthesis Phase**
During inference:
1. Input text is converted to phonetic representation
2. Tacotron2 generates a Mel spectrogram
3. HiFi-GAN vocoder converts the spectrogram to audio
4. Output is delivered in real-time

---

## 🎨 Example Use Cases

- **Content Creation** - Generate voiceovers for videos and podcasts
- **Accessibility** - Create personalized screen readers
- **Language Learning** - Practice pronunciation with your own voice
- **Virtual Assistants** - Build AI assistants that speak in your voice
- **Audio Books** - Narrate books in your personal speaking style

---

## 🔧 Customization

Adjust synthesis parameters in `modelparameters.py`:

- **Speaking rate**: Control speech tempo
- **Pitch variation**: Adjust vocal range
- **Energy levels**: Modify volume dynamics
- **Noise levels**: Fine-tune audio clarity

---

## 📊 Technical Details

**Models Used:**
- **Tacotron2**: Sequence-to-sequence architecture with attention mechanism
- **HiFi-GAN**: Generative adversarial network for high-fidelity audio synthesis

**Training Data:**
- 200 voice recordings (custom dataset)
- Single speaker
- Diverse phonetic coverage

**Output Quality:**
- Sample rate: 22,050 Hz
- Bit depth: 16-bit
- Format: WAV

---

## 🤝 Contributing

Contributions are welcome! Whether it's bug fixes, feature additions, or documentation improvements, feel free to submit a pull request.

---

## 🙏 Acknowledgments

Built with:
- [Tacotron2](https://github.com/NVIDIA/tacotron2) by NVIDIA
- [HiFi-GAN](https://github.com/jik876/hifi-gan) vocoder
- ARPAbet pronunciation dictionary

---

<div align="center">


⭐ Star this repo if you found it useful!

</div>
