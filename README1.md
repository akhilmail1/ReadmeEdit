## Model LOSS : 
Any deep learning model, during training evaluates a loss, that is a measure of how good or bad its predictions are. In SSD model, we need to detect the object location ( or find the bounding box parameters) as well as predict the class of the object ( Image classification ).

Hence, to calculate overall loss of the model, we first compute two losses, 
#### 1. Smooth L1 Loss:
![Smooth L1](https://miro.medium.com/max/3672/1*Ffwrleogyg4DqHAndxIp-Q.png)

This is a loss function for `regression` output of parameters of bounding boxes.
#### 2. Softmax Loss:
![Softmax Loss](https://miro.medium.com/max/1071/1*yD4d15xCcA45WaJBWzT4jg.png)

This is loss function for `classification` output of scores for each class.

Now, to improve the model stability, `Hard Negative Mining` is done.
### Hard Negative Mining:

Since we associated a background class, most of the default boxes will predict to be negative ( By negative we mean that it predicts there is no object, or it is background ). Therefore, we sort the negative boxes and pick the top boxes keeping the number of negative_boxes to number of positive_boxes at most 3 : 1. As written in paper :
> Instead of using all the negative examples, we sort them using the highest confidence loss for each default box and pick the top ones so that the ratio between the negatives and positives is at most 3:1.

Finally combining these concepts, the total model loss is calculated, which model will use in learning its parameters in further training.
