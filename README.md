# TensorFlow_Lite_Classification_Jetson-Nano
![output image]( https://qengineering.eu/images/SchoolbusUb.png )<br/>
## TensorFlow Lite classification running on a Jetson Nano
[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)<br/><br/>
A fast C++ implementation of TensorFlow Lite classification on a Jetson Nano.<br/>
Once overclocked to 2015 MHz, the app runs at 50 FPS.
Special made for a Jetson Nano see [Q-engineering deep learning examples](https://qengineering.eu/deep-learning-examples-on-raspberry-32-64-os.html) <br/>

------------

Papers: https://arxiv.org/pdf/1712.05877.pdf <br/>
Training set: COCO with 1000 objects<br/>
Size: 224x224 <br/>

------------

## Benchmark.
| CPU 2015 MHz | GPU 2015 MHz | CPU 1479 MHz | GPU 1479 MHZ | RPi 4 64os 1950 MHz |
|  :------------: | :-------------: | :-------------:  | :-------------: | :-------------: |
|  50 FPS | -- FPS  | 36.3 FPS | -- FPS  | 38.5 FPS |

------------

## Dependencies.
To run the application, you have to:
- TensorFlow Lite framework installed. [Install TensorFlow Lite](https://qengineering.eu/install-tensorflow-2-lite-on-jetson-nano.html) <br/>
- Optional OpenCV installed. [Install OpenCV 4.5](https://qengineering.eu/install-opencv-4.5-on-jetson-nano.html) <br/>
- Code::Blocks installed. (```$ sudo apt-get install codeblocks```)

------------

## Running the app.
To extract and run the network in Code::Blocks <br/>
$ mkdir *MyDir* <br/>
$ cd *MyDir* <br/>
$ wget https://github.com/Qengineering/TensorFlow_Lite_Classification_Jetson-Nano/archive/refs/heads/main.zip <br/>
$ unzip -j master.zip <br/>
Remove master.zip and README.md as they are no longer needed. <br/> 
$ rm master.zip <br/>
$ rm README.md <br/> <br/>
Your *MyDir* folder must now look like this: <br/> 
tabby.jpeg <br/>
schoolbus.jpg <br/>
grace_hopper.bmp <br/>
Labels.txt <br/>
TensorFlow_Lite_Mobile.cpb <br/>
TensorFlow_Lite_Class.cpp<br/>
 <br/>
Next, choose your model from TensorFlow: https://www.tensorflow.org/lite/guide/hosted_models <br/> 
Download a quantized model, extract the .tflite from the tarball and place it in your *MyDir*. <br/> <br/>
Now your *MyDir* folder may contain: mobilenet_v1_1.0_224_quant.tflite. <br/>
Or: inception_v4_299_quant.tflite. Or both of course. <br/> <br/>
Enter the .tflite file of your choice on line 54 in TensorFlow_Lite_Class.cpp <br/>
The image to be tested is given a line 84, also in TensorFlow_Lite_Class.cpp <br/> <br/>
Run TestTensorFlow_Lite.cpb with Code::Blocks.<br/>
You may need to adapt the specified library locations in *TestTensorFlow_Lite.cpb* to match your directory structure.<br/><br/>
With the `#define GPU_DELEGATE` uncommented, the TensorFlow Lite will deploy GPU delegates, if you have, of course, the appropriate libraries compiled by bazel. [Install GPU delegates](https://qengineering.eu/install-tensorflow-2-lite-on-jetson-nano.html)

------------

[![paypal](https://qengineering.eu/images/TipJarSmall4.png)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=CPZTM5BB3FCYL) 
