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
The configuration file can be found in the the github folder

The trained detection head can be accessed here:
https://drive.google.com/drive/folders/1xghVPv2haytx1HxOOl0aD77w-fFzncdY?usp=sharing





## Step 4: Training a HRnet keypoint detection model
The HRnet keypoint detection model was training using the 

## Step 5: A SAM + FasterRCNN based tracking model
### SAM2_tutorial
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

Then open anaconda prompt, and create our virtual envioronment. 
```python
conda create -n SAM2_test python=3.11
```
Then activate virtual environment
```
conda activate SAM2_test
```
Get the SAM2 github files

```python
git clone https://github.com/facebookresearch/segment-anything-2.git
```
nevigate to the segment-anything-2 folder
```python
cd segment-anything-2
```
Install required packages
``` python
pip install torch==2.3.1 torchvision==0.18.1 torchaudio==2.3.1 --index-url https://download.pytorch.org/whl/cu118
pip install hydra-core
pip install tqdm
pip install matplotlib
pip install opencv-python
pip install ninja
pip install imageio
```

Then use the installation command, make sure that the the working directory is in the segment-anything-2 folder
```python
python setup.py build_ext --inplace
```

To test if the installation is successful or not, you can enter the python environment using 
```python
python
```
then type in
```python
import sam2
```
If you do not see any error message, it means you have successully installed SAM2


Download the SAM2 large model
```python
https://dl.fbaipublicfiles.com/segment_anything_2/072824/sam2_hiera_large.pt
```
and put the .pt file in the "...\segment-anything-2\checkpoints" folder

Now you can run the script and make predictions.

The SAM2_2obj_test_qt_GUI_csv_v3.py could track and segment 2 mice at the same time with zero shot capability. 


## Step 6: Differentiation of sniffing and grooming behavior


## Step 7: Visualization of annotated behaviors 


## Step 8: Verifcation by human annotator
