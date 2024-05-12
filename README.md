## EX. NO.8 :
## DATE: 06-05-2024
# Implementation of Speech Recognition
### Aim:
 To implement the conversion of live speech to text.
### Algorithm:
#### Step 1: 
Import the speech_recognition library
#### Step 2: 
Initialize the Recognizer
#### Step 3: 
Create an instance of the Recognizer class, which will be used for recognizing speech.
#### Step 4: 
Set the duration for audio capture
#### Step 5: 
Define a variable to specify the duration (in seconds) for which the program will capture audio from the microphone.
#### Step 6: 
Display a message in the console to prompt the user to speak.
#### Step 7: 
Capture audio from the default microphone
#### Step 9: 
Use the default microphone as the audio source.
#### Step 10: 
Record audio for the specified duration using the Recognizer instance.
#### Step 11: 
Perform speech recognition with exceptional handling
•	Attempt to recognize speech from the captured audio using the Google Speech Recognition service.
•	If successful, print the recognized text.
•	Handle specific exceptions: If the recognition result is unknown or if there is an issue with the request to the Google Speech Recognition service, print corresponding error messages.
•	A generic exception block captures any other unexpected errors.
### Program:
~~~
import speech_recognition as sr
def record_audio():
    r=sr.Recognizer()
    r.energy_threshold = 6000
    voicedata=''
    try:
        with sr.Microphone() as source:
            audio=r.listen(source)
            voicedata=r.recognize_google(audio)            
    except sr.UnknownValueError:
        print("Unable to Recognize Audio")
    except sr.RequestError:
        print("Unable to find the Resource")
    return voicedata
while True:
    print("Say Something ....")
    text=record_audio()
    print(text)
    if text=="stop" or text=="close" or text=="exit":
        exit(1)
~~~
### Output:
![image](https://github.com/21005984/Ex-8--AAI/assets/94748389/d537ce83-0937-4d7b-8cca-df5460341bcc)

### Result:
Thus, The implementation of speech recognition is executed successfully.
