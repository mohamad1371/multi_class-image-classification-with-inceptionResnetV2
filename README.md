# multi_class-image-classification-with-inceptionResnetV2

for a 10-class image classification problem, i have used Transfer learning.
i had a train dataset of 10000 images which were categorized in 10 folder(each folder named from 1 to 10 and contained 1000 images).
i used ImageDataGenerator from tensorflow which helps us in spliting train folder for creating validation data.
for a better calculation i used categorical_crossentropy loss and CategoricalAccuracy.
for the puprose of augmenting dataset, i used the parameters such as fliping, rotating, zooming etc, in ImageDataGenerator argument.

from different pretrained models which are available in tf.keras.applications the inceptionResnetV2 had the best results for this problem.
the important thing in this model is that the input images should have height and width of 299 pixels and if the training time is important for us it's better to freeze the weights of model and then train it on our dataset.

i added four dense layers at the end of the inceptionResnetV2 model. this last layers have 2048, 1024, 512 and 10 unints respectively. this are for specifiying the model to our problem. this 4 layers will be trained during training process.

finally for the test set we had a seprate folder with 10000 uncategorized images. 
in the last blocks of code i tried to save the trained model and use it for predictiong the class of test images. there maybe a error of RAM overloading when you have 10000 images.
