# Head Pose Classification and Isolated Word Recognition with Vibration of Vocal Folds while Talking
___________________________________________________
## Project Overview
* Accumulated audio voices of Isolated Japanese words and head positions from both male and female using Throat microphone
* Labelled the audio with head positions
* Performed Resampling and normalization as a preprocessing
* Both speech recognition and head positions classification are performed by using the vibration of speech signals recorded by Throat Microphone
* CNN is used for classification
* Python 3.6 and Tensorflow 2
* Programming Language - Python
___________________________________________________________
## Environment Setup
* PyCharm Community Edition
* Python 3.6 
* Tensorflow 2.0
* Keras
* Sklearn
___________________________________________________________________________________________________
## Hardware Requirement
* Throat Microphone
_____________________________________________________________________________
## System Block Diagram
![image](https://user-images.githubusercontent.com/50255936/110509448-13cb2280-813d-11eb-9de4-070e87ff324d.png)
__________________________________________________________
## Working Procedures
* Audio Signals with different head postions were recorded using throat mircrophone and labelled them (Male voices ('asa', 'hiru', 'yoru') and Female voices( 'ichi', 'go', 'roku') are recorded)
* Pre - processing was performed by re-sampling and normalization
* Output labels were converted to integer encoded and then these encoded labels are converted to a one - hot vecotor
* 2D array was reshaped to 3D array before introduced into CNN network
* The data is split into 80% for training and 20% for validation

## Training Model Architecture
![image](https://user-images.githubusercontent.com/50255936/110511002-bcc64d00-813e-11eb-811b-13c7d80a49bb.png)

* Convolutional 1D was used to build both the speech recognition model and head postion classification model
* The model was implemented using Keras
* There are altogether 4 convoulutional layers with different numbers of filters and kernel size and relu is used as activation function
* After 4 convolutional layers, there is a flatten layer and the output from flatten layer goes into the two dense layers where activation function is also relu function.
* Sofmax is used as the activation in the output layer. 
* Categorical cross-entropy is used as the loss function because this is a multi-classification problem.
* Adam optimizer is used.
* For the wave files with the male voice, the model is trained on a batch size of 32 while for the wave files with the female voice, the model is trained on a batch size of 8.
* After the speech recognition model and head position model are trained, the best models were saved and used in prediction.

## Validation Results
### Speech Recognition ('asa', 'hiru', 'yoru')
![image](https://user-images.githubusercontent.com/50255936/110512552-4296c800-8140-11eb-9831-d66c61913b70.png)
### Head Position Classification ('asa','hiru','yoru')
![image](https://user-images.githubusercontent.com/50255936/110512608-517d7a80-8140-11eb-9c15-4920972d5429.png)
### Speech Recognition ('ichi','go','roku')
![image](https://user-images.githubusercontent.com/50255936/110513574-57279000-8141-11eb-95c2-05106a40be2a.png)
### Head Position Classification ('ichi','go','roku')
![image](https://user-images.githubusercontent.com/50255936/110513653-6dcde700-8141-11eb-8281-c970983eddb3.png)
_____________________________________________________________________________________________________________________________________________________________________
## Real Time Recognition Accuracy ('asa','hiru','yoru')
![image](https://user-images.githubusercontent.com/50255936/110513014-b8029880-8140-11eb-92f1-d9aac89ea026.png)

## Real Time Recognition Accuracy ('ichi','go','roku')
![image](https://user-images.githubusercontent.com/50255936/110514035-d4eb9b80-8141-11eb-966f-e48e929d5502.png)
______________________________________________________________________________________________________________________________
## Conclusions
In conclusion, speech recognition using Throat microphone is robust to noisy environment.Syllable, which has the same variation or intonation, has low accuracy. Head position classification using speech has lower accuracy.
_________________________________________________________________________
## Discussions
It will be possible if the cracking sounds of bones while turning head when speaking are used to recognize head's positions using speech. Two channel microphone will be needed instead of one channel throat microphone. If the throat microphone only is used, large data-sets are required because the vibration signal is recorded by using throat microphone and the vibration tones change according to the emotions and the position where the throat microphone is placed.
