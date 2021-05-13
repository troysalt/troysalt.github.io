---
layout: page
title: Image Classification with UAS
bigimg:
  - "/img/uas/phrag.jpg" : "Phragmites and native bulrush at the Great Salt Lake (2019)"
---

**Thesis Abstract**

A relatively new machine learning method in remote sensing, deep learning, has gained interest in recent years. Deep learning models are often applied to the analysis of fine spatial resolution imagery acquired by relatively low-cost unoccupied aircraft systems (UAS). Deep learning models such as convolutional neural networks (CNNs) can classify imagery using complex, non-linear relationships using spatial and spectral information. Particularly, CNNs have powerful capabilities to learn spatial patterns in an image. However, the spatial detail in an image depends on the spatial resolution, the coarser the spatial resolution, the less spatial detail in the image. In August 2020 at the Howard Slough Waterfowl Management Area, near Ogden, Utah, the Utah Department of Natural Resources (DNR) flew a UAS that captured 7.6 cm resolution imagery to monitor an invasive plants species, Phragmites australis, along with native vegetation and land covers. They applied a CNN model that reliably made predictions, but their UAS had a slow capture rate at about 1.2 km2/day. It is possible to increase the capture rate by using a different UAS and increasing the flight altitude, with a consequence that the spatial resolution will coarsen. For this reason, the Utah DNR is considering different options for UAS platforms, however, they need to evaluate the effect of a coarser spatial resolution on the CNN model’s classification accuracy. To test this relationship, this study used a subset of the 2020 image data and simulated coarser resolutions using spatial averaging to 15, 23, 30, 38, 53, and 76 cm resolution. A CNN model was produced at each resolution, and the accuracy metrics were compared to that of the original 7.6 cm resolution imagery. The testing indicated that model accuracy decreased as the spatial resolution coarsened. At the 23 cm resolution, the model overall accuracy decreased from 5-11% compared to the original resolution. One of the options for a new UAS system can capture about 65 km2/day at a 20 cm resolution. If selected, the large increase in capture rate is likely worth the relatively small decrease in model accuracy.

Please contact me if you'd like more information about the study.

Last update: May 13, 2021
