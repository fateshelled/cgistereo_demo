# cgistereo_onnx

ONNX inference demo for [CGI-Stereo](https://github.com/gangweiX/CGI-Stereo).


## Requirements
- OpenCV
- numpy
- onnxruntime

## Model Download
from [PINTO_model_zoo](https://github.com/PINTO0309/PINTO_model_zoo/tree/main/358_CGI-Stereo)

## Usage
```
usage: demo.py [-h] [-m MODEL_PATH] [-l LEFT_IMAGE] [-r RIGHT_IMAGE] [-o OUTPUT_PATH]

optional arguments:
  -h, --help            show this help message and exit
  -m MODEL_PATH, --model_path MODEL_PATH
                        ONNX model file path. (default: model.onnx)
  -l LEFT_IMAGE, --left_image LEFT_IMAGE
                        input left image. (default: data/left.png)
  -r RIGHT_IMAGE, --right_image RIGHT_IMAGE
                        input right image. (default: data/right.png)
  -o OUTPUT_PATH, --output_path OUTPUT_PATH
                        output colored disparity image paht. (default: output.png)
```
