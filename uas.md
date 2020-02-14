---
layout: page
title: Image Classification with sUAS
---

**Project Statement**

*Phragmites australis* near the Great Salt Lake, UT will be classified with
machine learning techniques by utilizing fine-resolution multispectral imagery, in order
to assist the Utah Department of Natural Resources in elminating the invasive species 
from the state.

**Motivation**

An invasive sub species of *Phragmites australis* was likely introduced to Utah in the early
1980s and has been a nuisance ever since. The Utah Department of Natural Resources (DNR)
has been working to remove the plant for many years, and in an effort to keep track of progress
and evaulate effectiveness of remediation, the DNR is imaging the Howard Slough Waterfowl Management
Area as they apply treatment. The environment is extremely difficult to navigate, and requires
a Marsh Master (essentially a tank) to avoid vehicles sinking into the marsh. A small Unmanned
Aerial System (sUAS) is ideal for monitoring the situation. The sUAS is fitted with a multispectral 
sensor (blue, green, red, red-edge, near-infrared) and flown at a height to produce a ground sample
distance of about 7.5 cm. 

**Workflow**

The current idea is to develop a Python script which utilizes the TensorFlow machine learning
library for a semi-automated workflow. To start, we'll perform a pixel-based supervised 
classification with a convolution neural network (CNN). In the future, we hope to assess 
several different methods, including some object-based methods.

**This project is in development and will be updated occasionally**

Last update: February 13th, 2020
