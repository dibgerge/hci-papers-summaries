# Detection of subconscious face recognition using consumer-grade brain-computer interfaces

* **Authors**: M V Martin, V Cho, and G Aversano
* **Journal**: ACM Transactions on Applied Perception, Vol. 14, Article 7
* **Publication Date**: 2016

This article investigates the ability to use EEG signal to detect if a subject recognizes pictures of famous people subconciously or does not recognize the picture at all. One of the interesting aspects of this paper is the way they designed their experiments.

A total of 19 subjects were used in the experiments. For each subject, experiments were conducted in two phases as follows:
- In phase 1 (used for training data), 30 famous people and 10 photos per person (300 total) were shown,
- In phase 2 (used for test data), 60 famous people and 10 photos per person (600 total) were shown,
- Photos were shown at a rate of 1 second,
- A 1 minute rest was given between the two phases phases,
- Subject could rest anytime during the experiment by hitting any letter key on the keyboard,
- Subject hit space bar if they recognized the photo.
- At end of experiment a questionaire was given to subjects to verify if they recognize each of the 90 famous people. All 10 pictures of the famous person were shown in the questionaire, along with an introduction paragraph from wikipedia.

Once all is done, the following table was used to label the EEG data:

| Outcome | Recognition in experiment | No recognition in experiment |
|-        |-                          |-
| Recognition in exit questionaire | Conscious recognition (CR) | Possible subconscious recognition (PSR)
| No recognition in exit questionaire | False recognition (FR) | Possible no recognition (PNR)

### Data Processing

- Only data corresponding to no recognition and subconscious recognition was kept.
- If subject recongnized a famous person less than 8/10 times, it is assumed that there is no recognition and data is dropped.
- Band-pass filter between 0.1 Hz and 15 Hz is applied to all channels.
- If a channel voltage goes above $\pm 50 \mu V$, the channel is dropped (assumed large signal due to blinks/head movement).


### Other remarks

- Authors used SVM for classification. They only used per-subject classification, and did not attempt to use inter-subject classification.

- Within the 1000 ms in which an image is shown, SVM was trained on many different epochs, based on literature describing when VEP (visually evoked potential) will appear. A total of 9 different time intervals were investigated.

- Only about 65% accuracy was acheived, and accuracy varies greatly between subjects (from 50 % up to 90%). <font color='red'>This is misleading, because subjects with higher accuracies had more imbalanced datasets! </font>

- In general, F-scores for all subjects were below 0.5, indicating that there is not much value in the detection...