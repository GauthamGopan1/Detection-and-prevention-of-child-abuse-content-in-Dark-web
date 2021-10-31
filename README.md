# Detection-and-prevention-of-child-abuse-content-in-Dark-web

The following are the code sniptets that forms the base work of our system

Nudity Detection :-

import numpy as np
import pandas as pd 
from keras.preprocessing.image import ImageDataGenerator, load_img
from keras.utils import to_categorical
from sklearn.model_selection import train_test_split
from keras.optimizers import RMSprop,SGD,Adam
import matplotlib.pyplot as plt
import random
import os
print(os.listdir("../input/fiveclasses/Five_classes_128"))
FAST_RUN = False
IMAGE_WIDTH=128
IMAGE_HEIGHT=128
IMAGE_SIZE=(IMAGE_WIDTH, IMAGE_HEIGHT)
IMAGE_CHANNELS=1
folders = os.listdir("../input/fiveclasses/Five_classes_128")
categories = []
filenames = []
for folder in folders:
    for filename in os.listdir("../input/fiveclasses/Five_classes_128/"+folder):
        categories.append (str(folder.split('_')[-1]))
        filenames.append("../input/fiveclasses/Five_classes_128/"+folder+"/"+filename)
    #     if category == 'norm':
    #         categories.append(1)
    #     elif category == 'nude':
    #         categories.append(0)
    #     else:
    #         categories.append(2)


df = pd.DataFrame({
    'filename': filenames,
    'category': categories
})
df.head()
df['category'].value_counts().plot.bar()
df['category'].value_counts()

Speech Emotion
