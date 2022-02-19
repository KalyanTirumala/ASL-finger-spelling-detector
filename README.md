# ASL finger spelling detector
### Setup
* Install python packages from `requirements.txt`
* Install node packages from `posenet_nodejs` via `npm install` 
* Change directories in `scale_to_videos.js`
* Model download instructions are available in respective directories
* User videos have to be placed in the following folders:
    * demo/alphabets: for alphabet recognition
    * demo/words: for word recognition

### Project structure
* data/
    * alphabets: A-Z training videos from each team member
    * words: 10 words in videos from each team member
* demo/
    * alphabets: given videos for alphabet recognition
    * words: given videos for alphabet recognition
    * frames: frames extracted from the user videos
    * posenets: pose estimation data extracted from the user videos
* model/
    * cnn_model.h5: trained model for asl recognition from given image
* code/posenet_nodejs
    * scale_to_videos.js: script for pose estimation model 
* code/prediction/
    * ASLpredictor.py: main prediction script
    * alphabet_mode_main.py: utility script for predictions
    * handshape_feature_extractor.py: feature extraction script
    * output_labels_alphabet.txt: labels for alphabet recognition
    * handtracking/: script to detect ROI(region-of-interest) from video
* output/: results generated from prediction files
* requirements.txt: File containing required python packages
* properties.iml: file containing required paths
* archive: contains replaced code for personal dump

### Execution steps
* put videos in `demo/alphabets` or `demo/words`
* navigate to project directory
* `python code/prediction/ASLpredictor.py`
* choose option:
    * A: alphabet recognition
    * B: word recognition
* Results are visible on the terminal and the `output/` directory

### Task list (completed 20/20)
1. [DONE] Use assignment 1 to collect data on all 26 alphabets by each person in the group
2. [DONE] Develop a palm detection algorithm 
    - a. Use Posenet to obtain wrist points [Ask for the posenet interface]
    - b. Develop a cropping algorithm from empirical understanding of the video data
    - c. Validate Palm detection algorithm on the videos collected by you
3. [DONE] Configure a 3D CNN that is trained on the ASL alphabet signs data set in the given link
4. [DONE] Use your own videos to recognize which alphabets were signed [80% re-training, 20% validation]
5. [DONE] Report accuracy F1 score metrics
6. [DONE] Now take 40 different words (each student considers 10 different words) and use the alphabet signs to fingerspell these words
    a. Shoot videos of each of these words using Assignment 1 (4 tasks)
7. [DONE] Use Posenet on each of these videos to develop a keypoint time series
8. [DONE] Develop a segmentation algorithm that separates each alphabet in the word
9. [DONE] Use the same 3D CNN you built to recognize each alphabet in the word
10. [DONE] Develop an algorithm that combines each alphabet recognition result to develop a recognition of a word
11. [DONE] Report the word recognition accuracy

### References
[1] https://github.com/victordibia/handtracking
[2] https://www.kaggle.com/mrgeislinger/asl-rgb-depth-fingerspelling-spelling-it-out