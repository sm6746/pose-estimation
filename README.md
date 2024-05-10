
-----------------

| **Build Type**   |`Linux`           |`MacOS`           |`Windows`         |
| :---:            | :---:            | :---:            | :---:            |
| **Build Status** | [![Status](https://github.com/CMU-Perceptual-Computing-Lab/openpose/workflows/CI/badge.svg)](https://github.com/CMU-Perceptual-Computing-Lab/openpose/actions) | [![Status](https://github.com/CMU-Perceptual-Computing-Lab/openpose/workflows/CI/badge.svg)](https://github.com/CMU-Perceptual-Computing-Lab/openpose/actions) | [![Status](https://ci.appveyor.com/api/projects/status/5leescxxdwen77kg/branch/master?svg=true)](https://ci.appveyor.com/project/gineshidalgo99/openpose/branch/master) |

[**OpenPose**](https://github.com/CMU-Perceptual-Computing-Lab/openpose) has represented the **first real-time multi-person system to jointly detect human body, hand, facial, and foot keypoints (in total 135 keypoints) on single images**.



## Contents
1. [Results](#results)
2. [Features](#features)
3. [Related Work](#related-work)
4. [Installation](#installation)
5. [Quick Start Overview](#quick-start-overview)
6. [Send Us Feedback!](#send-us-feedback)
7. [Citation](#citation)
8. [License](#license)


## Features
**Main Functionality**:
- **2D real-time multi-person keypoint detection**:
    - 15, 18 or **25-keypoint body/foot keypoint estimation**, including **6 foot keypoints**. **Runtime invariant to number of detected people**.
    - **2x21-keypoint hand keypoint estimation**. **Runtime depends on number of detected people**. See [**OpenPose Training**](https://github.com/CMU-Perceptual-Computing-Lab/openpose_train) for a runtime invariant alternative.
    - **70-keypoint face keypoint estimation**. **Runtime depends on number of detected people**. See [**OpenPose Training**](https://github.com/CMU-Perceptual-Computing-Lab/openpose_train) for a runtime invariant alternative.
- [**3D real-time single-person keypoint detection**](doc/advanced/3d_reconstruction_module.md):
    - 3D triangulation from multiple single views.
    - Synchronization of Flir cameras handled.
    - Compatible with Flir/Point Grey cameras.
- [**Calibration toolbox**](doc/advanced/calibration_module.md): Estimation of distortion, intrinsic, and extrinsic camera parameters.
- **Single-person tracking** for further speedup or visual smoothing.

**Input**: Image, video, webcam, Flir/Point Grey, IP camera, and support to add your own custom input source (e.g., depth camera).

**Output**: Basic image + keypoint display/saving (PNG, JPG, AVI, ...), keypoint saving (JSON, XML, YML, ...), keypoints as array class, and support to add your own custom output code (e.g., some fancy UI).

**OS**: Ubuntu (20, 18, 16, 14), Windows (10, 8), Mac OSX, Nvidia TX2.

**Hardware compatibility**: CUDA (Nvidia GPU), OpenCL (AMD GPU), and non-GPU (CPU-only) versions.

**Usage Alternatives**:
- [**Command-line demo**](doc/01_demo.md) for built-in functionality.
- [**C++ API**](doc/04_cpp_api.md/) and [**Python API**](doc/03_python_api.md) for custom functionality. E.g., adding your custom inputs, pre-processing, post-posprocessing, and output steps.

For further details, check the [major released features](doc/07_major_released_features.md) and [release notes](doc/08_release_notes.md) docs.



## Related Work
- [**OpenPose training code**](https://github.com/CMU-Perceptual-Computing-Lab/openpose_train)
- [**OpenPose foot dataset**](https://cmu-perceptual-computing-lab.github.io/foot_keypoint_dataset/)
- [**OpenPose Unity Plugin**](https://github.com/CMU-Perceptual-Computing-Lab/openpose_unity_plugin)
- OpenPose papers published in **IEEE TPAMI and CVPR**. Cite them in your publications if OpenPose helps your research! (Links and more details in the [Citation](#citation) section below).



## Installation
If you want to use OpenPose without installing or writing any code, simply [download and use the latest Windows portable version of OpenPose](doc/installation/0_index.md#windows-portable-demo)!

Otherwise, you could [build OpenPose from source](doc/installation/0_index.md#compiling-and-running-openpose-from-source). See the [installation doc](doc/installation/0_index.md) for all the alternatives.



## Quick Start Overview
Simply use the OpenPose Demo from your favorite command-line tool (e.g., Windows PowerShell or Ubuntu Terminal). E.g., this example runs OpenPose on your webcam and displays the body keypoints:
```
# Ubuntu
./build/examples/openpose/openpose.bin
```
```
:: Windows - Portable Demo
bin\OpenPoseDemo.exe --video examples\media\video.avi
```

You can also add any of the available flags in any order. E.g., the following example runs on a video (`--video {PATH}`), enables face (`--face`) and hands (`--hand`), and saves the output keypoints on JSON files on disk (`--write_json {PATH}`).
```
# Ubuntu
./build/examples/openpose/openpose.bin --video examples/media/video.avi --face --hand --write_json output_json_folder/
```
```
:: Windows - Portable Demo
bin\OpenPoseDemo.exe --video examples\media\video.avi --face --hand --write_json output_json_folder/
```

Optionally, you can also extend OpenPose's functionality from its Python and C++ APIs. After [installing](doc/installation/0_index.md) OpenPose, check its [official doc](doc/00_index.md) for a quick overview of all the alternatives and tutorials.




## Citation
Please cite these papers in your publications if OpenPose helps your research. All of OpenPose is based on [OpenPose: Realtime Multi-Person 2D Pose Estimation using Part Affinity Fields](https://arxiv.org/abs/1812.08008), while the hand and face detectors also use [Hand Keypoint Detection in Single Images using Multiview Bootstrapping](https://arxiv.org/abs/1704.07809) (the face detector was trained using the same procedure as the hand detector).

   

Paper links:
- OpenPose: Realtime Multi-Person 2D Pose Estimation using Part Affinity Fields:
    - [IEEE TPAMI](https://ieeexplore.ieee.org/document/8765346)
    - [ArXiv](https://arxiv.org/abs/1812.08008)
- [Hand Keypoint Detection in Single Images using Multiview Bootstrapping](https://arxiv.org/abs/1704.07809)
- [Realtime Multi-Person 2D Pose Estimation using Part Affinity Fields](https://arxiv.org/abs/1611.08050)
- [Convolutional Pose Machines](https://arxiv.org/abs/1602.00134)



## License
OpenPose is freely available for free non-commercial use, and may be redistributed under these conditions. Please, see the [license](./LICENSE) for further details. Interested in a commercial license
