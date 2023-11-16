     
     888b     d888        d8888 888     888 8888888888 8888888b.  8888888 .d8888b.   .d8888b.  
     8888b   d8888       d88888 888     888 888        888   Y88b   888  d88P  Y88b d88P  Y88b 
     88888b.d88888      d88P888 888     888 888        888    888   888  888    888 888    888 
     888Y88888P888     d88P 888 Y88b   d88P 8888888    888   d88P   888  888        888        
     888 Y888P 888    d88P  888  Y88b d88P  888        8888888P"    888  888        888        
     888  Y8P  888   d88P   888   Y88o88P   888        888 T88b     888  888    888 888    888 
     888   "   888  d8888888888    Y888P    888        888  T88b    888  Y88b  d88P Y88b  d88P 
     888       888 d88P     888     Y8P     8888888888 888   T88b 8888888 "Y8888P"   "Y8888P"  


**Machine Assisted Visual Extraction, Reconnaissance & Intelligence for Cosmic Captures
**

----------------------------------------------------------------------------

![ApNewsroom_Russia_Ukraine_War_47540](https://github.com/stephansturges/MAVERICC/assets/20320678/27b5ad7f-8fe7-45ec-bfe9-9da195b522ff)

----------------------------------------------------------------------------


**Release: V1.0 - Public Version
**
I am assuming you have  some experience with deployment of AI systems, 
but if you have any trouble using this release you can contact me at 
stephan.sturges at gmail

----------------------------------------------------------------------------


**WHAT IS MAVERICC?
**
MAVERICC is a detection AI model, based on a large YOLO-v7 backbone and my own
synthetic data pipeline. The basic model shared here, which is the only 
one published as FOSS at the moment, is capable of detecting ONLY PLANES in 
high resolution satellite imagery. 

The complete version (not free) can detect 16 classes, the same ones as my WALDO model:

car / van / truck / human / gas tank / digger / container / bus / utility pole / boat /
bike / smoke / solar panels / military vehicle / plane 

This free model is only trained for "plane" class. 

----------------------------------------------------------------------------

**WHERE IS MAVERICC?
**
Due to the size of the model files and the constraints of github LFS the files
are no longer stored directly on Github, please download the latest package 
using the link below:



----------------------------------------------------------------------------
**FOR AI NERDS !
**

It's a big set of YOLOv7 model, trained on my own datasets of synthetic and "augmented" / semi-synthetic data.
I'm not going to release the dataset for the time being.


This public release comes with a full-sized Yolov7-e6e .pt model file. 


----------------------------------------------------------------------------
**HOW CAN I START WITH MAVERICC?  
**

1. Clone the Yolov7 repo into your MAVERICC folder:

git clone https://github.com/WongKinYiu/yolov7.git

2. install requirements for yolov7

cd yolov7
pip3 install -r requirements.txt

3. run MAVERICC using the detect.py script, pointing to the model weights file and to your image folder:

python3 detect.py --weights ../V7-e6e/yolov7-M1-planeOnly-960--e6e-bs20-150it/yolov7-M1-planeOnly-960--e6e-bs20-150it.pt --source ../input_images/ --project ../output_images/ --conf-thres 0.1

In the example above we are running the model with a confidence threshold of 0.1. Check out
the command-line arguments in the detect.py file to see how you want to use it!

4. Check out some cool outputs in yout ../output_images/ folder!
   
![BoeingPlaza_800](https://github.com/stephansturges/MAVERICC/assets/20320678/eb45ef15-dcf8-4bce-96a7-82b03494d39c)
![original](https://github.com/stephansturges/MAVERICC/assets/20320678/46456e73-9a3e-403b-8f8a-07979e529533)
![zkzq2ph-021sizeoriginal](https://github.com/stephansturges/MAVERICC/assets/20320678/c683fab3-3bc1-49e4-bdd8-19984c6cb765)
![1699882947130](https://github.com/stephansturges/MAVERICC/assets/20320678/f1489bcb-00e7-4dd1-a8ec-198c71dc0d6a)
![31268fe1806fd747628c49226e81eac82c99362b](https://github.com/stephansturges/MAVERICC/assets/20320678/4990ab3c-c167-4747-a78a-d4d2912dac5e)


----------------------------------------------------------------------------

**PRO TIP: for large images use a sliding-window inference mecanism, slicing the input images into smaller pieces. 
**
See below, this is with some smart sliding windo inference:
![prediction_visual](https://github.com/stephansturges/MAVERICC/assets/20320678/78d29fed-bf62-4a73-83ca-91faaf39c2fe)

Now the same image processed "naively" with the network:
![Heathrow-London](https://github.com/stephansturges/MAVERICC/assets/20320678/93e7dafe-eca8-4d4b-bac1-5b68ce76a0f4)

Notice the sliding-window inference catches the small obects much better, despite this image being super low-rez:

![image](https://github.com/stephansturges/MAVERICC/assets/20320678/dcc3ffcf-c548-4b01-a29d-07c3396bada0)


----------------------------------------------------------------------------

**CAN YOU HELP ME WITH X? 
**
Perhaps! email me at stephan.sturges at gmail

----------------------------------------------------------------------------

**DETECTION OF X ISN'T WORKING AS EXPECTED:
**
I'd love to see example images, videos, sample data, etc at:
stephan.sturges@gmail.com

**HOW DOES AIRCORTEX MAKE MONEY?
**

Aircortex' mission statement is to make the SOTA in ground-risk AI and sensing,
and to make the basic models free and easy to use for both hobbyists and 
professionals in the UAV / AAM industry, to acclerate safe access to the skies
in the 21st century.


Aircortex is an "open-core" AI company: the basic model is completely
free and open-source for anyone to use including in commercial products.

I make money by charging for: 
1. help with training additional detection classes, 
2. retraining for your specific hardware, 
3. building the software stack to support specific deployment cases, 
4. helping companies set up the right hardware architecture for AI integration,
5. custom hardware setups for specific environments
6. more "feature-complete" versions of my FOSS products such as integrating 3D perception
etc... 

Contact me to find out more.

----------------------------------------------------------------------------
**SUPPORT MAVERICC!
**
If you find value in it, please support development of the next version on:
https://ko-fi.com/stephansturges

----------------------------------------------------------------------------

**LICENSE
**
----------------------------------------------------------------------------

Unless otherwise specified all code in this release is published with the 
licence conditions below.
----------------------------------------------------------------------------


**MIT License
**

Copyright (c) 2023 Stephan Sturges / Aircortex.com 

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.


    ................................................................................
    ................................................................................
    .................................... ...........................................
    ..................::^^~~!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!~~^^::....................
    ..............:!JY55PGP555555555555PP7^~~~5PP5555555555555YYYYJ?!^..............
    ...........:^75PP55YY5PGPYYJJJJJJJJJ5Y!!!?555YYYYYYYYYYYYYY5GP5YYY?~:...........
    ..........:PGBPYYYYYJJJYPG5JJJJJ????YPJ7?55YYYYYYYJJJJJJJYGGYJJJJJPGG?..........
    ...........~YPYJJJJJJJJJJYYJ???????7PJ.. !G5JJJJJJJJJJJJJYYJ?J????YPY~..........
    ........... ^PJJJ?????????77777777!?5:....7BY?????????????????????JY............
    .............JY??7777777!!!!!!!!~~!5^ .....?G?7777777777777777777!J!............
    .............:J?!!!!!!~~~~~~~~^^^~Y^ .......757~!!!!!!~~~~~~~~~~~7?.............
    ..............:??!~^^^^^^^:::::^!?: ........ ^J?~^^^^^^^^^^^^^^~7?..............
    ................^!77!!!~~~~~!!77~............ .~?7!!~~~^^^~~~!77~...............
    ...................::^^^^~~^^::..................:^~!!!!!~~~^::.................
    ................................................................................
    ................................................................................
