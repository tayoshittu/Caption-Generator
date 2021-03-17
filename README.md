# Caption-Generator

This Project generates a caption for a given image using RNNs and Long Short Term Memory Network (LSTM).

Completing this project gave me understanding in the principles of text pre-processing and text embeddings, experience working with an image to text model and the opportunity to perform comparative analysis between **RNNs** and **LSTMs** as sequence generators.

This project was implemented using Python and PyTorch and the data used was the Flickr8k image caption Dataset

![sampleimageGroundtruthCaptions](https://user-images.githubusercontent.com/36918009/111329399-65107000-866f-11eb-9712-f70601e2a797.png)

**Data**

Zip files containing the image data and text data can be downloaded here
https://github.com/jbrownlee/Datasets/releases/tag/Flickr8k

**Text Preparation**
 
 - A Vocabulary was built consisting of all possible words which could be used both as the input and output of the model. 
  - The image ID was split from the caption text
 
 - The caption text was split into words and every trailing whitespace was removed
 
 - Words were converted into lowercase using the *word.lower()* function
 
 - All punctuations like commas, periods were removed
 
 - Words that appeared 3 times or less were removed since the vocabulary size affects the embedding  layer dimensions
 - Remaining words were added to an instance of the *Vocabulary()*

**Evaluation**

BLEU is used to evaluate the model by comparing the generated text to the referenced text. The *sentence_bleu()* function is part of the python ntlk package.

**Training Using RNN decoder**
- RNN layer was added to the decoder and *batch_first* was set to true
- The training loop generates a sample caption from to test set image before any training and after each opoch.
- Both sample images and reference captions, generated captions and its BLUE score are displayed after every epoch.
- it was Trainned for 5 epochs

**Training Using LSTM decoder**
- The RNN layer was replaced with an LSTM layer
- Keeping everything else the same as with the RNN encoder training




