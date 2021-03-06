# RoboCupHumanoid
In this project, we are aiming to implement [1] and improve it using Conv + LSTM layer for detection and tracking of the soccer ball for <a href="https://www.robocuphumanoid.org/">RoboCup Humanoid League</a>.

### Dataset
example_data.csv contains information about training images with the following fields:
<ul>
  <li><b>image_file</b> - image location,</li>
  <li><b>width</b> - width of the image,</li>
  <li><b>height</b> - height of the image,</li>
  <li><b>label</b> - label of the object,</li>
  <li><b>xmin</b> - top left x-coordinate of rectangle around object,</li>
  <li><b>ymin</b> - top left y-coordinate of rectangle around object,</li>
  <li><b>xmax</b> - bottom right x-coordinate of rectangle around object,</li>
  <li><b>ymax</b> - bottom right y-coordinate of rectangle around object.</li>
</ul>

To extract and label images we are using <a href="https://imagetagger.bit-bots.de/images/">Image Tagger</a>
We used <a href="https://pjreddie.com/darknet/yolo/">YOLO</a> for automatic ball detection and then we manually verified each the detection.

<b>Note</b>: One image file may contain multiple objects of different types.


## Running the tests


- Train sweaty
`python train.py --batch_size=16 --alpha=1000 --model_name=alpha1000 --epochs=50
`
- Test Sweaty
`python test.py --load=pretrained_models/alpha1000_epoch_50.model --testSet=data/test/ --trainSet=data/train/`





## References
[1] Fabian Schnekenburger, Manuel Scharffenberg, Michael Wulker, Ulrich Hochberg, Klaus Dorer [*Detection and Localization of Features on a Soccer Field with Feedforward Fully Convolutional Neural Networks (FCNN) for the Adult-Size Humanoid Robot Sweaty*](http://lofarolabs.com/events/robocup/ws17/papers/Humanoids_RoboCup_Workshop_2017_pape_4.pdf)
