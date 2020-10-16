# Speech Emotion Recognition

The human speech emotion classification model is built using the MFCC (Mel Frequency Cepstral Coefficients) to train a CNN model and yields 
basic emotions such as calm, happy, sad, fear, angry, neutral 

## Datasets Used
### RAVDESS

RAVDESS is one of the most commonly used dataset which has audio recordings of 24 actors of different genders. The filename identifiers as per 
the official RAVDESS website:

Modality (01 = full-AV, 02 = video-only, 03 = audio-only).
Vocal channel (01 = speech, 02 = song).
Emotion (01 = neutral, 02 = calm, 03 = happy, 04 = sad, 05 = angry, 06 = fearful, 07 = disgust, 08 = surprised).
Emotional intensity (01 = normal, 02 = strong). 
Statement (01 = "Kids are talking by the door", 02 = "Dogs are sitting by the door").
Repetition (01 = 1st repetition, 02 = 2nd repetition).
Actor (01 to 24. Odd numbered actors are male, even numbered actors are female).

### SAVEE

The audio files are named in such a way that the prefix letters describes the emotion classes as follows:

'a' = 'anger'
'd' = 'disgust'
'f' = 'fear'
'h' = 'happiness'
'n' = 'neutral'
'sa' = 'sadness'
'su' = 'surprise'

### TESS 

It's only based on 2 speakers, a young female and an older female. This will balance out the male dominant speakers that is present in the 
SAVEE dataset.

### CREMA

CREMA has a good variety of different speakers, apparently taken from movies. And the speakers are of different ethnicities.Thus this dataset
is diverse.

Sample audio file format: 1012_IEO_HAP_HI.wav, 1001_DFA_DIS_XX.wav

## Feature Analysis

![time-frequency](https://user-images.githubusercontent.com/58515646/96236632-eaf19780-0fb9-11eb-832f-18b7646c13ed.jpeg)

there are two category of features:

### Time domain features
These are simpler to extract and understand, like the energy of signal, zero crossing rate, maximum amplitude, minimum energy, etc.
### Frequency based features
Theses are obtained by converting the time based signal into the frequency domain. Whilst they are harder to comprehend, it provides extra 
information that can be really handy such as pitch, rhythms, melody etc

## Model

Data processing is the most important step before building a model. After basic preprocessing, the data is split into 2 parts, one for 
training and one for validation. This ensures we measure the model's performance at its true accuracy. Data normalisation is done as multiple 
datasets are combined together as one.

A 2D CNN model is built with 14 target class numbers and the model is trained for 100 epochs to attain a nominal accuracy of 70%.
### CNN layer visualization


![model](https://user-images.githubusercontent.com/58515646/96239090-e37fbd80-0fbc-11eb-8aeb-bf5dbb49cec7.jpeg)

## Serialization and Validation

The model with utmost accuracy are serialised and the weights are saved. On reloading the saved model, the predictions are made on the 
test dataset. The prediction in the form of numbers are labelled and saved in the #### Predictions.csv file.

## Prediction

![prediction](https://user-images.githubusercontent.com/58515646/96239972-f646c200-0fbd-11eb-99ff-095c08d5c3ec.jpeg)


