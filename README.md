# LamboiseNet

*Master Thesis about Change Detection in Satellite Imagery using Deep Learning*

Héloïse BAUDHUIN - Antoine LAMBOT

### Description:

The aim of this thesis is to create a CNN capable of detecting new constructions in satellite imagery. More precisly, taking two satellite images taken at different times and output a segmentation mask with the contour of the new buildings. The model takes two RGB images of 650 x 650 as input and outputs a semgmentation mask of the same size.

![alt ](https://github.com/hbaudhuin/LamboiseNet/blob/master/Example/before.png?raw=true)
*First input: before image*

![alt ](https://github.com/hbaudhuin/LamboiseNet/blob/master/Example/after.png?raw=true)
*Second input: After image*

![alt ](https://github.com/hbaudhuin/LamboiseNet/blob/master/Example/gt.png?raw=true)
*Segmentation mask with the changes*

![alt ](https://github.com/hbaudhuin/LamboiseNet/blob/master/Example/output.png?raw=true)
*Mask output by the CNN*
 The CNN architecture we are using is the UNet++ with layers removed and the filter size reduced. This way the model fits on a GPU with 6G of memory. As you can see on the above pictures, our model manages to find the changes and produce a segmentation mask with their approximated shape.




### Requirements :

##### Dataset:
You need all the **Earth_*** (1-32) instances from the dataset.
They need to be in the DATA folder.

Link to the dataset : https://drive.google.com/drive/folders/1rd1vseWiFSqQc5-93XSRQW9Bzzcgqc6H?usp=sharing 

##### Weights and metrics:
If you want to run our already trained **Light UNet++** with the -reload argument, you need the following files :
- Weights/last.pth
- Loss/last.pth
- Loss/last_metrics.pth

Links to the files :

https://drive.google.com/drive/folders/1qbZm-b4gdhzzMCP09XwWx2wJKxsSXBJL?usp=sharing
https://drive.google.com/drive/folders/1-DdCZxCv7OInvpUnbbT-4p2Uhc_v6ztI?usp=sharing

##### Librairies:
- PyTorch (1.3.1+)
- numpy
- scikit-learn
- matplotlib
- imageio
- Pillow
- imgaug
- tqdm

### Usage :
## Predict

## Train
```
python3 train.py 
                [-h]
                [--epochs EPOCHS] 
                [--learning_rate LEARNING_RATE]
                [--n_data_augm N_DATA_AUGM] 
                [-reload] 
                [-save]
                
optional arguments:
  -h, --help            show this help message and exit
  --epochs EPOCHS       number of epochs the model will run (1 by default)
  --learning_rate LEARNING_RATE
                        starting learning rate (0.001 by default)
  --n_data_augm N_DATA_AUGM
                        number of data augmentation instances to generate per
                        original instance (2 by default)
  -reload               reload the model weights and metrics from the last run
                        (disabled by default)
  -save                 save the weights and metrics of the model when it has
                        finished running (disabled by default)
```

#### Licence : 
MIT
Copyright <2020> <Héloïse Baudhuin and Antoine Lambot>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE
