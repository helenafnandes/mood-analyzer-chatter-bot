# Mood Analyzer Chatbot

This project implements a chatbot tailored for a bakery, capable of engaging in conversation with users to provide information about the bakery's products and services, as well as assist with placing orders. The chatbot utilizes several natural language processing (NLP) techniques including spell checking and sentiment analysis to enhance user experience and interaction quality.

## Functionalities

1. ✅**Spell Checking**: The chatbot corrects spelling errors in user input to improve understanding and ensure accurate responses.

2. ✅**Sentiment Analysis**: Integrated sentiment analysis allows the chatbot to gauge the sentiment of user inputs. In case of negative sentiment, appropriate actions are taken to address the user's concern and escalate it to the bakery staff if needed.

3. ✅**Web-Based Interface for Tests**: A user-friendly web interface enabling easy viewing and testing of the chatbot.

4. 🔳**Enhanced Spell Checking**: Implement spell checking functionality that leverages keyboard configuration for improved accuracy and efficiency.

## How to Use

### Live Demonstration

You can experience the chatbot through a live web application by following this [link](#).

### Local Installation

If you prefer to run the chatbot on your own machine, you can download the chatbot folder and set it up locally.

To download the necessary files, run the following command in your terminal:

```bash
git clone https://github.com/helenafnandes/mood-analyzer-chatter-bot.git --depth 1 --filter=blob:none --sparse && cd mood-analyzer-chatter-bot && git sparse-checkout init --cone && git sparse-checkout set chatbot
```

Then, follow these instructions:

0. **Personalizing and Training the Chatbot**
   - **Personalization**: Modify the contents of the `intents.json` and `messages.json` files located in the `personalization_files` directory to tailor the chatbot to your context and specific use cases. Customize messages in the `messages.json` file to personalize responses.
   - **Training**: Execute the `training.py` script to train the chatbot.

1. **Running the Chatbot**:
   - Launch the chatbot by running the `chatbot.py` script.
   - Upon initialization, the chatbot greets the user and awaits input.

2. **Interacting with the Chatbot**:
   - With the original intents.json and messages.json files, users can type messages or questions related to the bakery's products, services, or any other inquiries.
   - The chatbot responds accordingly, providing relevant information or assistance.

3. **Ending the Chat**:
   - To conclude the conversation, simply type "goodbye" or any other exit keyword as defined in the intents.
      - If there is a "goodbye" intent on the intents.json file, the bot detects it and stops the application.

## Use Example

The bot will analyze the intents of the user's message and respond accordingly

Example:

```bash
Welcome to our bakery chatbot! 🍰🍩 I'm here to assist you with any questions you have about our delicious treats and services. Feel free to ask me anything, from information about our products to placing an order. Let's get started! How can I assist you today?
You: hello! what are your cake options?
Bot: Our cake selection includes flavors like chocolate, vanilla, red velvet, carrot, and lemon drizzle. Feel free to ask for more details or suggestions!
You: awesome, thanks
Bot: No problem at all! We're here to help if you have any other questions or need suggestions.
```

## Spell Checking

The spell checking functionality is implemented in the `spell_corrector.py` module using TextBlob. It corrects spelling errors in user input, ensuring better comprehension by the chatbot.

Example:

```python
from chatbot.chatbot import spell_check

input_text = "I wnt to oreder a cak"
corrected_text = spell_check(input_text)
print("Corrected text:")
print(corrected_text)  # "i want to order a can"
```

## Sentiment Analysis

Sentiment analysis is performed using spaCy and VADER (Valence Aware Dictionary and sEntiment Reasoner). It allows the chatbot to detect the sentiment of user inputs and take appropriate actions, such as addressing negative sentiment.

Example:

```python
from chatbot.chatbot import analyze_sentiment

text = "I'm very satisfied with your service."
sentiment = analyze_sentiment(text)
print("Sentiment:", sentiment)  # "Sentiment: Positive
```

## Personalizing the Bot

- The chatbot's behavior and responses can be personalized to suit different contexts or businesses. This customization primarily depends on the contents of the `intents.json` file. By modifying or adding intents and their corresponding patterns and responses in the `intents.json` file, the chatbot can be adapted to their specific requirements and industry domain.
- You may also modify the chatbot's actions depending on the intent or the sentiment of the user's sentence. For example, if the user wants to make an order, the bot can start an order making process instead of just showing a message.

## Libraries and Technologies Used

- **TensorFlow**: Used for building and training the neural network model for intent classification.
- **spaCy**: Utilized for tokenization and natural language processing tasks.
- **VADER Sentiment Analysis**: Integrated for sentiment analysis of user inputs.
- **TextBlob**: Employed for spell checking functionality.

## Thanks to Resources

This project was made possible because of some awesome content I used to learn about NLP techniques and to build this project. A big thank you for the following resourcers and creators:

- **"Natural Language Processing (NLP) Tutorial with Python & NLTK"**: Instructed by Edureka on freecodecamp's YouTube channel. Available at [this link](https://www.youtube.com/watch?v=X2vAabgKiuM&t=1s).
- **"Intelligent AI Chatbot in Python"**: Created by NeuralNine. Available on YouTube at [this link](https://www.youtube.com/watch?v=1lwddP0KUEg&t=1522s).
- **"What is Sentiment Analysis?"**: On aws.amazon.com, available at [this link](https://aws.amazon.com/what-is/sentiment-analysis/?nc1=h_ls).

## Contributions and Suggestions
Suggestions for improvements or additional features are much appreciated! Contributions to the project are also welcomed. Please feel free to fork the repository, make changes, and submit pull requests.
