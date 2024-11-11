# YOLO parameters

# Hyperparameters of YOLO
lr0: 0.01 # (float) initial learning rate (i.e. SGD=1E-2, Adam=1E-3)
lrf: 0.01 # (float) final learning rate (lr0 * lrf)
momentum: 0.937 # (float) SGD momentum/Adam beta1
weight_decay: 0.0005 # (float) optimizer weight decay 5e-4
warmup_epochs: 3.0 # (float) warmup epochs (fractions ok)
warmup_momentum: 0.8 # (float) warmup initial momentum
warmup_bias_lr: 0.1 # (float) warmup initial bias lr
box: 7.5 # (float) box loss gain
cls: 0.5 # (float) cls loss gain (scale with pixels)
dfl: 1.5 # (float) dfl loss gain
pose: 12.0 # (float) pose loss gain
kobj: 1.0 # (float) keypoint obj loss gain
label_smoothing: 0.0 # (float) label smoothing (fraction)
nbs: 64 # (int) nominal batch size
hsv_h: 0.015 # (float) image HSV-Hue augmentation (fraction)
hsv_s: 0.7 # (float) image HSV-Saturation augmentation (fraction)
hsv_v: 0.4 # (float) image HSV-Value augmentation (fraction)
degrees: 0.0 # (float) image rotation (+/- deg)
translate: 0.1 # (float) image translation (+/- fraction)
scale: 0.5 # (float) image scale (+/- gain)
shear: 0.0 # (float) image shear (+/- deg)
perspective: 0.0 # (float) image perspective (+/- fraction), range 0-0.001
flipud: 0.0 # (float) image flip up-down (probability)
fliplr: 0.5 # (float) image flip left-right (probability)
bgr: 0.0 # (float) image channel BGR (probability)
mosaic: 1.0 # (float) image mosaic (probability)
mixup: 0.0 # (float) image mixup (probability)
copy_paste: 0.0 # (float) segment copy-paste (probability)
auto_augment: randaugment # (str) auto augmentation policy for classification (randaugment, autoaugment, augmix)
erasing: 0.4 # (float) probability of random erasing during classification training (0-0.9), 0 means no erasing, must be less than 1.0.
crop_fraction: 1.0 # (float) image crop fraction for classification (0.1-1), 1.0 means no crop, must be greater than 0.

# YOLO description

This study implements YOLO in the PyCharm environment. PyCharm is open-source and has an intuitive interface, making it easy to train and validate models, as well as optimize model parameters such as IOU settings and confidence adjustments. Additionally, by adding plugins, the object detection results can be connected to an Arduino development board, directly displaying on the circuit board and sending images and messages of detected faults. This was a major reason for choosing this algorithm.
During the training process, we initially tried manually labeling items, but the process was tedious and exhausting. We later improved our experimental method by using image processing to extract frames from videos, flipping and aligning images to automate the generation of bounding boxes and class text files through code. This saved a significant amount of manual annotation time. The model was trained with parameters set to epochs=10 to compare differences between manual labeling and auto-generated bounding boxes. By testing on non-training images, the accuracy of auto-generated bounding boxes reached 98.64%, while manual labeling had an accuracy of 0% and even led to misclassifications.
