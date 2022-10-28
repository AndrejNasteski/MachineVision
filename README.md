# MachineVision

Image Classification using Siamese Network

The goal is to identify and classify images of potato plant leaves. There are 3 categories of leaves: Healthy potato plant leaves, potato leaves with early blight and potato leaves with late blight. 

Considering that the dataset of images is relatively small (50 images for each class), a classic deep neural network would not perform very well. Instead, the idea is to build a model that only predicts if both samples from a pair of images are from the same class or not. For that task we used the siamese network model.

This particular siamese networks has two identical subnetworks. These subnetworks have the same architecture, parameters, and weights. Meaning parameters and weights are changed in both subnetworks. The two subnetworks are then joined and are evaluated for similarity with euclidean distance. One way to think about the two subnetworks is that they perform feature extraction on the images and then the outputs are joined.

The image dataset is transformed into a image pair dataset. Each image is first paired with a image from the same class (that isn't the same image), then another pair is created with the same initial image paired with an image from different class. The label for each pair is 1 if both images are from the same class, and 0 otherwise.

When a new image needs to be evaluated, we need to create pairs of images for each class and then see which class has the highest similarity with the new image sample.
