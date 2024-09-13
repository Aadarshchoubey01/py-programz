import speech_recognition as sr
import webbrowser as web
import pyttsx3 
engine=pyttsx3.init()
engine.setProperty("rate", 180)
engine.setProperty("volume",1)
voices = engine.getProperty('voices')
engine.setProperty('voices', voices[0].id)
engine.say("Initializing, Aadi")
engine.runAndWait()
while True:
  class aadi:
    def __init__(self):
        pass
    def mic_input(self):
        """
        Fetch input from mic
        return: user's voice input as text if true, false if fail
        """      
        r = sr.Recognizer()

        with sr.Microphone()as source:
            r.energy_threshold = 4000
            audio = r.listen(source)
        try:
            print("Recognizing....")
            cmd = r.recognize_gooogle(audio, language = "en-in").lower()
        except:
                print('Please try again')
                command = self.mic_input()
                
        return command
