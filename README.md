# WhisperX Transcription + Diarization Audio Processing for Researchers
This repository contains a Jupyter notebook for qualitative researchers to transcribe, diarize speakers, and convert audio or video files into various text formats (csv, txt, json, & vtt). The notebook uses advanced transcription and diarization capabilities provided by Whisper and WhisperX, as well as [pyannote speaker-diarization-3.1](https://huggingface.co/pyannote/speaker-diarization-3.1) and [segmentation-3.0](https://huggingface.co/pyannote/segmentation-3.0) libraries from Hugging Face.  
 ###[A free Hugging Face token is required](https://huggingface.co/docs/hub/en/security-tokens)
 
 The code is derived and built from the following [Medium article](https://towardsdatascience.com/unlock-the-power-of-audio-data-advanced-transcription-and-diarization-with-whisper-whisperx-and-ed9424307281)

To be clear, I am a very novice programmer, and much of this work has been done in collaboration with ChatGPT. I am a PhD student with a focus on equity in STEM education as well as educational technology. I have tried to redesign the code so that it is much more useful for generating transcriptions for researchers like me and others I work with. 

This means: 
1. I wanted the ability to do batch transcriptions of audio files found in multiple subdirectories. 
2. I wanted to take advantage of WhisperX word level time stamping. 
3. Utilize pyannote's speaker diarization capabilities. 
4. Generate csv, txt, json, and vtt files for each audio file transcribe. 
5. Ability to anonymize specific names and places during transcription. 

![csv output example](image.png)

## What This Code Does

1. **Device and Configuration Setup**: Sets up the device (GPU or CPU) and other configuration variables like batch size, compute type, and model type.
2. **Library Imports**: Imports necessary libraries including PyTorch, WhisperX, and others for handling audio files, text processing, and file I/O.
3. **Path and File Type Setup**: Defines paths to your audio files and output directories and specifies the types of audio files to process.
4. **Pseudonym Loading**: Loads a CSV file containing pseudonyms for anonymizing transcripts.
5. **Audio Processing Functions**: Includes functions to find audio files, get file modification dates, anonymize text, convert segments to different formats, and process each audio file.
6. **Main Function Execution**: Finds all audio files in the specified directory, processes them, and saves the transcripts in multiple formats (CSV, TXT, JSON, VTT).

## How to Use This Code

### 1. Set Up Your Environment

- **Install Required Libraries**:
  Make sure you have all the required libraries installed. You can install them using pip:
  ```sh
  pip install os pandas torch whisperx gc datetime json webvtt srt
 
### 2. Configure Paths and Settings

Paths: Replace the placeholder paths with your actual directories:
```sh
base_dir = 'Data/RawAudioFiles_Inputs'       # Path to your main folder containing subfolders with audio files
output_base_dir = 'Data/Trancripts_Outputs'  # Path to the folder where you want to save the transcripts
```

## 3. Audio File Types

Update the file types if your audio files are in different formats:
```sh
file_type1 = '.wav'
file_type2 = '.mp3'
file_type3 = '.ogg'
```
## 4. Prepare Pseudonyms CSV
Pseudonyms CSV: Ensure you have a CSV file named pseudonyms.csv in the data directory. This file should contain columns name and pseudonym for anonymizing the transcripts.

## 5. Execute the set-up code
The main function finds all audio files in the specified directory, processes them, and saves the transcripts. To run the code, simply execute the script.

## 6. Execute the transcription and diarization functions
## 7. Check the Outputs
Output Files:
The transcripts will be saved in the specified output directory in multiple formats: CSV, TXT, JSON, and VTT

## Conclusion
This code is designed to make it easy to process and transcribe large batches of audio or video files while ensuring anonymity through pseudonymization. Happy transcribing!# WhisperXTranscription4Researchers