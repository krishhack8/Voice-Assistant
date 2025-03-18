import pyttsx3
import webbrowser
import wikipedia
import os

def speak(text):
    """Convert text to speech."""
    engine = pyttsx3.init()
    engine.say(text)
    engine.runAndWait()

def process_command(command):
    """Process user commands and perform actions."""
    if "search" in command:
        search_query = command.replace("search", "").strip()
        speak(f"Searching for {search_query}")
        webbrowser.open(f"https://www.google.com/search?q={search_query}")
    
    elif "wikipedia" in command:
        search_query = command.replace("wikipedia", "").strip()
        try:
            result = wikipedia.summary(search_query, sentences=2)
            speak(result)
        except wikipedia.exceptions.DisambiguationError:
            speak("There are multiple results, please be more specific.")
        except wikipedia.exceptions.PageError:
            speak("Sorry, I couldn't find anything on Wikipedia.")
    
    elif "open notepad" in command:
        speak("Opening Notepad.")
        os.system("notepad")

    elif "exit" in command or "stop" in command:
        speak("Goodbye!")
        exit()
    
    else:
        speak("Sorry, I can't do that yet.")

if __name__ == "__main__":
    speak("Hello,there ! How can I assist you?")
    while True:
        user_command = input("Enter command: ")  # Replace voice input with text input
        process_command(user_command)
