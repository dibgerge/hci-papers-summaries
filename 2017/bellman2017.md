# Use of Machine Learning for Detection of Unaware Facial Recognition Without Individual Training
* **Authors**: C Bellman, MV Martin
* **Conference**: 16th IEEE International Conference on Machine Learning and Applications
* **Publication date**: 2017

- This paper attempts to differentiate between fully-aware (conscious) recognition from the unaware (subconscious) recognition.
- An experiment was conducted over the course of two days. 
- Data was taken from the FERET database (face recognition technology).
- Total of 43 participants. 6 out of the 43 participants had bad data, and were not considered.

**Day 1**

- Considered as a training session (not yet clear if this means that the data collected was used for training the classifier).
- Total of 162 images used.
- 20 images shows as UR (unaware recognition). Repeated 3 times each.
- Each image shown for 1 second, followed by a blank screen for one second.

**Day 2**

- Total of 102 images shown to each participant.
- Phase 1: 10 images out of the 20 images shown the previous day were spaced envenly among 92 filler images. 
- Phase 2: Shown a single pre-selected image and subject asked to memorize it for aware recognition (AR). Then, participants asked to search for face shown to them from a number of images. The image was shown a total of 20 times. Other 10 UR images were also shown among 72 filler images.

### Data Pre-processing
 - Now we have a dataset with two labels (UR/AR). 
 - 0.5 - 12 Hz bandpass filter
 - ICA 
 - All data was concatenated and had a size of 122 samples (almost 1 second)
 - Remove features within the lowest 80% of variance, resulting in **24 features for classification**.
 
 
### Classification 
 
 - They used a 3 layer multi-layer perceptron and data was split into 80/20 for train/validate. 
 - Cross-validation to determine parameters (mostly hidden layer sizes).
 - Achieved 0.71 F-score. 
 