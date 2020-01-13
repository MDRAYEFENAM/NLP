import pyttsx3
import speech_recognition as sr
import winsound
import time

talk = pyttsx3.init()
# Set properties _before_ you add things to say
talk.setProperty('rate', 150)    # Speed percent (can go over 100)
talk.setProperty('volume', 0.9)  # Volume 0-1

#possible lists of possible words or sentences with different punctuation
hi_List = ['hi', 'Hi', 'Hello', 'hello', 'Hey', 'hey', 'yo', 'Yo,' 'salam', 'Salam', 'hi totla', 'Hi totla', 'totla', 'Totla']
bye_List = ['Bye', 'bye', 'Goodbye', 'goodbye', 'Good bye' 'good bye', 'byebye', 'by by', 'By by', 'Tata', 'tata', 'So long', 'so long', 'okay bye', 'ok bye', 'Ok bye', 'Okay bye']
qst1_list = ["Who are you", 'who are you', 'whats your name', 'your name', 'Your name', 'What are you', 'what are you']
res_neg_list = ['bad robot', 'Bad robot','bad boy', "Bad boy", 'you are rude totla', 'You are rude totla', 'you are a bad robot', 'You are a bad robot']
Love_list = ['i love you', 'I love you', 'Love you', 'love you']
hate_list = ['i hate you', 'I hate you', 'Hate you', 'hate you']
friend_list = ['do you know who is my girl friend', 'do you know what is my girl friend name']
name_list =['do you know', 'who i am','do you know me', 'do you know what is my name']

def Listen():
    """
    Takes users voice as input and converts it to text.
    """
    speech = sr.Recognizer()
    #say beep before listening
    
    #take input from microphone
    with sr.Microphone() as source:
        winsound.Beep(frequency = 2500, duration = 100) #beep to inform that it's listening
        print("Say>>")
        voice = speech.listen(source) 
        text = speech.recognize_google(voice)
        print(text) #print what it heard just to debug

    return text  #return what was heard

    
def Decide(listen):
    """
    Takes decision based on what user says.
    """
    print(f" Command = {listen}.") #just to debug

    #see what user said is in which list or not
    if listen in hi_List:
        print("Resonse in Hi list")
        Respond("Hi there, Good to see you. Assalamualaikum")

    elif listen in bye_List:
        print("In bye list.")
        Respond("I liked talking with you, okay take care.")

    elif listen in Love_list:
        Respond("Yuk, I have a robot girl friend. No seat available")
    
    elif listen in hate_list:
        Respond("I Hate you too.")
     
    elif listen in qst1_list:
        Respond("""I am Totla Robot. The dumb talking robot written in python.
                    My creator Md Rayef Enam is trying to make me smart""")
    
    elif listen in res_neg_list:
        Respond("I am very sorry I was just joking.")
    
    elif listen in friend_list:
        Respond("Your girl friend name is Taspiya Jaha Joya and she live in Norway at Oslo city")
         
    elif listen in name_list:
        Respond("Your name is Md Rayef Enam and you are studying in Computer Science and Engineering at BGC Trust University Bangladesh")

    else:
        Respond("Sorry I don't understand Please say again.")

def Respond(t):
    print(f"Talking the: {t}") #to debug and see if everythings going okay

    talk.say(t)
    talk.setProperty('rate', 90) #90 words per minute
    talk.runAndWait()

while True: #for ever loop 

    comm = Listen() #listen to what user says

    Decide(comm)  #take decision and respond

    time.sleep(1)
