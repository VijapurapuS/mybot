## DIY: BUILD YOUR OWN JARVIS! (AI Chatbot)
### By Subhash Naveen V<br>
Please visit the below blog for referring to the Original article.<br>
https://medium.com/@naveen.vijapurapu/diy-build-your-own-jarvis-7fae3801c49

Credit — Marvel Studios
It is no longer just a figment of Scify imagination on the big movie screens to have an Artificial Intelligent Robot similar to Jarvis for IronMan replying to your queries. And NO, you don’t have to be wealthy rich like Tony Stark either to own one (or one of the big MNC’s). Sounds interesting, then please continue reading..
Below we go through some of the popular options for creating AI Chatbots.
But first, let us understand the architecture and the inner working details of a Chatbot.
Process flow of NLP (Natural Language Processing) Pipeline:
Most of the chatbots follow the below structure to identify the intent and entity classifications which is fed in to a pre-trained machine learning model to predict suitable responses to the input query. The steps are as follows —
· Text Processing (Input & Output)
Cleaning
Normalization
Tokenization
Stop Word Removal
Part of Speech Tagging
Named Entity Recognition
Stemming and Lemmatization
· Feature Extraction
Bag of Words
TF-IDF (Term Frequency — Inverse Document Frequency)
Word Embeddings
· Modeling
The final stage of the NLP pipeline is modeling, which includes designing a statistical or machine learning model, fitting its parameters to training data, using an optimization procedure, and then using it to make predictions about unseen data.

Credit — Wall-E & Eva characters are Copyrighted by Disney Pixar Studios
Different Types of Chatbots –
Contextual AI- (Set of Rules or State Machines)
· Notifications (Automated messages on expiry or for renewal)
· FAQ Chatbots (Hardcoded commonly asked FAQ’s)
Conversational AI & Types-
· Rule Based ChatBot
· Retrieval Based (TF-IDF)
o Few of the frequently used models for Chatbots –
§ CNN (Convolutional Neural Networks)
§ DNN (Neural Networks)
· Generative Based
o Deep Learning
§ RNN (Recurrent Neural Networks)
Now that we understood the inner workings of a chatbot, let us now compare the three poplar options available and used in the industry based on varying degrees of Ease of Use versus Open Source.
We will go over Diaglogflow, Chatterbot & RASA as our three options to build chatbots.
Side by side comparison

Now as we can clearly see, there is no one single solution that fits all, we will go over the details of each of the options and leave it to you to pick the right tool for your needs!

Dialogflow (formerly Api.ai, Speaktoit) is a Google-owned developer of human–computer interaction technologies based on natural language conversations.
Give users new ways to interact with your product by building engaging voice and text-based conversational interfaces, such as voice apps and chatbots, powered by AI. Connect with users on your website, mobile app, the Google Assistant, Amazon Alexa, Facebook Messenger, and other popular platforms and devices.
Dialogflow is an end-to-end, build-once deploy-everywhere development suite for creating conversational interfaces for websites, mobile applications, popular messaging platforms, and IoT devices.
Natural language understanding recognizes a user’s intent and extracts prebuilt entities such as time, date, and numbers. You can train your agent to identify custom entity types by providing a small dataset of examples. You can also use 40+ prebuilt agents as templates.
In September 2014, Speaktoit released api.ai (the voice-enabling engine that powers Assistant) to third-party developers, allowing the addition of voice interfaces to apps based on Android, iOS, HTML5, and Cordova. The SDK’s contain voice recognition, natural language understanding, and text-to-speech. api.ai offers a web interface to build and test conversation scenarios. The platform is based on the natural language processing engine built by Speaktoit for its Assistant application. Api.ai allows Internet of Things developers to include natural language voice interfaces in their products.
Dialogflow now does sentiment analysis for each user query, powered by Cloud Natural Language. Sentiment analysis scores can be used to hand off unsatisfied users to live agents, or to get a better understanding of which intents lead to the highest customer sentiment.
References: https://www.diagflow.com
Wikipedia: Dialogflow

ChatterBot is a machine-learning based conversational dialog engine build in Python which makes it possible to generate responses based on collections of known conversations. The language independent design of ChatterBot allows it to be trained to speak any language.
How it works
An untrained instance of ChatterBot starts off with no knowledge of how to communicate. Each time a user enters a statement, the library saves the text that they entered and the text that the statement was in response to. As ChatterBot receives more input the number of responses that it can reply and the accuracy of each response in relation to the input statement increase. The program selects the closest matching response by searching for the closest matching known statement that matches the input, it then returns the most likely response to that statement based on how frequently each response is issued by the people the bot communicates with.

References:
https://github.com/gunthercox/ChatterBot
https://chatterbot.readthedocs.io/en/stable/

RASA is a set of open source Machine learning tools for developers for Conversational AI. An open source machine learning framework to automate text-and voice-based conversations.
Rasa’s primary purpose is to help you build contextual, layered conversations with lots of back-and-forth. To have a real conversation, you need to have some memory and build on things that were said earlier. Rasa lets you do that in a scalable way.
Rasa contains two main components:
· NLU — Natural Language Understanding for Intent Classification and Entity extraction
Takes unstructured data and converts them to structured data on the form of intents and entities
· Core — Framework for machine learning based, contextual decision making. Dialog Management component. Brains of the Conversational AI
Tutorial:
https://rasa.com/docs/rasa/user-guide/rasa-tutorial
Try RASA

Reference: https://rasa.com/
GitHub: https://github.com/rasaHQ/
Conclusion:
Hope this article has simplified the process for creating your own bot! Message me in the comments with your example bots for interaction.
These are my bot examples:
Chatterbot — https://shankachakra.pythonanywhere.com/
Dialogflow bot –dialogflow-demo-bot
References:
Udacity Nano Degree for Data Scientist
Searches on stackoverflow.com for research




















# flask-chatterbot

#### A web implementation of [ChatterBot](https://github.com/gunthercox/ChatterBot) using Flask.

## Local Setup:
 1. Ensure that Python, Flask, SQLAlchemy, and ChatterBot are installed (either manually, or run `pip install -r requirements.txt`).
 2. Run *app.py* with `python app.py`.
 3. The demo will be live at [http://localhost:5000/](http://localhost:5000/)

## How do I deploy this to a web server?
If you do not have a dedicated server, I highly recommend using [PythonAnywhere](https://www.pythonanywhere.com/), [AWS](https://aws.amazon.com/getting-started/projects/deploy-python-application/) or [Heroku](https://devcenter.heroku.com/articles/getting-started-with-python#introduction) to host your application.

### Deploying on Heroku
If you are deploying on Heroku, you will have to change the database adapter from `chatterbot.storage.SQLStorageAdapter` to `chatterbot.storage.MongoDatabaseAdapter` since SQLite3 isn't supported. To do this simply change the following line:

`english_bot = ChatBot("English Bot", storage_adapter="chatterbot.storage.SQLStorageAdapter")`

... to use the MongoDB adapter:

```
english_bot = ChatBot("English Bot", 
                     storage_adapter = "chatterbot.storage.MongoDatabaseAdapter",
                     database = mongodb_name,
                     database_uri = mongodb_uri)
```
... where `mongodb_name` is the name of the database you wish to connect to and `mongodb_uri` is the URI of a remote instance of MongoDB.

## License
This source is free to use, but ChatterBot does have a license which still applies and can be found on the [LICENSE](https://github.com/gunthercox/ChatterBot/blob/master/LICENSE) page.
