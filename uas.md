---
layout: page
title: Image Classification with UAS
bigimg:
  - "/img/uas/phrag.jpg" : "Phragmites and native bulrush at the Great Salt Lake (2019)"
---

**Project Statement**

*Phragmites australis* near the Great Salt Lake, UT is classified with a deep convolutional neural network and fine-resolution multispectral imagery, in order to assist the Utah Department of Natural Resources in removing the invasive species from the state.

**Motivation**

An invasive subspecies of *Phragmites australis* was likely introduced to Utah in the early 1980s and has been a nuisance ever since. The Utah Department of Natural Resources (DNR) has been working to remove the plant for many years, and in an effort to keep track of progress and evaluate the effectiveness of remediation, the DNR is imaging the Howard Slough Waterfowl Management Area as they apply treatments. The environment is extremely difficult to navigate and requires a Marsh Master to avoid vehicles sinking into the marsh. A small Unmanned Aerial System (sUAS) is ideal for monitoring the situation. The sUAS is fitted with a multispectral sensor (blue, green, red, red-edge, near-infrared) and flown at a height to produce a ground sample distance of about 7.5 cm.

**Workflow**

There are several image collection zones about 100 acres each. Training images and labels are produced for each zone, then they are added and split randomly into training and test data. These data are input to the convolutional neural network, which uses Keras and a Tensorflow backend. The model is evaluated for overall accuracy, precision, recall, and kappa index, then saved as a .h5 file. The model is now input to a Python script that takes the original model, iterates through each image zone, and trains and predicts for that specific zone. The result is a multiclass prediction for Phragmites, Native Vegetation, Water, Algae, and Non-Photosynthetic Material in a .tif format with the original geospatial information retained from the input orthoimage. The script also outputs a .txt file with calculated areas of each class.

**This project is in the late stages of development and will be updated with results after final image collection in July.**

Last update: June 25th, 2020
