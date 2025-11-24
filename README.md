### AIM: 

To perform and verify speech recognition using SCILAB. 

### APPARATUS REQUIRED:
software using co-lab

### PROGRAM : 
```
!pip install SpeechRecognition pydub

from google.colab import files
from IPython.display import Audio

uploaded = files.upload()

# Get file name
file_name = list(uploaded.keys())[0]

# Play the audio
print("Playing uploaded audio:")
display(Audio(file_name))

import speech_recognition as sr
from pydub import AudioSegment

# Convert mp3 → wav if needed
if file_name.endswith(".mp3"):
    sound = AudioSegment.from_mp3(file_name)
    file_name_wav = "converted.wav"
    sound.export(file_name_wav, format="wav")
else:
    file_name_wav = file_name

# Recognize speech
r = sr.Recognizer()

with sr.AudioFile(file_name_wav) as source:
    audio = r.record(source)

try:
    text = r.recognize_google(audio)
    print("Text from speech:")
    print(text)

except Exception as e:
    print("Error:", e)


```

### OUTPUT: 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/76f19917-2109-490c-b451-d100d981ca2b" />



https://github.com/user-attachments/assets/8b9f6be8-e34f-40bc-b38f-aa369aca0167



### RESULT: 
Thus the speech recognition using co-lab was performed and verified.
