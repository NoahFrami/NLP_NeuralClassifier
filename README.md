# Neural Network Sentiment Classifier

A simple neural network sentiment classifier built with Python and PyTorch. This project demonstrates how a neural network can process text, convert words into numerical representations, and classify sentences as either positive or negative.

## Project Overview

The goal of this project is to understand the basic steps involved in building a neural network for Natural Language Processing (NLP).

The classifier is trained on a small sample dataset containing positive and negative movie-related sentences. The model learns patterns from the training examples and then uses those patterns to predict the sentiment of new sentences.

### Sentiment Classes

* `1` = Positive
* `0` = Negative

## Technologies Used

* Python
* PyTorch
* PyTorch Neural Networks
* Natural Language Processing (NLP)

## How It Works

The project processes text through several steps:

1. **Tokenization**

   * Converts text to lowercase.
   * Splits sentences into individual words.

2. **Vocabulary Building**

   * Creates a dictionary that assigns a numerical index to each word.
   * Uses `<PAD>` for padding shorter sentences.
   * Uses `<UNK>` for words that are not in the vocabulary.

3. **Text Encoding**

   * Converts words into numerical indices that the neural network can process.

4. **Padding**

   * Makes all sentences the same length so they can be processed together.

5. **Embedding Layer**

   * Converts word indices into numerical vectors.
   * These vectors allow the neural network to work with word representations.

6. **Mean Pooling**

   * Combines the word vectors into one representation of the sentence.

7. **Hidden Layer**

   * Processes the sentence representation and learns patterns from the training data.

8. **ReLU Activation**

   * Adds a non-linear activation function to the network.

9. **Output Layer**

   * Produces scores for the positive and negative classes.

10. **Softmax**

    * Converts the output scores into probabilities.

11. **Prediction**

    * The class with the highest probability becomes the predicted sentiment.
    * The model also provides a confidence score.

## Model Architecture

The neural network follows this basic structure:

```text
Input Text
    ↓
Tokenization
    ↓
Word Indices
    ↓
Embedding Layer
    ↓
Mean Pooling
    ↓
Hidden Layer
    ↓
ReLU
    ↓
Output Layer
    ↓
Softmax
    ↓
Positive / Negative
```

## Example Dataset

The model is trained using a small dataset such as:

```text
"I love this movie"       → Positive
"This is amazing"         → Positive
"I hate this"             → Negative
"This is terrible"        → Negative
"I really enjoyed this"   → Positive
"This was awful"          → Negative
```

## Training

The model uses:

* **Embedding Dimension:** 10
* **Hidden Layer Size:** 8
* **Output Classes:** 2
* **Learning Rate:** 0.01
* **Training Epochs:** 50
* **Loss Function:** Cross Entropy Loss
* **Optimizer:** Adam

During training, the model makes predictions, calculates its error, uses backpropagation to calculate gradients, and updates its weights.

## Example Predictions

After training, the program tests sentences such as:

```text
"I love this"
"This is bad"
"I do not like this"
"This was amazing"
"This was terrible"
```

The program displays:

* The original sentence
* Predicted sentiment
* Confidence score
* Probability for each class

Example output:

```text
Text: I love this
Prediction: positive
Confidence: 0.9500
Probabilities: [[0.0500, 0.9500]]
```

*The exact results may change each time the neural network is trained because the model starts with randomly initialized weights.*

## Project Structure

```text
NLP_NeuralClassifier/
│
├── neural_sentiment.py
└── README.md
```

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/NLP_NeuralClassifier.git
```

### 2. Open the project

Open the project in PyCharm or another Python IDE.

### 3. Install the required packages

```bash
pip install torch numpy
```

### 4. Run the program

```bash
python neural_sentiment.py
```

## What I Learned

This project helped me understand how neural networks can be used for NLP tasks. I learned how text can be converted into numerical data, how embedding layers represent words as vectors, and how a neural network can learn patterns from training data.

I also learned how training works using a loss function, backpropagation, and an optimizer. The project gave me hands-on experience building and testing a basic NLP classification model with PyTorch.

## Limitations

This project uses a very small training dataset, so it is mainly intended as a learning project rather than a production-ready sentiment classifier.

Because the vocabulary is built only from the training data, new words that were not seen during training are represented using the `<UNK>` token.

A larger and more diverse dataset would be needed to improve the model's ability to generalize to real-world text.

## Future Improvements

Possible improvements include:

* Train the model using a larger dataset.
* Add more positive and negative examples.
* Improve text preprocessing.
* Add punctuation handling.
* Use a larger embedding dimension.
* Experiment with different neural network architectures.
* Add validation and test datasets.
* Compare the neural network with other machine learning models.

## Author

**Noah Frami**

This project was created as part of my coursework and portfolio development in Natural Language Processing and machine learning.
