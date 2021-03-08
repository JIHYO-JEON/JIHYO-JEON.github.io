---
layout: post
title: "How to Use Google TTS with Python - Tutorial"
date: 2020-08-03 20:46:00
tags: [ML paper]
---

![](https://cdn.aitimes.kr/news/photo/201710/10791_10296_126.png)

**More information:**
- DeepMind blog post about WaveNet [WaveNet - DeepMind](https://deepmind.com/blog/article/wavenet-generative-model-raw-audio)
- WaveNet Paper [arxiv](https://arxiv.org/pdf/1609.03499.pdf)

## Google TTS
### 1. First sign up for Google Cloud Platform
[Google Cloud Platform](https://console.developers.google.com/?hl=ko)
First, you need to add a new project Cloud Speech-to-Text API.
Then, download the json Auth key named like 'yourname-text-to-speech-0a0a000aa00a' with first 10 digits of your private key id.


### 2. Create Python project and place your json file in it
The environment needs your google application credentials, so it doesn't need to place in the same place with your code but make sure the address of the json file.

### 3. Environment Setting

```python

import os  
import time  
import html  
from google.cloud import texttospeech

```

If you use the conda environment for setting, install Google Cloud Sdk with the line below,
		`conda install -c conda-forge google-cloud-sdk`
And set the google application credentials.

	os.environ["GOOGLE_APPLICATION_CREDENTIALS"] = "./your_json_file"

And find the voice you want, with the function below,

```python

def list_voices():  
    """Lists the available voices."""  
  client = texttospeech.TextToSpeechClient()  
    # Performs the list voices request  
  voices = client.list_voices()  
    for voice in voices.voices:  
	# Display the voice's name. Example: tpc-vocoded  
  print(f"Name: {voice.name}")  
	# Display the supported language codes for this voice. Example: "en-US"  
  for language_code in voice.language_codes:  
	    print(f"Supported language: {language_code}")  
	ssml_gender = texttospeech.SsmlVoiceGender(voice.ssml_gender)  
	# Display the SSML Voice Gender  
  print(f"SSML Voice Gender: {ssml_gender.name}")  
	# Display the natural sample rate hertz for this voice. Example: 24000  
  print(f"Natural Sample Rate Hertz: {voice.natural_sample_rate_hertz}\n")
  
```

Here is the sample video of voices that you can see in the voice list. I picked "en-US-Standard-C" which is charismatic female voice.

[Voice Samples Video](https://www.youtube.com/watch?v=j9b7pNTE_SY)

	Name: en-GB-Wavenet-A  
	Supported language: en-GB  
	SSML Voice Gender: FEMALE  
	Natural Sample Rate Hertz: 24000  
	 
	Name: en-GB-Wavenet-B  
	Supported language: en-GB  
	SSML Voice Gender: MALE  
	Natural Sample Rate Hertz: 24000  
	 
	Name: en-GB-Wavenet-C  
	Supported language: en-GB  
	SSML Voice Gender: FEMALE  
	Natural Sample Rate Hertz: 24000  
	 
	Name: en-GB-Wavenet-D  
	Supported language: en-GB  
	SSML Voice Gender: MALE  
	Natural Sample Rate Hertz: 24000  
	 
	.
	.
	.

### 4. Create TTS voice file

The easiest way is just creating the 'mp3' or 'wav' file with the function below. There is no extra options in the way TTS reads.

```python

def text_to_speech(voice_name, text, filename):  
    language_code = "-".join(voice_name.split("-")[:2])  
    text_input = texttospeech.SynthesisInput(text=text)  
    voice_params = texttospeech.VoiceSelectionParams(  
	language_code=language_code, name=voice_name  
    )  
    audio_config = texttospeech.AudioConfig(  
	audio_encoding=texttospeech.AudioEncoding.LINEAR16  
    )  
    client = texttospeech.TextToSpeechClient()  
    response = client.synthesize_speech(  
	input=text_input, voice=voice_params, audio_config=audio_config  
    )  
    filename = f"{filename}.wav"
  with open(filename, "wb") as out:  
	out.write(response.audio_content)  
	print(f'Audio content written to "{filename}"'
	
```

Fill three inputs of this function (voice_name, text, filename) and run it. Then you can see the wav file named 'VoiceFiles.wav'.

```python

voice = "en-US-Standard-C"
Text = "His hope is based on the fact that he is a researcher for a company that has invented a revolutionary new technology. The refrigerator is an example of the type of devices that use this new technology. The refrigerator is not powered by electricity, but rather, it uses a special chemical to cool down."
text_to_speech(voice, Text, "VoiceFiles")

```

 If you want to change the file extension, fix the line,
 
```python

filename = f"{filename}.wav"
```

in the text_to_speech function definition.
	
