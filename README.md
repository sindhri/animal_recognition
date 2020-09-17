# Animal Recognition
Data source: dphi
Train a model to recognize 5 classes of animals
<img src = "https://github.com/sindhri/animal_recognition/blob/master/doc/img/img1.png" width = "500">
* Training: 6558 images, validation: 1638 images, testing: 901 images
* Used ImageDataGenerator for image augmentation, resizing, and normalization
* Use Accuracy as the metrics, and categorical_crossentropy as the loss function

Several different models are trained

<table>
  <tr>
    <th>Models</th>
    <th>Description</th>
    <th>Accuracy</th>
    <th>Notes</th>
  </tr>
  <tr>
    <td>Model1: MLP</td>
    <td>4-layer Dense, image size [256x256], optimizer= adam</td>
    <td>40%</td>
    <td>Not bad for an MLP</td>
  </tr>
  <tr>
    <td>Model2: MLP</td>
    <td>5-layer Dense with 2-layer dropout, tried both [256x256] and [100x100], optimizer tried both adam and sgd</td>
    <td>stuck at 23%</td>
    <td>MLP can't handle this problem</td>
  </tr>
  <tr>
    <td>Model3: CNN</td>
    <td>5-layer CNN + Maxpooling + dropout + Dense, [256x256], optimizer ='adam'</td>
    <td>stuck at 23%</td>
    <td>Not sure why CNN is preforming purely, local minimum?</td>
  </tr>
    <tr>
    <td>Model4: CNN</td>
    <td>4-layer CNN + Maxpooling + dropout + Dense, [100x100], optimizer ='adam', 20 epochs</td>
    <td>69%</td>
    <td>better!</td>
  </tr>
    <tr>
    <td>Model5: CNN</td>
    <td>4-layer CNN + Maxpooling + dropout + Dense, [100x100], optimizer ='adam', 50 epochs</td>
    <td>77%</td>
    <td>better with more epochs!</td>
  </tr>
    <tr>
    <td>Model6: CNN</td>
    <td>4-layer CNN + Maxpooling + dropout + Dense, [100x100], optimizer ='sgd', learning rate decay starting with 0.02, 20 epochs</td>
    <td>23%</td>
    <td>Learning rate too large!</td>
  </tr>
    <tr>
    <td>Model7: CNN</td>
    <td>4-layer CNN + Maxpooling + dropout + Dense, [100x100], optimizer ='sgd', with learning rate decay starting 0.01, 50 epochs</td>
    <td>81%</td>    
    <td>better with sgd and learning rate decay!</td>
  </tr>
    <tr>
    <td>Model8: VGG-19</td>
    <td>VGG-19 + 3 Dense + 2 dropout, image size [100x100], optimizer ='adam', 100 epochs with early stopping, stopped at epoch 10</td>
    <td>91%</td>
    <td>transfer learning has the best performance</td>
  </tr>
</table>
<br>

## Model1
<img src = "https://github.com/sindhri/animal_recognition/blob/master/doc/img/model1.png" width = "250">
## Model2
<img src = "https://github.com/sindhri/animal_recognition/blob/master/doc/img/model2.png" width = "250">
## Model3
<img src = "https://github.com/sindhri/animal_recognition/blob/master/doc/img/model3.png" width = "250">
## Model4
<img src = "https://github.com/sindhri/animal_recognition/blob/master/doc/img/model4.png" width = "250">
## Model5
<img src = "https://github.com/sindhri/animal_recognition/blob/master/doc/img/model5.png" width = "250">
## Model7
<img src = "https://github.com/sindhri/animal_recognition/blob/master/doc/img/model7.png" width = "250">
## Model8
<img src = "https://github.com/sindhri/animal_recognition/blob/master/doc/img/model8.png" width = "250">
