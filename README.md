# tract-paddle-repro

A minimal reproduction of an issue observed with the tract runtime using PaddleOCR

## Setup

Be sure to create and use an appropriate conda env by running

```sh
conda env create --file environment-3.9.yml
conda activate python-3.7
```

## Background

The `onnx` models were generated using [these instructions](https://github.com/PaddlePaddle/PaddleOCR/blob/release/2.6/deploy/paddle2onnx/readme.md).

## Working Python Version

To see an example of the `onnx` models working in python onnx inference engine, run:

```sh
cd PaddleOCR
python3.7 tools/infer/predict_system.py --use_gpu=False --use_onnx=True \
  --det_model_dir=../det_onnx/model.onnx  \
  --rec_model_dir=../rec_onnx/model.onnx  \
  --cls_model_dir=../cls_onnx/model.onnx  \
  --image_dir=doc/imgs_en/img_12.jpg \
  --rec_char_dict_path=ppocr/utils/en_dict.txt \
  --rec_image_shape='3,32,320
```

## Tract Errors
