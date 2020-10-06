# R-MNIST
The MNIST database (Modified National Institute of Standards and Technology database) is a large database of handwritten digits that is commonly used for training various image processing systems. The database is also widely used for training and testing in the field of machine learning. The MNIST database contains 60,000 training images and 10,000 testing images of  28x28 grayscale images. Each image is encoded as a row of 784 integer values between 0 and 255 indicating the brightness of each pixel. The label associated with each image is encoded as an integer value between 0 and 9. The arrangement of the data is as follows:

Functions to see the image encoded in each row:

```
rotate <- function(x) {
  return(t(apply(x, 2, rev)))
}
```

```
plot_matrix <- function(vec) {
  q <- matrix(vec, 28, 28, byrow = TRUE)
  nq <- apply(q, 2, as.numeric)
  image(rotate(nq), col = gray((0:255)/255))
}
```

If you want to plot the fifth image, for example, you can call the plot function as follows: 

```
plot_matrix(mydata[5, 2:785])
```

-----

## Logistic regression:
[Code file](https://github.com/Janette-Le/R-MNIST/blob/main/Codes%20-%20Logistic%20regression.R)<br>
[Report](https://github.com/Janette-Le/R-MNIST/blob/main/Logistic%20Regression%20report.pdf)<br>

![.](/images/linear 1.PNG)
![.](/images/linear 2.PNG)

-----

## Random forests
[Code file](https://github.com/Janette-Le/R-MNIST/blob/main/Codes%20-%20Random%20forest.R)<br>
[Work approach](https://github.com/Janette-Le/R-MNIST/blob/main/Random%20forests%20report.pdf)<br>
<p>The task is to deploy a script that allows us to grow multiple classification trees on the MNIST dataset and combine their outputs. 
- Each tree is to be grown from a random sample of the original training set. The random training sample is generated by sampling images from the original training set (with replacement) and selecting a subset of the features each time (the size of this sample is also random). This means that each time training a new tree, the number of features to use for the training process should be determined. Each time an image is selected, randomly choose training_set_size pixels from the image and add it to the new training set. 
- Once having a full new training set, grow the classification tree (use the default parameters values of the library that are decided to use to grow these trees).  
- Finally, to produce a prediction, select the appropriate features for each new test image that corresponds to each tree and combine the outputs according to a majority voting rule.
- Run the script for 1, 10, and 500 trees. Each time produces a confusion matrix to summarize the results. Draw comparisons with the accuracy obtained with logistic regression.</p>

----

## Model accuracy comparison

| Models | Accuracy |
| ------------- | ------------- |
| Linear regression  | 66.59%  |
| Random forests - 1 tree| 82.85% |
| Random forests -  tree| 94.91% |
| Random forests - 1 tree| 97.22% |
