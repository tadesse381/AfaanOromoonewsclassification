# AfaanOromoonewsclassification
## Methodology
In this work we proposed to classify Afaan Oromoo news using Long Short Term Memory(LSTM). Long short-term memory (LSTM) is a deep learning architecture based on an artificial recurrent neural network (RNN). These are special types of neural networks which are designed to work well when one has sequence data set and there exists a long term dependency. These networks can be useful when one needs a network to remember information for a longer period. This feature makes LSTM suitable for processing textual data. Fig. 1 shows a typical architecture of an LSTM. As it can be seen in the diagram, an LSTM is a collection of similar cells, whereas each cell processes the input in a specific approach. Apart from the input from external sources, each cell also receives inputs from its earlier cell in the chain. This arrangement of cells, facilitates LSTM to remember earlier information for a longer time.

![tadesse381/AfaanOromoonewsclassification](data/LSTM.png)

 Fig. 1. Architecture of LSTM
 The LSTM is made up of four neural networks and numerous memory blocks known as cells in a chain structure. A conventional LSTM unit consists of a cell, an input gate, an output gate, and a forget gate. The flow of information into and out of the cell is controlled by three gates, and the cell remembers values over arbitrary time intervals. The LSTM algorithm is well adapted to categorize, analyze, and predict time series of uncertain duration. The cells store information, whereas the gates manipulate memory. There are three entrances:
•	Input Gate: It determines which of the input values should be used to change the memory. The sigmoid function determines whether to allow 0 or 1 values through. And the tanh function assigns weight to the data provided, determining their importance on a scale of -1 to 1.
 
•	Forget Gate: It finds the details that should be removed from the block. It is decided by a sigmoid function. For each number in the cell state Ct-1, it looks at the preceding state (ht-1) and the content input (Xt) and produces a number between 0 (omit this) and 1 (keep this).
 
•	Output Gate: The block’s input and memory are used to determine the output. The sigmoid function determines whether to allow 0 or 1 values through. And the tanh function determines which values are allowed to pass through 0, 1. And the tanh function assigns weight to the values provided, determining their relevance on a scale of -1 to 1 and multiplying it with the sigmoid output.
 
The recurrent neural network uses long short-term memory blocks to provide context for how the software accepts inputs and creates outputs. Because the program uses a structure based on short-term memory processes to build longer-term memory, the unit is dubbed a long short-term memory block. In natural language processing, these systems are extensively used.
To classify the Afaan Oromoo news text to four categories, the model is developed using Long Short Term Memory (LSTM). In the current era, the field of NLP is dominated by Deep Learning based approaches. Text classification is a classic problem in NLP. This problem involves classifying a given piece of text into respective classes. News classification is a task that falls under text classification. LSTM has recently become a popular tool among NLP researchers for their superior ability to model and learn from sequential data. These models have shown state of the art results on various public benchmarks ranging from the classification of sentences and various tagging problems for language modeling and sequence to sequence to sequence prediction.  LSTM is a deep learning algorithm which is prominently used for text classification. LSTM can trace back several states and observe what occurred, resulting in an effect of what will happen in the future. The proposed technique includes: data collection, data preprocessing, build and train models, evaluation and prediction.
A.	Data collection 
In this work, a corpus containing 1078 Afaan Oromoo news topic with its description which is collected by the https://www.masakhane.io, from BBC (British Broadcasting Corporation) news Afaan Oromo, VOA (Voice of America) Afaan Oromo is used. The 1078 Afaan Oromoo news are classified into four classes of news i.e., 110 entertainment, 338 health, 350 politics and 280 sports.
B.	Data Preprocessing
The preprocessing component of Afaan Oromoo news comprises activities such as setting, parameters, encoding, tokenization, padding, and stop word removal. These processes are explained in detail in the following sections. 
First we have set parameters like MAX_NB_WORDS” defines the max number of words for tokenizer, and “MAX_SEQUENCE_LENGTH” defines the max length for our corpus. If any rows of our data does not match this length we are going to add padding on it. Then Unicode encoding is performed. Unicode encoding is changing text data (categorical) into numbers. This applies because this project works with the type of sequence classification and uses deep learning methods, LSTM. Tokenization is the process of breaking up the flow of text into words, phrases, symbols or other meaningful elements called tokens. It is mandatory step before all types of processing. This process will divide the text into sentences and sentences into typographic tokens. The feature is generated from tokenizing is the training data.
Further we have performed padding is carried out to identify the end of sentences because the decoder is trained sentence by sentence. MAX_SEQUENCE_LENGTH for our features are determined here.
C.	LSTM model	
A LSTM was also trained on the data. An input embedding of size 18 was trained on the data with the LSTM model.The LSTM was connected to two fully connected networks. Then a softmax on the output gave the probabilities for different classes. 
Our first layer will be an input layer which takes the max sequence length of our data. Our second layer will be an Embedding layer. We feed our embedding matrix which we’ve created earlier to the embedding layer and set trainable to false. This is because we are using the pre-trained weights vector and we don’t want to train it again. After creating our embedding sequences, it’s time to define the LSTM layer which returns the sequence data. We are also using a GlobalMaxPool layer of 1 dimension and dropouts. Our final layer is a dense layer which is of length 2 because our labels are one-hot vectors of length 2. Generally the model parameters are:
	Batch size=256
	Epochs: 25
	Optimizer: Adam
	Embedding dimension: 256
	Activation: softmax
	Droupout:0.25
After compiling our model using the above parameters we have trained our model using 25 epochs because using more epochs resulted in overfitting. The accuracy of the model is evaluated using confusion matrix.
## Experimental result and Discussion
The experimentation is performed using LSTM algorithm to classify the news into four classes. In this the developed model classifies the news according its category entertainment, health, politics and sport based on the news title. The 90% of data used for training and for 10% data is used for testing purpose. Based on the trained LSTM model the news classified according to its categories based on the topic or titles of the news. When the new data is entered this model predicts the Afaan Oromoo news text to the matched classes. This model classifies the news titles with the accuracy of 72.1%. 
Sample of the predicted news are given in the following figure.
 
## Conclusion
In this work, we’ve trained our simple LSTM model to classify Afaan Oromoo news dataset into four categories: entertainment, health, sports and politics and got an accuracy of 72.1%. The result of this work is promising. In the future work, we will train the model with more corpus and further increase model size, tweak the hyperparameters, use another deep learning algorithms and test if the model performs better. 
## Contributors

1. [Maraf Mengesha](https://github.com/Maraf26)
2. [Tadesse Kebede](https://github.com/tadesse381)

