## Remarks

Initial Thoughts:

-   We are compressing the images too much, which should be improved by adjusting the IMAGE_SIZE
-   Also we should then decrease the BATCH_SIZE so that we can increase the number of batches
-   There are some aberrations in the WEED class images in form of streched pixel lines, I wonder it can be omitted
-   Some images in the dataset are vertical while some horizontal, we should take care of that
-   Since, we are doint binary classification we will use BinaryCrossentropy loss.

training1:

-   This training was just to take a feel of the dataset.
-   The accuracy was low and loss was all over the place
-   We did not implement the above discussed points yet, e.g. using BCE, increasing IMAGE_SIZE, etc.

thoughts_2:

-   I've mostly worked on categorical data (non-binary), since I thought they were more challenging.
-   For binary_crossentropy we should use sigmoid in the output layer.
-   The output layer should only have one neuron
-   Use of adamW might do some magic

training2:

-   Implemented a lot of thoughts, result is good, needs refinement.
-   Used recall also along with accuracy as metric, which may be unnecessary as data is quite balanced
-   The training time was a lot, should've used GPU but tensoflowwwww, might shift to pytorch
-   Everything was kinda fine, till the third last epoch, which messed up a bit
-   Need to get the epochs right.

suggestions:

-   I need to change some layers and hyperparameters.
-   Increase epochs to 100, might need to cut parameters then.
-   Can change activation functions in CNN itself
-   Should also use: VGG19, ResNet50, efficientNet

thought_3n4:

-   Going to use VGG19 with pretrained weights of imagenet

training3 and training4:
- I was more focused on model training, but the results are still unsatisfactory.
- Most of the training took too much time for my laptop (sometimes 30hrs) and even them my system would crash due lack of memory/RAM
- Technically I am producing good accuracy and recall.
- The correct are predictions are coming with good confidence while incorrect ones are showing less confidence which is a good thing.
- But there is something off with the training pattern, especially the graph.

thought_5:
-  In hindsight, the dataset can be fixed a bit.
-  The normal class have some images with mostly soil in it, but they still *might* be useful.
- The normal class need some standardization in images, also the larger images can be broken down into smaller ones
- The weed class is consistent in sizing, but there are some distortions.
- The weed class can be zoomed in a bit, since it will be efficient to use a low res zoomed in image instead of a high res one with the similar signinficance
- I wonder what tools I can use to do this , I have little idea.
