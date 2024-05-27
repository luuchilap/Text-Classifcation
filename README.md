This project uses Neural Network to classify whether a comment from clients is positive or negative. The steps can be summarized as follows:
Data Preparation
1.	Download and Extract Dataset:
o	Clone the GitHub repository containing the dataset.
o	Extract the training and test datasets from the downloaded ZIP files.
2.	Load Data:
o	Define a function to load data from the extracted folder paths.
o	Read the content of each file, combine the lines into a single sentence, and label it as positive (1) or negative (0).
o	Create DataFrames for training, validation, and test sets.
Language Identification and Filtering
3.	Language Identification:
o	Install the langid library for language identification.
o	Use the LanguageIdentifier to classify the language of each sentence in the DataFrame.
o	Filter out sentences that are not classified as Vietnamese (vi) with a high confidence score.
Text Preprocessing
4.	Text Preprocessing:
o	Define a function to preprocess text by:
	Removing URLs, HTML tags, punctuation, digits, and emojis.
	Converting text to lowercase.
o	Apply the preprocessing function to the sentences in the training, validation, and test DataFrames.
Tokenization and Vocabulary Building
5.	Tokenization:
o	Use the basic_english tokenizer from torchtext.data.utils to tokenize sentences.
o	Define a function to yield tokens from the preprocessed sentences.
6.	Build Vocabulary:
o	Build a vocabulary from the tokenized sentences, limiting the vocabulary size to 10,000 tokens.
o	Set the default index for unknown tokens.
Dataset Preparation
7.	Prepare Dataset:
o	Define a function to encode sentences using the built vocabulary and pair them with their labels.
o	Convert the encoded sentences and labels into a map-style dataset compatible with PyTorch's DataLoader.
8.	DataLoader:
o	Define a custom collate function to handle batches of varying sentence lengths.
o	Create DataLoaders for the training and validation datasets.
Model Definition
9.	Text Classification Model:
o	Define a simple text classification model using an embedding bag and a linear layer.
Training and Evaluation
10.	Training Loop:
o	Define a training function to:
	Train the model for a specified number of epochs.
	Compute and print training accuracy and loss at regular intervals.
11.	Evaluation Function:
o	Define an evaluation function to compute accuracy and loss on the validation dataset.
12.	Train the Model:
o	Set training parameters such as learning rate, number of epochs, and criterion.
o	Train the model using the defined training loop and evaluate its performance after each epoch.
Prediction and Testing
13.	Prediction Function:
o	Define a function to predict the sentiment of a given sentence using the trained model.
14.	Test Accuracy:
o	Use the prediction function to compute accuracy on the test dataset.

