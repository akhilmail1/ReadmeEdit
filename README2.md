### Intersection over Union / IOU (Jaccard overlap) :
One of the task to be done before model training is to match a set of default boxes with actual ground truth boxes. 
This matching is done by a method called Intersection over Union, in which we divide the area of intersection of the two boxes by the area of union of the two boxes to yield a iou value(floating point number). Now if this value is greater than a threshold ( mostly 0.5 ) then we say it is matched, otherwise it is not matched.

![IOU](https://www.researchgate.net/profile/Rafael-Padilla/publication/343194514/figure/fig2/AS:916944999956482@1595628132920/Intersection-Over-Union-IOU.ppm)
