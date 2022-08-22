# ChatBot-using-Tensorflow-and-Neural-Network
By means of this project, we have learnt how to create a Chatbot using TensorFlow. Using feedforward neural network, we were able to create a training algorithm which would take in input as a statement or question from user and would come up with an appropriate response on its own. The responses are selected by the algorithm from our JSON (JavaScript Object Notation) file of responses. <br/>
## Proposed Method 
![flow_chart](/img/flowchart.png "Proposed_flow_chart")

### a) Training Data
Since this is a simple chatbot we don't need any massive datasets. We will just use data that we write ourselves. We used a .JSON file to write a data
The data is structured into tags, patterns, responses, and context.
•	**Tags:** Possible classes of user intention for asking a question.
•	**Patterns:** The ways in which users usually ask questions relating to a particular tag.
•	**Responses:** Predefined responses for each tag in the dataset from which the model can choose to respond to a particular question.
•	**Context:** Contextual words relating to a tag for easy and better classification of what the user intends with their request.

With the four data heads explained above in an intent.json file, we can train a chatbot to suit our particular use case.

### b)	Loading our JSON Data
Importing some modules and loading in our json data
Imported NLTK (Natural Language Toolkit) for ***NLP (Natural Language Processing)***. This toolkit is one of the most powerful NLP libraries which contains packages to make machines understand human language and reply to it with an appropriate response.
### c) Extracting Data
We need all the patterns and which class/tag they belong to. We also want a list of all the unique words in our patterns.

### d)	Word Stemming
Stemming a word is attempting to find the root of the word. For example, the word "that’s" stem might be "that" and the word "happening" would have the stem of "happen". We will use this process of stemming words to reduce the vocabulary of our model and attempt to find the more general meaning behind sentences.
![stemmed_word](/img/stemmed_word_example.png "Stemmed_word_example")
For word stemming we used the ***Lancaster Stemmer Algorithm***. Lancaster Stemmer is the most aggressive stemming algorithm used for stemming. While using this stemmer in NLTK we can add our own custom rules very easily to this algorithm

### e)	Bag of Words

**Neural Networks** and **Machine Learning Algorithm** require numerical input so we can’t use our list of strings. Bag of words model is used to pre-process the text by converting it into a bag of words, which keeps a count of the total occurrences of most frequently used words. What we are going to do is represent each sentence with a list the length of the number of words in our model’s vocabulary. Each position in the list will represent a word from our vocabulary. If the position in the list is a 1 then that will mean that the word exists in our sentence, if it is a 0 then the word is not present. We call this a bag of words because the order in which the words appear in the sentence is lost, we only know the presence of words in our model’s vocabulary. As well as formatting our input we need to format our output to make sense to the neural network. Similarly, to a bag of words we will create output lists which are the length of the number of labels/tags we have in our dataset. Each position in the list will represent one distinct label/tag, a 1 in any of those positions will show which label/tag is represented.

### f)	Developing a Model
For our purpose we have used a ***standard feed-forward neural network*** with two hidden layers. Each of the hidden layer has 10 nodes. The goal of our network will be to look at a bag of words and give a class that they belong too (one of our tags from the JSON file).
### g)	Training and Saving the Model
To do these we will fit our data to the model. The number of epochs we set is the number of times that the model will see the same information while training.
We have set ***epochs as 1000***.

### h)	Making Predictions
Ideally, we want to generate a response to any sentence the user types of in. To do this we need to remember that our model does not take string input, it takes a bag of words. We also need to realize that our model does not spit out sentences, it generates a list of probabilities for all our classes. This makes the process to generate a response look like the following: – Get some input from the user – Convert it to a bag of words – Get a prediction from the model – Find the most probable class – Pick a response from that class

***Steps to run the project:***
1. Take Chatbot.ipynb file and open it with google colab
2. Run each shell one by one and upload [Intents_file](https://github.com/deependra278/ChatBot-using-Tensorflow-and-Neural-Network/blob/bcd7a0bbc88f76937901910d7c2065ef5ba76262/intents.json) file when asked.
3. Train the model using neural network
4. Check response using [Demo_output] [Demo_output.mp4](https://github.com/deependra278/ChatBot-using-Tensorflow-and-Neural-Network/blob/bcd7a0bbc88f76937901910d7c2065ef5ba76262/Demo_output.mp4)
5. ***Enjoy***



