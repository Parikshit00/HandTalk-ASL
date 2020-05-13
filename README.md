# HandTalk-ASL
This project is American Sign Language classifier.


Uses python, openCV and Tensorflow to train Inception-V3 model, a Deep CNN image classifier. The Inception-V3 should be trained ny Imagenet dataset which is already been taken
care in Train.py. 


The last layer of Inception-V3 CNN can be retrained to identify numerous new categories. For this project the layer will be trained to classify
english alphabets represented by hand signs as used in American Sign Language. Few custom made hand signs must be included by the user for proper
communication (explained in the dataset section).


Framework used for this project: [Simple transfer learning with an Inception V3 architecture model](https://github.com/xuetsing/image-classification-tensorflow)

## Requirements

This project uses python 3.5 and the PIP following packages:
* opencv
* tensorflow
* matplotlib
* numpy
See requirements.txt for required packages and versions.

### Install using PIP
```
pip3 install -r requirements.txt
```

## Dataset
This project contains the code only. The dataset should be in the format like below:

```
|
---- /dataset
|    |
|    |
|    ---- /A
|    |    A1.jpg
|    |    A2.jpg
|    |    ...
|    |
|    |
|    ---- /B
|         B1.jpg
|         B2.jpg
|         ...
|     |
|     | 
|     |  
|     ---- /del
|           del1.jpg
|           del2.jpg
|           ...
```

Like `del` folder, add folders for `space` with labelled images as `space1.jpg space2.jpg...` .
                       

Also add a `nothing` folder with labelled images as `nothing1.jpg nothing2.jpg...` in different lighting conditions and
background color to train the classifier to output `nth` when no input is given via webcam during live demo. Improper
images for `nothing` class will result in a continous stream of random outputs which must be avoided for proper communication.
AND ofcourse the alphabets with their representation of sign language.
                    
Each folder must contain atleast 3000 images for each categories.

The image below shows hand signs for american sign loanguage:
![American sign language](https://i.pinimg.com/originals/37/cf/87/37cf874cf43063575bf28c5ac5ac97e5.jpg)

## Training

Visit the framework link for more command options. Depending upon your dataset it may take more than 3 hours to train.

```
python3 train.py \
  --bottleneck_dir=logs/bottlenecks \
  --how_many_training_steps=2000 \
  --model_dir=inception \
  --summaries_dir=logs/training_summaries/basic \
  --output_graph=logs/trained_graph.pb \
  --output_labels=logs/trained_labels.txt \
  --image_dir=./dataset
```

## Classifying
  
To test classification, use the following command:
```
python3 classify.py path/to/image.jpg
```

## Using webcam (demo)

To use webcam, use the following command:
```
python3 classify_webcam.py
```
Your hand must be inside the rectangle. Keep position to write word and if you need to delete or give spaces hold `del` and `space` hand sign position.


                        
