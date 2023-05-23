# Distracted_Driver_classification

# Image Classification was done into following 10 classes.

c0: safe driving

c1: texting - right

c2: talking on the phone - right

c3: texting - left

c4: talking on the phone - left

c5: operating the radio

c6: drinking

c7: reaching behind

c8: hair and makeup

c9: talking to passenger

# Introduction: 
Driving a car is a complex task, and it requires complete attention. Distracted driving is any activity that takes away the driver’s attention from the road. Several studies have identified three main types of distraction--
# visual distractions (driver’s eyes off the road)
# manual distractions (driver’s hands off the wheel) 
# cognitive distractions (driver’s mind off the driving task).

Motor Vechicle Acciedents due to distracted driving. Texting is the most alarming distraction. Sending or reading a text takes your eyes off the road for 5 seconds. At 55 mph, that’s like driving the length of an entire football field with your eyes closed. Many states now have laws against texting, talking on a cell phone, and other distractions while driving.

We believe that computer vision can augment the efforts of the governments to prevent accidents caused by distracted driving. Our algorithm automatically detects the distracted activity of the drivers and alerts them. We envision this type of product being embedded in cars to prevent accidents due to distracted driving.

# Data:
We took the StateFarm dataset which contained snapshots from a video captured by a camera mounted in the car. The training set has labeled samples with equal distribution among the classes and unlabeled test samples. There are 10 classes of images:

# Evaluation Metric:
Before proceeding to build models, it’s important to choose the right metric to gauge its performance. Accuracy is the first metric that comes to mind. But, accuracy is not the best metric for classification problems. Accuracy only takes into account the correctness of the prediction i.e. whether the predicted label is the same as the true label. But, the confidence with which we classify a driver’s action as distracted is very important in evaluating the performance of the model. 

Data leakage: With the understanding of what needs to be achieved, we proceeded to build the CNN models from scratch. We added the usual suspects — convolution batch normalization, max pooling, and dense layers. The results — loss of 0.014 and accuracy of 99.6% on the validation set in 3 epochs. Oh, well. There was no serendipity after all. So, we looked deeper into what could have gone wrong and we found that our training data has multiple images of the same person within a class with slight changes of angle and/or shifts in height or width. This was causing a data leakage problem as the similar images were in validation as well, i.e. the model was trained much of the same information that it was trying to predict.
