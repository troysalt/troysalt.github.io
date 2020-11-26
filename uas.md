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

**Prediction Workflow**

There are several image collection zones that total about 8 km^2. Training images and labels are produced for each zone, then they are added and split randomly into training and test data. These data are input to a convolutional neural network, which uses Keras and a Tensorflow backend. The model is evaluated for overall accuracy, precision, recall, and kappa index, then saved as a .h5 file. The model is now input to a Python script that takes the original model, iterates through each image zone, and trains and predicts for that specific zone. The result is a multiclass prediction for Phragmites, Native Vegetation, Water, Algae, and Non-Photosynthetic Material in a .tif format with the original geospatial information retained from the input orthoimage. The separate orthoimage predictions are then added to a mosaic dataset. A heavily compressed version of the imagery and predictions can be viewed in this [web mapping application](https://uofu.maps.arcgis.com/apps/webappviewer/index.html?id=8109cf223ed949b088c9b2376c22e4f0).

The general model had a test overall accuracy of 78.4% and a kappa index of 0.729.

The models trained on each orthoimage had a range of overall accuracy from 84.7-93.0% and kappa index from 0.798-0.913.

**Simulating Coarser Resolutions**

While we've had success with mapping using UAS imagery, only a small extent was covered and the collection and image processing took a full week. The Utah DNR has a much larger area to cover, so other options need to be explored. We will use spatial averaging to degrade the native imagery to several different resolutions to simulate other UAS, airborne, and satellite imagery collection methods. In future projects with the Utah DNR, we may use UAS for certain focus areas and satellites for broader classifications of large extents. We are also considering capturing UAS imagery in certain areas, predicting on those images, then using the predictions as ground truth for satellite image predictions. Results are forthcoming in early 2021.

**AGU Poster**

A poster was presented at the American Geophysical Union meeting in December of 2020. [View it here.](https://agu2020fallmeeting-agu.ipostersessions.com/default.aspx?s=C3-FF-11-90-43-F9-3D-49-DC-6B-53-35-3F-7C-0E-8D&guestview=true)

Last update: November 26th, 2020
