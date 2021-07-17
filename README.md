# Vision Impulse Test

Goal of this project is to prototype and showcase a segmentation model on a custom geo-dataset. 

### Design Choices
* Pytorch along with Pytorch Lightning [1] is used for prototyping the model. 
  Pytorch Lightning is used to scale the model training on multiple GPUs/TPUs.        
* Due to time / computational constraints, the model was trained only for 50 epochs and the results obtained can be further improved.
* UNet architecture similar to [2] was used for the task. Due to unavailability of pre-trained models trained on required classes, we preferred custom model.
  <img width="640" height="240" src="https://github.com/njanirudh/Vision-Impulse-Test/blob/feature-segmentation/assets/unet_architecture.png" title="Input Image Channels">
* The trainer supports both 3 channels (RGB) and 12 channels (bands) for training and inference.
* Code is designed to be modular. This will make prototyping different models, hyperparameter tuning easier.  

### Input Image
The input 'tif.' image contains 12 channels.  

<img width="240" height="200" src="https://github.com/njanirudh/Vision-Impulse-Test/blob/feature-segmentation/assets/12_img_collage.png" title="Input Image Channels">

### Result
<img width="480" height="200" src="https://github.com/njanirudh/Vision-Impulse-Test/blob/feature-segmentation/assets/results.png" title="Input Image Channels">
The (left) image shows the output of the model trained only on the RGB channels (4,3,2)    <br />
The (right) image shows the output of model trained on all the channels (1-12)

Since the model is not trained till convergance, the results are not directly usable.

#### References
1. https://pytorch-lightning.readthedocs.io/en/latest/
1. https://medium.com/analytics-vidhya/creating-a-very-simple-u-net-model-with-pytorch-for-semantic-segmentation-of-satellite-images-223aa216e705
