# Mouse_behavioral_annotation
The "Mouse behavioral annotation" repository is dedicated to developing and implementing a pipeline that can help annotate mouse behaviors.

## Step 1: Boris annotation
BORIS can be downloaded using the following link
https://www.boris.unito.it/

A detailed guide regarding the usage of boris can be found here. 
https://www.boris.unito.it/user_guide/pdf/boris_user_guide.pdf#page=3.14

## Step 2: LabelMe annotation
LabelMe works great for bbox and keypoints annotation, 
LabelMe can be downloaded from https://github.com/labelmeai/labelme
Instruction regarding how to use LabelMe has been detailed in the official website.
After annotation, we converted the annotation to COCO format using the labelme2coco package
https://github.com/fcakyon/labelme2coco


## Step 3: Training a FasterRCNN Mouse Detection Head
The fasterRCNN model was trained using the openmmlab in a GPU machine
First create a virtual environment
```python
conda create --name openmmlab python=3.8 -y
conda activate openmmlab
```
Then 
```python
conda install pytorch torchvision -c pytorch
```
Then 
```python
pip install -U openmim
mim install mmengine
mim install "mmcv>=2.0.0"
```
final step is to install the mmdetection
```python
git clone https://github.com/open-mmlab/mmdetection.git
cd mmdetection
pip install -v -e .
```
The configuration file and the trained model can be found in the the github folder






## Step 4: Training a HRnet keypoint detection model
The HRnet keypoint detection model was training using the 

## Step 5: A SAM + FasterRCNN based tracking model
This step requires a GPU machine to work.
First, let's install anaconda
```python
https://www.anaconda.com/download/success
```
Then, let's install cuda 11.8
```python
https://developer.nvidia.com/cuda-11-8-0-download-archive
```
In the anaconda prompt, you can check the cuda using
```python
nvidia-smi
```
This one would display the GPU status as follows, you can have a different GPU model and CUDA version depends on your system.
Mon Aug  5 12:21:34 2024
+---------------------------------------------------------------------------------------+
| NVIDIA-SMI 536.23                 Driver Version: 536.23       CUDA Version: 12.2     |
|-----------------------------------------+----------------------+----------------------+
| GPU  Name                     TCC/WDDM  | Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp   Perf          Pwr:Usage/Cap |         Memory-Usage | GPU-Util  Compute M. |
|                                         |                      |               MIG M. |
|=========================================+======================+======================|
|   0  NVIDIA GeForce RTX 3070      WDDM  | 00000000:01:00.0 Off |                  N/A |
|  0%   42C    P8               7W / 220W |      0MiB /  8192MiB |      0%      Default |
|                                         |                      |                  N/A |
+-----------------------------------------+----------------------+----------------------+
|   1  NVIDIA GeForce RTX 3070      WDDM  | 00000000:4B:00.0  On |                  N/A |
|  0%   54C    P8              24W / 220W |   6404MiB /  8192MiB |     14%      Default |
|                                         |                      |                  N/A |
+-----------------------------------------+----------------------+----------------------+





python version 3.11
CUDA version 11.8

```python
pip install torch==2.3.1 torchvision==1.18.1  torchaudio=2.3.1 –index-url https://download.pytorch.org/whl/cu118
```

The SAM for video model can be downloaded through 
```python
https://dl.fbaipublicfiles.com/segment_anything_2/072824/sam2_hiera_large.pt
```

## Step 6: Differentiation of sniffing and grooming behavior


## Step 7: Visualization of annotated behaviors 


## Step 8: Verifcation by human annotator
