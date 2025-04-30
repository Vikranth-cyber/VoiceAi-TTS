# VoiceAi-TTS
This repository demonstrates a custom multilingual Text-to-Speech (TTS) model capable of generating voice samples in English, Hindi, and Telugu. It includes steps to prepare your dataset, fix metadata, train the model, and generate audio samples.
Custom Multilingual TTS Model
This project demonstrates the process of training and generating speech using a custom multilingual Text-to-Speech (TTS) model. It supports generating voice samples in English, Hindi, and Telugu.

Features
Multilingual Support: Generates speech in English, Hindi, and Telugu.

Custom Voice Model: Trains a TTS model using your dataset.

Audio Generation: Converts text input into audio files.

Prerequisites
Before using this project, ensure the following libraries are installed:

pandas

TTS

torch

shutil

You can install the required libraries by running:
        pip install pandas TTS torch
Setup
1. Prepare Your Dataset
Collect .wav audio files and a metadata.csv file that contains the file names and their corresponding texts.

Place all .wav files and the metadata.csv file into the /content/clips/ directory.

2. Fix Metadata Format
Ensure the metadata.csv file is properly formatted. If the file is pipe-delimited, the code automatically fixes it to be comma-delimited.

3. Train the Model
Place your TTS model checkpoint and configuration in the /content/clips/ directory.

Run the notebook cells to initialize and train the model.

4. Generate Audio
Use the model to convert text input into an audio file (e.g., output.wav).

Example Usage :
python:

### Example Usage:
```python
from TTS.utils.synthesizer import Synthesizer

synthesizer = Synthesizer(
    tts_checkpoint="/content/clips/checkpoint.pth", 
    tts_config_path="/content/clips/config.json"
)

output_wav = synthesizer.tts("Hello, this is your custom multilingual voice!")
synthesizer.save_wav(output_wav, "custom_voice_sample.wav")

print("Audio generated and saved as custom_voice_sample.wav")
### Download the checkpoint

You can download the model checkpoint file from [Dropbox here](https://www.dropbox.com/scl/fi/lz3wmgg9pactg3u270nmn/checkpoint_1110000.pth?rlkey=hn3g6pba7jkkzllcgw7xrzdzw&st=018dm6zk&dl=0).
