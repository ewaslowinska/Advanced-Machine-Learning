## Report on the respective parts of the assignment

### Part 1

I managed to run the code after installing and modifying some of the modules. After training the code with its original setup, the character accuracy turned out to be almost 99 percent, while the word accuracy was 93 percent. After scanning the predicted vs. ground truth labels, the only error I noticed was in the word "Kitty", which the machine read as "Kifty"

### Part 2

After manually splitting the Car Plate dataset into train and test, I proceeded to modify the SynthDataset and SynthCollator classes. In the new SynthDataset, I take the image filename and, based on it, I choose its respective XML annotation file. Using the BeautifulSoup package, I extract individual letters from each XML file and concatenate them into a single string representing the car plate name. In the new SynthCollator, I resize images to the size 32x100

### Part 3

I added measures to evaluate the character predictions: precision, micro and macro recall, and micro and macro F1-score

### Part 4

The model doesn't work quite well with the new dataset. Its character accuracy is barely 13 percent. Its recall and F1-scores are below 10 percent, indicating that the model is missing a significant number of true positive instances. Only its precision is worthwhile, being almost 62 percent, which suggests that when the model predicts something, it's often correct. The predicted labels are often the same for different images , which could indicate a lack of diversity in the training data or a tendency to predict certain labels more frequently. The predicted labels are also usually much shorter than the ground truth labels, which means that the model is overly simplifying its predictions. The majority of output labels contain only the characters "K", "L", "M", "H", "1", "2", "6" and "0".  It suggests that the model might be biased or stuck in a certain pattern, which may be due to imbalances in the training data or limitations in the model architecture. Possible improvements include:

- Finding a more diversed training data in terms of the fonts and character patterns
- Augmenting the data, by artificially diversifying the dataset
- Trying out a different model architecture
- Checking and preventing label imbalance
- Adjusting the post-processing techniques

### Part 5

In the process of implementing another model architecture, I focused on modifying the convolutional layers of the CRNN architecture. I changed the number of kernels, paddings, strides, filters and convolutional layers. These changes were made to capture more complex patterns. I also added global average pooling layer ```nn.AdaptiveAvgPool2d((1, None)))``` after the convolutional layers to ensure that the height becomes 1 before passing the features to the LSTM layers. I also added dropout with p=0.1 after each ReLU activation in the convolutional layers to prevent overfitting. Unfortunately, these adjustments did not improve the model's performance