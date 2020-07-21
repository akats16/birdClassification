# birdClassification


# 1. Background

As part of a 24 hour challenge, I was asked to create a "Bird Trackr" that could take an image of a bird and classify it as either a wren, sparrow, warbler, or sparrow. 


# 2. Data Background
The Caltech-UCSD Birds 200 (CUB-200) dataset with 11,788 different images of birds. Associated with the project were the following files:

Images: images of each of the birds
Train/ Test Split: splits for training and testing
Bounding boxes: the x, y, width, and height of the boxes surrounding the birds


# 3. Data Preprocessing 

To process the data, I first imported all the files and combined them into a larger dataset that was concated based on bird id. I only kept the four species that were mentioned in the assignment. In the dataframe, there was a column that identifies whether the bird was a training or testing bird. I was then able to create a training and testing data. For both dataframes, I changed all the images to be 224X224X3 and divided the pixel values by 255.0 to ensure their values are between 0 and 1.


# 4. Model Creation

For the model, I had two 32 filters followed by two 64 filters. I utilized max-pooling between layers to reduce the amount of parameters and computation cost. Additionally, max-pooling theoretically extracts the sharpest features. I also added some dropout layers to prevent overfitting of the data.


# 5. Results

The model achieved 87% accuracy during training, but since the classes were imbalanced, with mostly images of sparrows and warblers, this model needs further image augmentation for the other classes. Hence, although the performance seems high, it is not an accurate depiction of the model success.


# 6. Next Steps

As I simply hard-coded the hyperparameters, I would like to go back and do a grid-search on them. I also would like to explore different variations of architecture. For instance, I think underlying the model with a ResNet framework would likely improve performance.

I need to oversample the vireos and wren classes.

Additionally, I would like to use the bounding-boxes to actually crop the images before processing them.

I need to remove all the hard coding from my code and transform the blocks of code into actual classes so they're easier to re-use.
