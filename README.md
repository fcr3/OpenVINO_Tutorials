# Wine Detector Using OpenVINO

## Introduction

This is a tutorial on how to use OpenVINO if you have an object detection model. The particular tutorial detects different kinds of wine. Feel free to flip through the Jupyter Notebooks in order to understand how OpenVINO's Python API works. 

## Two Tutorials

### Simple object detection

Contains a brief example of how to set up a network, load it into a plugin, and run inference.

### Real-time object detection

Contains a slightly more complicated example, but puts the pieces together from the simple object detection module in order to detect different kinds of wine from a webcam.

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
