# Quantize a Segmentation Model and Show Live Inference

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/eaidova/openvino_notebooks_binder.git/main?urlpath=git-pull%3Frepo%3Dhttps%253A%252F%252Fgithub.com%252Fopenvinotoolkit%252Fopenvino_notebooks%26urlpath%3Dtree%252Fopenvino_notebooks%252Fnotebooks%2Fct-segmentation-quantize%2Fct-scan-live-inference.ipynb)

<p align="center">
    <img src="https://user-images.githubusercontent.com/77325899/154279555-aaa47111-c976-4e77-8d23-aac96f45872f.gif"/>
</p>

## Notebook Contents

This folder contains four notebooks that show how to train,
optimize, quantize and show live inference on a [MONAI](https://monai.io/) segmentation model with
[PyTorch Lightning](https://lightning.ai/) and OpenVINO:

1\. [Data Preparation for 2D Segmentation of 3D Medical Data](data-preparation-ct-scan.ipynb)

2\. [Train a 2D-UNet Medical Imaging Model with PyTorch Lightning](pytorch-monai-training.ipynb)

3\. [Convert and Quantize a UNet Model and Show Live Inference using NNCF](ct-segmentation-quantize-nncf.ipynb)

4\. [Live Inference and Benchmark CT-scan Data with OpenVINO](ct-scan-live-inference.ipynb)

NNCF performs quantization within the PyTorch framework. There is a pre-trained model and a subset of the dataset provided for the quantization notebook,
so it is not required to run the data preparation and training notebooks before running the quantization tutorial.

This quantization tutorial consists of the following steps:

* Use model conversion Python API to convert the model to OpenVINO IR. For more information about model conversion Python API, see this [page](https://docs.openvino.ai/2024/openvino-workflow/model-preparation.html).
* Quantizing the model with NNCF with the [Post-training Quantization with NNCF Tool](https://docs.openvino.ai/2024/openvino-workflow/model-optimization-guide/quantizing-models-post-training/basic-quantization-flow.html) API in OpenVINO.
* Evaluating the F1 score metric of the original model and the quantized model.
* Benchmarking performance of the original model and the quantized model.
* Showing live inference with async API and MULTI plugin in OpenVINO.

You will also see real-time segmentation of kidney CT scans running on a CPU, iGPU, or combining both devices for higher
throughput. The processed frames are 3D scans that are shown as individual slices. The visualization slides through the slices with detected kidneys
overlayed in red. A pre-trained and quantized model is provided, so running the previous notebooks (1-3) in the series is not required.

## Installation Instructions

This is a self-contained example that relies solely on its own code.</br>
We recommend running the notebook in a virtual environment. You only need a Jupyter server to start.
For details, please refer to [Installation Guide](../../README.md).
