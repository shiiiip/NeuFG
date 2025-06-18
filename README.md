# NeuFG
We establish a new neural 3D reconstruction theoretical frame called neural fuzzy geometric representation (NeuFG), which is a special type of implicit representation of geometric scene that only takes value in [0, 1]. 

This is the official repo for the implementation of **NeuFG: Neural Fuzzy Geometric Representation for Multi-View Reconst**.


## Setup
### Installation  
This code is built with pytorch 1.12.0 and pytorch3d 0.7.1. You can build the environment by running: 
```  
conda create -n geoneus python=3.7  
conda activate geoneus  
conda install pytorch==1.11.0 torchvision==0.12.0 cudatoolkit=11.3 -c pytorch  
conda install fvcore iopath  
conda install -c bottler nvidiacub  
conda install pytorch3d -c pytorch3d  
pip install -r requirements.txt  
```  
<details>
  <summary> Dependencies </summary>

  -imageio==2.9.0
  -matplotlib==3.4.2
  -open3d==0.9.0
  -opencv_python==4.5.3.56
  -plotly==5.1.0
  -pyhocon==0.3.58
  -icecream==2.1.0
  -scikit_image==0.18.2
  -scikit_learn==1.0.1
  -scipy==1.7.1
  -trimesh==3.9.26
  -PyMCubes==0.1.2
  -pandas==1.3.5
  -tensorboard
</details>

## Data Download 
the DTU data from [Google Drive](https://drive.google.com/drive/folders/1p7Vq6VAm1g_qCJcHLeXeGXc0qEkO4Rme?usp=sharing), which provides the files on sparse points and image pairs. 
You can place the data in the publicdata folder or you can change the confs to specify the location of the data. 

## Running 
- Training 
```
python exp_runner.py --mode train --conf ./confs/womask.conf --case <case_name>
```  
- Extract surface from trained model
```
python exp_runner.py --mode validate_mesh --conf ./confs/womask.conf --case <case_name> --is_continue
```
- Evaluation
```
python eval.py --conf ./confs/womask.conf --case <case_name>
```
And you can add --gpu to choose the GPU you want to use. 

## Acknowlegement
Our code is partially based on [NeuS](https://github.com/Totoro97/NeuS) project and some code snippets are borrowed from [GeoNeus](https://github.com/GhiXu/Geo-Neus). The eval code is borrowed from [DTUeval-python](https://github.com/jzhangbs/DTUeval-python). Thanks for the authors of these great projects.
