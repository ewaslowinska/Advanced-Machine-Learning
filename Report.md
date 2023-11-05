## Project report

The aim of this project was to create a machine learning model that would perform score classification and sentiment analysis of Korean drama reviews. There are 4 files, each of which corresponds to one of the 4 experiments planned in this project. In the first experiment, the model performs a multiclass score classification with 19 classes, which are scores ranging from 1 to 10 with half-point increments. In the second experiment, a multiclass score classification is performed with 10 classes as the original "full" scores were merged with their "half" counterparts (e.g. 1 with 1.5). In the third experiment, a sentiment analysis is taking place, where scores from 1 to 5.5 are classified as negative and from 6 to 10 as positive. A weight tensor is created to account for the class imbalance. In the fourth experiment, the same sentiment analysis is performed but with undersampling applied to counter the class imbalance.

### Running the code files

You might need to install torch and torchtext to your mltgpu server in order to run the code. Next, make sure that the 'reviews.csv' file is in the same directory as your code file. Then feel free to run the code all at once. You might get a "cuDNN version incompatibility" error when running the training block, but after running it again, the error should disappear
