# Wine Detector Using OpenVINO

## Introduction

This is a tutorial on how to use OpenVINO if you have an object detection model. The particular tutorial detects different kinds of wine. Feel free to flip through the Jupyter Notebooks in order to understand how OpenVINO's Python API works. 

## Featured Tutorials

### Simple Object Detection

Contains a brief example of how to set up a network, load it into a plugin, and run inference.

### Real-time Object Detection

Contains a slightly more complicated example, but puts the pieces together from the simple object detection module in order to detect different kinds of wine from a webcam.

### Async Real-time Object Detection

Basically the same tutorial as the real time object detection one, but using multiple requests to distribute inference tasks. While we wait for the inference task we care about to finish, others will be processing in the background.

### Core API Tutorials

Accompanying the simple object detection tutorial, real-time object detection tutorial, and the async real-time object detection tutorial are also tutorials that pretty much do the same thing but utilize the IECore instead of IEPlugin. IEPlugin may/will be deprecated in future releases of OpenVINO.

### Reshaping Input Layer of IENetwork

Contains a brief tutorial showing when/how to reshape your network.

### Loading Mutliple Networks

Contains a not-so-brief but hopefully clear walkthrough on how someone can use multiple networks in an application. 

## Dependencies

### Packages/Libraries
- OpenVINO 2019 R2
- OpenCV
- Numpy
- jupyter notebook
- matplotlib

### Networks
Download files from here and put in `./reverse_hand` directory!
https://drive.google.com/open?id=1o7ZeLIcNgb5f-gJh6qwnGM0HJ4TzJQ8T

Download files from here and put in `./reverse_hand_fp16` directory!
https://drive.google.com/open?id=1uXejmgdDaVr2bsbFrrVdlk5nAMm6Fq2i

## Classes (enumerated as follows)

1. Silveroak 2006
2. Silveroak 2015
3. Twomey 2013
4. Twomey 2016

## Conversion from Tensorflow to IR
This assumes that you have set up the OpenVINO environment. Replace `##` with either `16` or `32`.

```
$ mo.py \
>> --input_model wine_export/frozen_inference_graph.pb \
>> --tensorflow_use_custom_operations_config ssd_support_api_v1.14.json \
>> --tensorflow_object_detection_api_pipeline_config wine_export/pipeline.config \
>> --data_type FP## \
>> --output_dir wine_optimized/fp##/
```

## Citations

OpenPose Citation:


    @inproceedings{cao2018openpose,
      author = {Zhe Cao and Gines Hidalgo and Tomas Simon and Shih-En Wei and Yaser Sheikh},
      booktitle = {arXiv preprint arXiv:1812.08008},
      title = {Open{P}ose: realtime multi-person 2{D} pose estimation using {P}art {A}ffinity {F}ields},
      year = {2018}
    }

    @inproceedings{cao2017realtime,
      author = {Zhe Cao and Tomas Simon and Shih-En Wei and Yaser Sheikh},
      booktitle = {CVPR},
      title = {Realtime Multi-Person 2D Pose Estimation using Part Affinity Fields},
      year = {2017}
    }

    @inproceedings{simon2017hand,
      author = {Tomas Simon and Hanbyul Joo and Iain Matthews and Yaser Sheikh},
      booktitle = {CVPR},
      title = {Hand Keypoint Detection in Single Images using Multiview Bootstrapping},
      year = {2017}
    }

    @inproceedings{wei2016cpm,
      author = {Shih-En Wei and Varun Ramakrishna and Takeo Kanade and Yaser Sheikh},
      booktitle = {CVPR},
      title = {Convolutional pose machines},
      year = {2016}
    }

Links to the papers:

- [OpenPose: Realtime Multi-Person 2D Pose Estimation using Part Affinity Fields](https://arxiv.org/abs/1812.08008)
- [Realtime Multi-Person 2D Pose Estimation using Part Affinity Fields](https://arxiv.org/abs/1611.08050)
- [Hand Keypoint Detection in Single Images using Multiview Bootstrapping](https://arxiv.org/abs/1704.07809)
- [Convolutional Pose Machines](https://arxiv.org/abs/1602.00134)


