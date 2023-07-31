# Nlp-Project-T5-transformer-for-translation-paragraphs


Description of experiments that you carried out the work on the project -
First, we decided that we are looking to use one of the existing t5 models in hugging face because we saw that given a fine tune relevant to the translation tasks, the adapted model produces quality results. After that, we tried to learn the nature of the model by running the t5-small model with different parameters in the trainer to understand what affects the training and increases the performance. Also, all kinds of prefixes can be used for the tokenization of the information and therefore we have tested several options to find the best quality prefix for the task of translating German to English, among them translate German to English, translate and more. Furthermore, after the lectures, we saw that it is important to preprocess with and without modifiers and roots and the way the dataset is produced with which training is performed for fitting the t5 model.
As part of the tests we performed, we saw different settings regarding the tokenization of the sentence size, adding padding, different learning rates, etc. and we also saw dramatic effects on the capabilities of the model after training.
All these were taken into account after many lectures which finally brought us to the final and most successful model to create.
Description of the algorithm you used to train the model and label the val file -
Since we receive for the non-modifying files and roots for the translated sentence, we used the spacy library and in it ben_core_web_sm in order to find roots and modifiers for the English sentence on the training and with this we chose to train the model with an input prefix containing what
":> translate <modifiers - english_Modifiers roots - '+ english_roots" followed by the sentence in German and the target is the sentence in English, since we used space we could not use the map on
￼￼
Huggingface's data set to make the tokenizer and for that we created the My_Dataset class inside it we used batch_encode_plus in the tokenizer with the possible functions for the trainer, in order to train the model we used the t5-base model which we fine-tuned with the Lang input and focus as described for the translation task from German. After the training phase, in order to label the val file, we did a preprocess similar to what was described, only that the val.unlabeled file was not labeled, so we received the changes and roots together with them. A sentence with model.generate with 8 beams and we output the predicted sentence without special tokens
The percentage of accuracy obtained on the file val - percentage of accuracy according to the bleu index - 43.5
Description of experiments you performed to improve the results in the competition -
We used the same tools from the non-competitive model and labeling
Description of the algorithm you used to train the competitive model and label the comp file -
We used the same tools from the non-competitive model and labeling
The percentage of accuracy according to the expected bleu index is -43.5
An explanation of the division of labor between the two members of the group -
We built the model construction, the training function and the basic processing together, then the hyperparameter test, options for the tokenizer of the t5 models of various kinds (that is, those that are improvements of t5), etc. Since each such test takes a lot of time, everyone performed it separately and we chose the ones that led to the best results. most
Drive link for the model:
https://drive.google.com/drive/folders/1mswrj_mYaWtrDKQVvs8Vqg6yFWVmNbrY?usp=sharing
