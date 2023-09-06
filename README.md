# CascadeTabNet

## 简介

这个仓库仅完成了CascadeTabNet的推理部分，CascadeTabNet是一种用于端到端表格检测和结构识别的方法。它的原论文为[CascadeTabNet: An approach for end-to-end table detection and structure recognition from image-based documents](https://arxiv.org/abs/2004.12629)。你可以在[原作者的GitHub仓库](https://github.com/DevashishPrasad/CascadeTabNet/tree/master)上找到源代码和更多细节。也可在[这篇知乎](https://zhuanlan.zhihu.com/p/654721103)找到更具体的实现原理。

## 实验环境

- PyTorch = 1.5.1
- Python = 3.8 (在ubuntu18.04上测试)
- CUDA = 10.1

## 如何使用

本仓库仅用于展示如何使用已经训练好的模型进行推理。如果你想进行训练、评估等其他操作，请查看[原仓库](https://github.com/DevashishPrasad/CascadeTabNet/tree/master)中的详细文档。

### 示例模型权重文件

你可以从以下链接下载示例模型权重文件：[示例模型权重文件](https://drive.google.com/u/0/uc?id=1-QieHkR1Q7CXuBu4fp3rYrvDG9j26eFT)

### 注意事项

由于版本兼容性问题，你需要在以下文件中将`AT_CHECK`替换为`TORCH_CHECK`：

- `mmdetection/mmdet/ops/dcn/deform_conv.py`
- `mmdetection/mmdet/ops/dcn/deform_pool.py`
- `mmdetection/mmdet/ops/roi_align/src/roi_align_cuda.cpp`
- `mmdetection/mmdet/ops/nms/src/nms_cuda.cpp`
- `mmdetection/mmdet/ops/roi_pool/src/roi_pool_cuda.cpp`
- `mmdetection/mmdet/ops/masked_conv/src/masked_conv2d_cuda.cpp`
- `mmdetection/mmdet/ops/carafe/src/carafe_cuda.cpp`
- `mmdetection/mmdet/ops/carafe/src/carafe_naive_cuda.cpp`

更多具体步骤请查看 `demo.ipynb`。

### 示例推理结果

使用模型对示例图片进行推理，以下是推理结果示例：

![result_image.jpeg](https://s1.imagehub.cc/images/2023/09/06/result_image.jpeg)
