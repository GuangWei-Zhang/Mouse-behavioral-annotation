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
