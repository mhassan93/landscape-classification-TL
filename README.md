# Landscape Classification
<h3> Transfer Learning on VGG16 model using Keras </h3>

I had a dataset of 6 types of landscape: <b>Buildings, Forest, Glacier, Mountains, Sea, Street</b>

Instead of training a custom model from scratch, I used one of pretrained models available in keras, namely VGG16, pretrained on Imagenet.

<h4><p align="center">Some training samples</p></h4>

<p align="center">
  <img width="150" height="175" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Images/0.jpg'/>
  <img width="150" height="175" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Images/10.jpg'/>
  <img width="150" height="175" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Images/16.jpg'/>
  <img width="150" height="175" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Images/7.jpg'/>
  <img width="150" height="175" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Images/8.jpg'/>
  <img width="150" height="175" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Images/9.jpg'/>
</p>


<hr>
For training I used retrain.py script (provided by TF). First it created bottleneck files with every image's cache in order to speed up training (only the last layer is not frozen, so a particular image always has the same output from the previous layers, regardless of the last layer. Therefore we compute these values once and save in .txt files). Next we have to specify a few hyperparameters (train-val-test ratio, training and validation batch sizes, learning rate, number of training steps) and a few directories (where to save final model, summaries for TensorBoard, where to get data from). You can find it in params.txt file. Then training is started. You can see how the loss was decreasing during training

A bit suprisingly train, validation and test accuracies were 100%, even without much hyperparameters tuning

<hr>
<p align="center"><b>The confusion matrix for the model is shown below</b></p>

<p align="center">
  <img width="100" height="100" src="https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/Confusion%20Matrix.png"/><br/>
  <b>Confusion matrix</b>
</p>
</hr>

<hr>
<p align="center"><b>Below you can see a few testing instances with classes probabilities</b></p>

<p align="center">
  <img width="350" height="200" src="https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/Glacier.png"/><br/>
  <b>Actual: Glacier</b>
  <b>Predicted: Glacier</b>
</p>

<p align="center">
  <img width="100" height="100" src="https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/Mountains.png"/><br/>
  <b>Actual: Mountains</b>
  <b>Predicted: Mountains</b>
</p>

<p align="center">
  <img width="100" height="100" src="https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/building.png"/><br/>
  <b>Actual: Building</b>
  <b>Predicted: Building</b>
</p>

<p align="center">
  <img width="100" height="100" src="https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/street.png"/><br/>
  <b>Actual: Street</b>
  <b>Predicted: Street</b>
</p>
<hr>
