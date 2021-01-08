# Landscape Classification
<h3>Comparison of transfer learning using VGG16, ResNet50, and InceptionV3 </h3>

I had a dataset of 6 types of landscapes with 25k total images.
```
The images belonged to the following classes:
Buidling
Forest
Glacier
Mountain
Sea
Street
```
Instead of training a custom model from scratch, pretrained models available in keras, VGG16, ResNet50, and InceptionV3 were used. The pre-trained weights of imagenet were used. 

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
After loading the pretrained models avialable with keras, 2 fully connected layers were added before the final classification layer. The activations for the fully connected layers were ReLu and the activation for classification layer was softmax. Categorical Cross Entropy loss was used as this was a multi-class classification problem. Stochastic gradient descent optimizer was used with a learning rate of 0.001, decay of 1e-7 and momentum of 0.9. The models were trained under two different set of conditions. First, they were trained for 30 epochs to study the speed of learning for each model. Then the models were trained with early stopping but under the condition that if the validation loss did not decrease for 6 continuous epochs, the model training would be stopped. This yielded two sets of results which are shown below in the form of graphs and tables.
<hr>
<p align="center">
  <img width="400" height="230" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/Plot%20ResNet50.png'/>
  <img width="400" height="230" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/Plot%20VGG16.png'/>
  <img width="400" height="230" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/Plot%20Inception.png'/>
</p>
<p align = "center">Validation and training loss progress graphs for training of models when all models were trained for 30 epochs</p>

<p align="center">
  <img width="400" height="230" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/Plot%20ES%20ResNet50.png'/>
  <img width="400" height="230" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/Plot%20ES%20VGG16.png'/>
  <img width="400" height="230" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/Plot%20ES%20Inception.png'/>
</p>
<p align = "center">Validation and training loss progress graphs for training of models when all models were trained until early stopping</p>
<hr>

<hr>
<p align = "center">Tables with quantitative comparison of base models on differnt training settings are shown below</p>
<p align="center">
  <img width="700" height="300" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/Training%2030%20Epochs.png'/>
  <img width="700" height="300" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/ES%20Training.png'/>
</p>
<hr>

Note: Remove the early stopping callback from model.fit function if you want to train for a fixed number of epochs.
