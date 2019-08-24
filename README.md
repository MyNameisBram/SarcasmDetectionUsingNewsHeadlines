# Detect Sarcasm Using News Headlines

## Abstract

Accroding to [Smithsonian.com](https://www.smithsonianmag.com/science-nature/the-science-of-sarcasm-yeah-right-25038/)Scientist are finding that the ability to detect sarcasm is extremely useful. Researchers from linguists to pychologists to neurologists have been studying humans ability to perceive sarcasm and gaining new insights into how the mind works. They believe sarcasm detection is an essential skill if one is to function in a modern society. 

The 21st century in America is flooded with sarcasm, and according to one study based on telephone conversations, 23% of the time the phrase "yeah, right" was used, it was used in a sarcastic manner. Another phrase "big deal," phrases like that said in a snarky way has lost its literal meaning. 

We wanted to see if we can train a machine to detect sarcasm by bringing it to the 21st century.


## Summary

We used Natural Language Processing (NLP) and supervised machine learning with in our text classification to detect sarcasm using news headlines. 

The data was sourced from [kaggle](https://www.kaggle.com/rmisra/news-headlines-dataset-for-sarcasm-detection/home)

- Sarcastic news: TheOnion 
- Real: Huffpost 

### Result 
Our Pre-trained RNN  Algorithm received an accuracy of **80%** and we're pretty happy with the outcome since we used the smallest GloVe, pre-trained word embedding from [Stanford NLP group](https://nlp.stanford.edu/projects/glove/). 

Recurrent Neural Network (RNN) 
--- 
**RNNs** are a class of neural networks that allow previous outputs to be used as inputs while having hidden layers. RNNs are used to evaluate ___**Sequences**___ of data, vs. individual data points, where order and time series are important. 

Time series and text data are great examples of sequence data. Time series (stock price), where historical price matters. Text data, where words need to be in proper order for a letter or document to make sense. RNNs excel at NLP tasks because they can take in text as full sequences of words, from a single sentence, up to an entire corpus or book. Because of their ability to sequencing data, they do not lose information that comes from a traditional bag-of-words vectorization approach. 

<img src='unrolled-Copy1.gif'>

Neural Networks typically consists of the below: 
- **Input layer**, takes the input values (features) and passes the information on to the next layer. We define this layer with a max words property, which will only accept a list a words with the set dimension `maxwords= 1000`.
- We then pass our vectors to an **embedding layer**, where we project the words onto a defined vector space, which allows us to reduce model size and reduce dimesionality.
- **Dense layers** or **"Hidden layers"**, are a linear operation where every input is connected to every output by a weight, and generally followed by a non-linear **activation function**, in our case we'll use `relu`.
- To manage overfitting, **Regularization layers** are used. In this layer, we penalise our loss term by adding a L1 (LASSO) or L2 (Ridge),  on the weight vector. Alternatively, we can apply a **dropout layer**, where individual nodes are dropped out of the network to reduce the size of the network.
- Last but not least, the **output layer**. This is last layer in the network and receives its inputs from the last hidden layer. In this layer, we define the number of desired outcome values. In our case only 1 neuron in the output layer. A final **activation function** is used to assign the output neurons the desired values. Generally, we use the sigmoid function because of it's inherent binary results, which is highly beneficial to a classification task. 



