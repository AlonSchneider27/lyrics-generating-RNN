# Lyrics Generating RNN

## Overview
In this project, I aimed to build an RNN-based model trained on both the lyrics and MIDI data of various songs. The objective was to create a model that, when given a seed word and MIDI data, generates the remaining lyrics for a song.

## Preprocessing
The preprocessing consisted of two main parts: handling the lyrics and processing the MIDI data. I removed punctuation from the lyrics before tokenization. For each song, I extracted features from its MIDI file and further engineered custom features. This process led to each sample comprising tokenized lyrics paired with a unique set of MIDI features. Ultimately, using a word2vec model, I represented each word from a song's lyrics as an embedding vector. This vector was then concatenated with the MIDI features, resulting in a 305-entry vector for each sample.

## Training
The model was trained over 25 epochs, with the following architecture:
 - (gru_I): GRU(305, 1024, batch_first=True)
 - (gru_II): GRU(1024, 1024, batch_first=True)
 - (dropout): Dropout(p=0.3, inplace=False)
 - (linear_I): Linear(in_features=1024, out_features=1024, bias=True)
 - (linear_II): Linear(in_features=1024, out_features=6690, bias=True)

![image](https://github.com/AlonSchneider27/lyrics-generating-RNN/assets/99593061/62bf846e-a162-4540-b4a6-b427630c45c5)
