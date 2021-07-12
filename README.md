
# HAND SIGN PREDICTIONS USING TENSORFLOW OBJECT DETECTION

## Acknowledgements

I take this opportunity to express my sincere thanks to Mr. Nicholas Renotte, his work on hand sign detection using tensorflow was a great help for me in making my own project and bring it to a level where it can be used to make sentences.
This project was an amazing journey of learning and I have enclosed some of the links which have helped me during my journey to make this project.
- [Nicholas Renotte](https://github.com/nicknochnack)
- [Label Image](https://github.com/tzutalin/labelImg)
- [SSD Mobilenet](https://medium.com/@techmayank2000/object-detection-using-ssd-mobilenetv2-using-tensorflow-api-can-detect-any-single-class-from-31a31bbd0691)
- [ASL(American Sign Language)](https://www.nidcd.nih.gov/health/american-sign-language#:~:text=American%20Sign%20Language%20(ASL)%20is,grammar%20that%20differs%20from%20English.&text=It%20is%20the%20primary%20language,many%20hearing%20people%20as%20well.)
- [Tensorflow Model Garden](https://github.com/tensorflow/models)
- [Tensorflow Records](https://github.com/nicknochnack/GenerateTFRecord)


## Inspiration and Overview

Mute people often come across scenarios where they face a huge gap while communication with normal people. There are some stae of the art models availabe which have taken an approach on this problem by using <a href="https://www.mdpi.com/1424-8220/19/24/5429/htm">3DCNN and LSTM with FSM Context-Aware Model</a> and many more.<br>
The general concept is that a number of CNN layers are used followed by a number of LSTM layers, use of a pretrained mobile net followed by a number of LSTM layers. These models end up requiring large amounts of data to produce good results and also demand very high compute power due to presence of 30 to 40 million parameters.

## Minimum Requirements
1) RAM : 8 GB and above
2) Disk Space : 2 GB is the approx size of the repository
3) Processor : i3  and above in 10th gen (for anything less than 10th Gen minimum Intel i5 is required)
4) GPU : Its good to have one.
5) CUDA and CUDNN : If GPU is available

## Setup Process
<br />
<b>Step 1.</b> Clone this repository: <a href = "https://github.com/VaibhavSaran/Hand-Sign-Detection-with-Tensorflow-Object-Detection">Hand Sign Prediction</a>.
<br/><br/>
<b>Step 2.</b> Create a new virtual environment 
<pre>
python -m venv tfod
</pre> 
<br/>
<b>Step 3.</b> Activate your virtual environment
<pre>
source tfod/bin/activate # Linux
.\tfod\Scripts\activate # Windows 
</pre>
<br/>
<b>Step 4.</b> Install dependencies and add virtual environment to the Python Kernel
<pre>
python -m pip install --upgrade pip
pip install ipykernel
python -m ipykernel install --user --name=tfodj
</pre>
<br/>
<b>Step 5.</b> Run Jupyter Notebook or Jupyter Lab which ever is available. Run the command : 
<pre>
Jupyter Notebook # To run Jupyter Notebook 
 # or run the below to launch Jupyter Lab
Jupyter Lab
</pre>
Error: If the above command is not recognized then try installing the module with command. Anyone will do or both can be done.
<pre>
pip install jupyterlab # To install Jupyter Lab
pip install jupyter # To install Jupyter Notebook
</pre>
<br/>
<b>Step 6.</b> After launching Jupyter make sure to select the kernel to the virtual environment.
<img src="https://i.imgur.com/8yac6Xl.png">
<br/>
<b>Step 7.</b> First run the notebook **Dependencies.ipynb**, it will install all the requisite libraries for your system. However do check which version of tensorflow you are installing and the corresponding CUDA and cuDNN libraries.

## Executing Project
Run all the cells of the notebook **Generating Labelled Data.ipynb** if you want to create your own data and train the model on it. If not you can use the pretrained model available . The model has been saved and is available as **models.tar.gz**. While executing the project if there are any refers do try checking out **Common Errors.md** there is a good chance your error is already covered there.

## Data Collection
For this project I have not used any data from any 3rd party source/company. I went and created my own data by taking pictures of myself performing the signs and then adding labels in each and every image. There are 10 labels used in this project namely ok, notok, thankyou, livelong, name, what, you, iloveyou, nice, love. Per class 30 images have been collected which makes a total of 300 images and then the data has been split 240 images to train and 60 images to test the model. The model itself has been trained for 10000 steps.

## Working Summary of Project
1) Installing all the dependecies.
2) Defining labels to be collected and collecting data for each label.
3) Use labelimg to label data and split the data into test and train.
4) Training the model [SSD MobileNet V2 FPNLite 320x320](http://download.tensorflow.org/models/object_detection/tf2/20200711/ssd_mobilenet_v2_fpnlite_320x320_coco17_tpu-8.tar.gz)
5) Performing real time detections and detection on image.
6) Freezing the graph and saving the model.

## Results Achieved
1) After training the model for 10000 steps.
<img src="https://i.imgur.com/T77mIGY.jpg">
<br>
2) Model evalutaion.
<img src="https://i.imgur.com/wfMxpD8.jpg">
3) Graph for Learning Rate and Losses.
<img src="https://i.imgur.com/uIfRZu1.jpg">
<img src="https://i.imgur.com/43ByVlI.jpg">

## Future Scope and Improvements
1) Adding more data to perform better predictions.
2) Adding more signs for recognition.
3) Integrating with ASL alphabets so that basic conversation can take place using this model.
4) It can be used to develop a Robot to recognize these hand signs. These robots can then be deployed at Airports and railway stations which can help in easing the communication between mute people and authorities.
5) Using some other SOTA architectures which can enable to detect motion signs like 3DCNN or maybe use MediaPipe with LSTM.
