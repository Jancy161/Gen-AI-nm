# Gen-AI-nm
import nltk
from nltk.chat.util import Chat, reflections

# Define some reflections to transform input (e.g., "I am" -> "you are")
reflections = {
    "i am": "you are",
    "i was": "you were",
    "i": "you",
    "i'm": "you are",
    "i'd": "you would",
    "i've": "you have",
    "i'll": "you will",
    "my": "your",
    "you are": "I am",
    "you were": "I was",
    "you've": "I have",
    "you'll": "I will",
    "your": "my",
    "yours": "mine",
    "you": "me",
    "me": "you",
}

# Define some simple patterns and responses
pairs = [
    [
        r"my name is (.*)",
        ["Hello %1, How are you today?",]
    ],
    [
        r"what is your name?",
        ["My name is Chatterbox  and I'm a chatterbox.",]
    ],
    [
        r"how are you ?",
        ["I'm doing good\nHow about You ?",]
    ],
    [
        r"sorry (.*)",
        ["Don't apologize, it's okay.",]
    ],
    [
        r"(.*) (good|great|fine)",
        ["That's good to hear!",]
    ],
    [
        r"(.*) age?",
        ["I am a computer program and I don't have an age.",]
    ],
    [
        r"quit",
        ["Bye, take care. See you soon :) ","It was nice talking to you. Goodbye!"]
    ],
]

# Create a ChatBot using the defined patterns and reflections
def chatbot():
    print("Hi, I'm ChatBot! How can I help you today?")
    chat = Chat(pairs, reflections)
    chat.converse()

# Main function to run the chatbot
if __name__ == "__main__":
    nltk.download("punkt", quiet=True)
    chatbot()
