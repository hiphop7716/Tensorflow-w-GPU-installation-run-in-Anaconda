### Tensorflow w/ GPU 環境建置流程：
#### *建立一個使用tensorflow的Anaconda environment*
```shell
$ conda create -n {environment name} python=3.x
P.S. --name is equivalent to -n
$ conda activate {environment name created in step.1}
$ pip install tensorflow=2.6
```

#### *驗證是否有 GPU enable，接續輸入下列指令*
```shell
$ python
Python 3.9.12 (main, Apr  4 2022, 05:22:27) [MSC v.1916 64 bit (AMD64)] :: Anaconda, Inc. on win32 Type "help", "copyright", "credits" or "license" for more information.
```

#### *進入 Python shell*
```python
>>> import tensorflow as tf
>>> tf.__version__
'2.6.0'
(先暫停，跳到下方先確認是否安裝對應版本的CUDA toolkit & cuDNN)
>>> tf.test.is_gpu_available('GPU')
I tensorflow/core/common_runtime/gpu/gpu_device.cc:1532] Created device /device:GPU:0 with 8966 MB memory: -> device: 0, name: NVIDIA GeForce {graphic card type}, pci bus id: 0000:01:00.0, compute capability: 7.5 True <= 看到 True 代表有啟動
>>> tf.config_list_physical_devices('GPU')
[PhysicalDevice(name='/physical_device:GPU:0', device_type=('GPU')] <= 看到'GPU'代表有啟動
```

#### *針對有安裝顯示卡的設備，如要使用GPU加速，需要以下事項；反之，無顯示卡系統自動使用CPU mode運行模組 (以下連結請用ctrl+click開啟)*
- [![tf-windows](https://img.shields.io/badge/Refference-CPU%2FGPU%20support%20--%20Linux/MacOS%20-informational)](https://www.tensorflow.org/install/source) [![tf-win](https://img.shields.io/badge/Refference-CPU%2FGPU%20support%20--%20Windows%20-informational)](https://www.tensorflow.org/install/source_windows) 
- [![nvidia](https://img.shields.io/badge/Update-Nvidia%20latest%20version-blue.svg)](https://www.nvidia.com/zh-tw/geforce/drivers/)
- [![cuDNN](https://img.shields.io/badge/Downloads-cuDNN-red.svg)](https://developer.nvidia.com/rdp/cudnn-archive)
- [![cuda-toolkit](https://img.shields.io/badge/Downloads-cuda--toolkit-green)](https://developer.nvidia.com/cuda-downloads)
- **Ex:** ![example](https://img.shields.io/badge/Tensorflow-2.6-blue) ![example](https://img.shields.io/badge/cuDNN-8.1-red) ![example](https://img.shields.io/badge/CUDA-11.2-green)