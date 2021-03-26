# Dockship-Boat_classification

The challenge is to classify the image among 9 different types of boats. At first it seemed pretty easy like a simple beginer level image classification problem. But the real problem arose when I checked the dataset and it consisted of non-uniform distribution of data and moreover the data given were very much crowded by useless objects. The distribution of images per class was, 
* 'buoy': 53
* 'cruise_ship': 191
* 'ferry_boat': 63
* 'freight_boat': 23 
* 'gondola': 193 
* 'inflatable_boat': 16 
* 'kayak': 203 
* 'paper_boat': 31
* 'sailboat': 389
---
* Total : 1162

With such non-uniform distribution there was a high possibilty of variance and that's what happened over the course of time. I used ***InceptionResNetV2*** with weight of imagenet for as my model for transfer learning and added two more dense layer as my final model. The final model was 575 layer deep and the validation and train loss and accuracy are provided below.

![Screenshot 2021-03-27 001117](https://user-images.githubusercontent.com/44130583/112678506-0332e000-8e91-11eb-8b61-baeaa206ff16.png)
![Screenshot 2021-03-27 001457](https://user-images.githubusercontent.com/44130583/112678877-805e5500-8e91-11eb-8422-0fdaa06ad0f3.png)

As the network was very deep I did 15 epochs only. And the last epoch had this result,

    loss: 0.0685 - accuracy: 0.9868 - val_loss: 0.3339 - val_accuracy: 0.9079
    
So there is clearly a problem of variance in this model. The model is overfitting over the training dataset.
