Yolov8’s original model includes post-processing. Some shapes exceed the matrix calculation limit of 3588, so some cropping of the output layer is required.





pt to onnx





Clone ultralytics\_yolov8 repository and pull docker





docker pull kaylor/rk3588\_pt2onnx

git clone https://github.com/airockchip/ultralytics\_yolov8.git

cd ultralytics\_yolov8

git checkout 5b7ddd8f821c8f6edb389aa30cfbc88bd903867b





Download the newest model files from Yolov8 github repository.







For example, I download the model named yolov8n.pt









wget https://github.com/ultralytics/assets/releases/download/v8.1.0/yolov8n.pt





Edit ./ultralytics/cfg/default.yaml, replace "yolov8m-seg.pt" with "yolov8n.pt"









model: yolov8n.pt # (str, optional) path to model file, i.e. yolov8n.pt, yolov8n.yaml





Convert pt to onnx...







\# run the command in your host 

docker run -it -v ${PWD}:/root/ws kaylor/rk3588\_pt2onnx bash

----------------------------------

\# run commnads in your container

cd /root/ws

export PYTHONPATH=./ 

python ./ultralytics/engine/exporter.py

exit





onnx to rknn



onnx 到 rknn



Clone rk3588-convert-to-rknn repository and pull docker







cd ../

docker pull kaylor/rk3588\_onnx2rknn # for yolov8 

docker pull kaylor/rk3588\_onnx2rknn:beta # for yolov10

git clone https://github.com/kaylorchen/rk3588-convert-to-rknn.git

cp ultralytics\_yolov8/yolov8n.onnx rk3588-convert-to-rknn

cd rk3588-convert-to-rknn





Convert onnx to rknn



将 onnx 转换为 rknn





\# run the command in your host 

docker run -it -v ${PWD}:/root/ws kaylor/rk3588\_onnx2rknn bash # for yolov8

docker run -it -v ${PWD}:/root/ws kaylor/rk3588\_onnx2rknn:beta bash # for yolov10

docker run -it -v ${PWD}:/root/ws kaylor/rk3588\_onnx2rknn:2.3.0 bash # for all the yolos

----------------------------------

\# run commnads in your container

cd /root/ws

python convert.py yolov8n.onnx rk3588 i8 yolov8n.rknn

exit





