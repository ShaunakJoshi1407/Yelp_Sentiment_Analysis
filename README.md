# Yelp Sentiment Analysis Using BERT

## Project Overview

This project focuses on the application of transformer-based architectures, specifically utilizing the BERT (Bidirectional Encoder Representations from Transformers) model, to perform sentiment analysis on Yelp reviews. Our approach enhances the BERT model's ability to understand nuanced expressions of sentiment through strategic modifications.

## Model Architecture

### BERT Model Customization

We utilize a `BERTsmall` model integrated within a custom classifier architecture. The primary configuration involves:
- **Layer Freezing**: The first 8 layers of the BERT model are frozen to preserve the pre-trained contextual embeddings.
- **Fine-Tuning**: The last four layers of the BERT model are fine-tuned to adapt to the sentiment analysis task, allowing updates during the training phase.

### Additional Model Components

- **Fully Connected Layers**: Several fully connected layers follow the BERT output. These layers are dimensioned to transform the BERT output into classifications. Batch normalization is applied after each fully connected layer to stabilize the learning process by normalizing activations.
  
- **Dropout**: To combat overfitting, dropout layers are implemented post each fully connected layer, effectively dropping out a fraction of neurons to enhance generalization.

- **Activation Functions**: The ReLU (Rectified Linear Unit) activation function is used post each fully connected layer, introducing non-linearity into the model, which helps in learning complex data relationships.

## Training Strategy

The model's training involves updating the weights of the last few layers while keeping earlier layers unchanged. This method leverages the pre-trained advantages of BERT while fine-tuning the model to better suit our specific task of sentiment analysis.

## Conclusion

Employing a fine-tuned pre-trained model like BERT for sentiment analysis has proven effective in handling complex, contextualized data inputs. Our modifications aim to enhance this model's sensitivity to the subtle nuances of sentiment expressed in Yelp reviews, promising robust performance in real-world applications.
