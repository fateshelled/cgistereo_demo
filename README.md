# CGI-Stereo Inference DEMO

ONNX and TensorRT inference demo for [CGI-Stereo](https://github.com/gangweiX/CGI-Stereo).


<img src="https://github.com/fateshelled/cgistereo_onnx/blob/main/data/im0.png" width="320" height="240" alt=""><img src="https://user-images.githubusercontent.com/53618876/223908423-dbf68910-141f-4160-89b9-69722454f2f5.png" width="320" height="240" alt="">

<img src="https://github.com/fateshelled/cgistereo_onnx/blob/main/data/left.png" width="320" height="240" alt=""><img src="https://user-images.githubusercontent.com/53618876/223908408-22ca7389-a3e8-47cf-9bde-38782571444d.png" width="320" height="240" alt="">


## Requirements
- OpenCV
- numpy
- ONNXRuntime
- TensorRT
- pycuda

## Model Download
from [PINTO_model_zoo](https://github.com/PINTO0309/PINTO_model_zoo/tree/main/358_CGI-Stereo)

## Usage
### ONNXRuntime
```bash
usage: demo.py [-h] [-m MODEL_PATH] [-l LEFT_IMAGE] [-r RIGHT_IMAGE] [-o OUTPUT_PATH]

optional arguments:
  -h, --help            show this help message and exit
  -m MODEL_PATH, --model_path MODEL_PATH
                        ONNX model file path. (default: cgi_stereo_sceneflow_480x640/cgi_stereo_sceneflow_480x640.onnx)
  -l LEFT_IMAGE, --left_image LEFT_IMAGE
                        input left image. (default: data/left.png)
  -r RIGHT_IMAGE, --right_image RIGHT_IMAGE
                        input right image. (default: data/right.png)
  -o OUTPUT_PATH, --output_path OUTPUT_PATH
                        output colored disparity image paht. (default: output.png)
```

### TensorRT
#### Convert model
```bash
bash convert_onnx2trt.bash <onnx-model-path> <output-engine-path> 
```

#### Inference
```bash
usage: demo_trt.py [-h] [-e ENGINE_PATH] [-ih INPUT_HEIGHT] [-iw INPUT_WIDTH] [-l LEFT_IMAGE] [-r RIGHT_IMAGE] [-o OUTPUT_PATH]

optional arguments:
  -h, --help            show this help message and exit
  -e ENGINE_PATH, --engine_path ENGINE_PATH
                        TensorRT engine file path. (default: cgi_stereo_sceneflow_480x640.engine)
  -ih INPUT_HEIGHT, --input_height INPUT_HEIGHT
                        Model input height. (default: 480)
  -iw INPUT_WIDTH, --input_width INPUT_WIDTH
                        Model input width. (default: 640)
  -l LEFT_IMAGE, --left_image LEFT_IMAGE
                        input left image. (default: data/left.png)
  -r RIGHT_IMAGE, --right_image RIGHT_IMAGE
                        input right image. (default: data/right.png)
  -o OUTPUT_PATH, --output_path OUTPUT_PATH
                        output colored disparity image paht. (default: output.png)
```
