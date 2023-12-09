# Lyrics Generating RNN

## Overview
In this project, we were tasked with building an RNN-based model that is trained on songs' lyrics and MIDI data of the songs' music. The goal is to create a model that given a seed word, and MIDI data will generate the rest of the lyrics for that song.

## Preprocessing
The preprocessing had two main parts, Lyrics handling and MIDI data. Punctuations were removed from the lyrics before they were tokenized. Each song has MIDI data, so I extracted features from the MIDI file and feature-engineered some more custom features so each sample had tokenized lyrics and a set of unique MIDI features. Eventually, using a word2vec model each word from the lyrics of a given song was represented in an embeddings vector that was concatenated with the MIDI features - resulting in a 305 entries vector.

## Training
The model was trained for 25 epochs, using the following architecture:
 - (gru_I): GRU(305, 1024, batch_first=True)
 - (gru_II): GRU(1024, 1024, batch_first=True)
 - (dropout): Dropout(p=0.3, inplace=False)
 - (linear_I): Linear(in_features=1024, out_features=1024, bias=True)
 - (linear_II): Linear(in_features=1024, out_features=6690, bias=True)

![image](https://github.com/AlonSchneider27/lyrics-generating-RNN/assets/99593061/62bf846e-a162-4540-b4a6-b427630c45c5)
