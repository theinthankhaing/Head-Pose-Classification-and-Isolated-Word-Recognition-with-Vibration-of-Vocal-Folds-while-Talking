# Head-Pose-Classification-and-Isolated-Word-Recognition-with-Vibration-of-Vocal-Folds-while-Talking
___________________________________________________
## Project Overview
* Accumulated audio voices of Isolated Japanese words and head positions from both male and female using Throat microphone
* Labelled the audio with head postions
* Performed Resampling and normalization as a preprocessing
* Both speech recognition and head postion classification are performed by using the vibration of speech signals recorded by Throat Microphone
* CNN is used for classification
* Python 3.6 and Tensorflow 2
___________________________________________________________
## Environment Setup
* PyCharm Community Edition
* Python 3.6 
* Tensorflow 2.0
* Keras
___________________________________________________________________________________________________
## Hardware Requirement
* Throat Microphone
_____________________________________________________________________________
## System Block Diagram
![image](https://user-images.githubusercontent.com/50255936/110509448-13cb2280-813d-11eb-9de4-070e87ff324d.png)
__________________________________________________________
## Working Procedures
* Audio Signals with different head postions were recorded using throat mircrophone and labelled them ('asa', 'hiru', 'yoru', 'ichi', 'go' and 'roku' words are recorded)
* Pre - processing was performed by re-sampling and normalization
* Output labels were converted to integer encoded and then these encoded labels are converted to a one - hot vecotor
* 2D array was reshaped to 3D array before introduced into CNN network
* The data is split into 80% for training and 20% for validation

### Training Model Architecture
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
