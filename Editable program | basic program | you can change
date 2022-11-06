# Importing part

from ast import While
from cProfile import label
from doctest import Example
from multiprocessing.connection import answer_challenge
from operator import truediv
import webbrowser
import pyttsx3
import speech_recognition as sr
import datetime
import wikipedia
import pywhatkit as kit
from googletrans import Translator
import time
import requests
import os
import random
from tkinter import *
from tkinter.ttk import *
from time import strftime
from pynput.keyboard import Controller



# Variables 
harry_count = 0 # you an give any name
count = 0
faces = ["Head", "Tail"]
listener = sr.Recognizer()
translator = Translator()
API_KET = "f610b2191c27c4215a44c464963c6e0d"
BASE_URL = "https://api.openweathermap.org/data/2.5/weather"


# Correcting 'pttsx3' (Never Change)
engine = pyttsx3.init("sapi5")
voices = engine.getProperty('voices')
engine.setProperty('voice', voices[0].id)



# deffining 'Speak' function
def speak (audio):
    engine.say(audio)
    engine.runAndWait()



# deffining 'Wish me' function
def Wish_me ():
    hour = int(datetime.datetime.now().hour)

    if hour >= 0 and hour < 12:
        speak("Good Morning!!!")

    elif hour >= 12 and hour < 18:
        speak("Good Afternoon!!!")


    else:
        speak("Good Evening!!!")

    speak("I am Harry, how may i help you?")



# deffining 'Take Command' function
def Take_command():
    r = sr.Recognizer()
    with sr.Microphone() as source:
        print("\n")
        print("Call my name and say whatever you want...")
        r.pause_threshold = 2
        audio = r.listen(source)

    try: 
        print("Recognizing...")
        query = r.recognize_google(audio, language='en-in')
        print(f"User said:- {query}\n")


    except Exception as e:
        print("Say that again please...")
        speak("Please repeat...")
        return "None"

    return query



# Deffining 'Watch' function
def watch():
    string = strftime('%H%M%S%p')
    label.config(text = string)
    label.after(100, watch)




# def What_can_I_do():
    # Your choice (Add the features that your asistant can do)

    # Example:
    #     print("1. Search anything on YouTube")
    #     speak("Search anything on YouTube")





# Main Program
if __name__ == '__main__':
    Wish_me()

    while True:
        query = Take_command().lower()

        if "harry" in query:

            if "wikipedia" in query:
                speak('Searching Wikipedia...')
                query = query.replace("wikipedia", "")
                result = wikipedia.summary(query, sentences = 1) # You can change the 'sentences' and cahange it to how much ever you want
                print(result)
                speak(result)

            elif 'youtube' in query:
                while True:
                    time.sleep(1)
                    listener = sr.Recognizer()
                    search = "What Do you want to watch or listen from youtube"
                    answer = print(search)
                    speak("what Do you want to watch or listen from youtube")
                    time.sleep(3)
                    try:
                        with sr.Microphone() as source:
                            print("listening")
                            voice = listener.listen(source)
                            info = listener.recognize_google(voice)
                            print("")
                            print("opening...")
                            time.sleep(1)
                            kit.playonyt(info)
                            print("")
                            time.sleep(5)
                            print("completed")
                            print("")
                            time.sleep(3)
                            break
                    except:
                        pass
                time.sleep(5)
                key = Controller()
                key.press('f') # to FUll screan the youtube window
                key.release('f')
                quit()
