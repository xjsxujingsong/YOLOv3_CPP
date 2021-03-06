YOLOv3 C++ 
=================

Torch (C++) implementation of YOLOv3, which works on `Windows`,`Mac`, `Linux`.

## Dependency

* cmake
* libTorch >= 1.3, or nightly
* OpenCV   >= 4.0
* C++17
* Win10: vs2019, passed
* Linux: 
  - g++ >=7.3.0
  - Pre-cxx11 ABI: passed
  - cxx11 ABI => `error`: libtorch.so: undefined reference to `lgammaf@GLIBC_2.23'
* MacOS: passed 

## Usage

For now, only support inference. Please use `Darknet` weights format as input.  

If you need training your own model, try [PyTorch-YOLOv3](https://github.com/eriklindernoren/PyTorch-YOLOv3/) and save your weights.  

To test all `jpg` format images in a folder, use your `yolo.custom.cfg` and `custom.weights`, run the code below:  


```shell
# yolov3 <config_file> <weights> <image_folder> 
yolov3.exe yolov3.cfg yolov3.weights images
```

## Build

```shell

# before running this project, you have to edit two file
# -> edit the CMakeList.txt, set correct path to libtorch and OpenCV
# -> edit the yolov3/main.cpp at line 27. Set correct image format. 
cd path/to/YOLOv3
mkdir build
cd build
cmake ..
make # linux, mac
# if windows, open YOLOV3-app.sln and then build 
```

## Performance
test code:
```
yolov3 models/yolov3.cfg models/yolov3.weights images
```

Results:

1. tested with CPU: `Core i9`
    - Windows
    - MAC: average time (682 ms/image).
    
2. tested with GPU: `Tesla V100`
    - Linux: average time (22 ms/image).


## Features
Supports  
- NMS
- Soft NMS
- Weighted NMS

## TODO
- Support training
- ...



## Credits

This repo is created based on the implementations below:  
[weixu000](https://github.com/weixu000/libtorch-yolov3-deepsort)  
[PyTorch-YOLOv3](https://github.com/eriklindernoren/PyTorch-YOLOv3)  
[YOLO_v3_tutorial_from_scratch](https://github.com/ayooshkathuria/YOLO_v3_tutorial_from_scratch)







