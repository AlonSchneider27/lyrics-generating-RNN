# Lyrics Generating RNN

## Overview
In this project, we were tasked with building an RNN-based model that is trained on songs' lyrics and MIDI data of the songs' music. The goal is to create a model that given a seed word, and MIDI data will generate the rest of the lyrics for that song.

## Preprocessing
The preprocessing had two main parts, Lyrics handling and MIDI data. Punctuations were removed from the lyrics before they were tokenized. Each song has MIDI data, so I extracted features from the MIDI file and feature-engineered some more custom features so each sample had tokenized lyrics and a set of unique MIDI features. Eventually, using a word2vec model each word from the lyrics of a given song was represented in an embeddings vector that was concatenated with the MIDI features - resulting in a 305 entries vector.

## Training
The model was trained for 25 epochs
