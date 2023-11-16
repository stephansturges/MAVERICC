     
     ___ ___ _______ ___ ___ _______ _______ ___ _______ _______ 
     |   Y   |   _   |   Y   |   _   |   _   |   |   _   |   _   |
     |.      |.  1   |.  |   |.  1___|.  l   |.  |.  1___|.  1___|
     |. \_/  |.  _   |.  |   |.  __)_|.  _   |.  |.  |___|.  |___ 
     |:  |   |:  |   |:  1   |:  1   |:  |   |:  |:  1   |:  1   |
     |::.|:. |::.|:. |\:.. ./|::.. . |::.|:. |::.|::.. . |::.. . |
     `--- ---`--- ---' `---' `-------`--- ---`---`-------`--------  


----------------------------------------------------------------------------

Machine Assisted Visual Extraction, Reconnaissance & Intelligence for Cosmic Captures

Release: V1.0 - Public 

I am assuming you have  some experience with deployment of AI systems, 
but if you have any trouble using this release you can contact me at 
stephan.sturges at gmail

----------------------------------------------------------------------------


WHAT IS MAVERICC?

MAVERICC is a detection AI model, based on a large YOLO-v7 backbone and my own
synthetic data pipeline. The basic model shared here, which is the only 
one published as FOSS at the moment, is capable of detecting ONLY PLANES in 
high resolution satellite imagery. The complete version (not free) can detect
16 classes, the same ones as my WALDO model.


----------------------------------------------------------------------------

WHERE IS MAVERICC?

Due to the size of the model files and the constraints of github LFS the files
are no longer stored directly on Github, please download the latest package 
using the link below:



----------------------------------------------------------------------------
FOR AI NERDS !

It's a big set of YOLOv7 model, trained on my own datasets of synthetic and "augmented" / semi-synthetic data.
I'm not going to release the dataset for the time being.


This public release comes with a full-sized Yolov7-e6e .pt model file. Do with it as you will!


----------------------------------------------------------------------------
HOW CAN I START WITH MAVERICC?  

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


----------------------------------------------------------------------------

CAN YOU HELP ME WITH X? 

Sure, email me at stephan.sturges@gmail.com


----------------------------------------------------------------------------

DETECTION OF X ISN'T WORKING AS EXPECTED:

I'd love to see example images, videos, sample data, etc at:
stephan.sturges@gmail.com


HOW DOES AIRCORTEX MAKE MONEY?

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

Contact me at stephan.sturges@gmail.com to find out more.

----------------------------------------------------------------------------
SUPPORT MAVERICC!

If you find value in it, please support development of the next version on:
https://ko-fi.com/stephansturges
----------------------------------------------------------------------------
LICENSE
----------------------------------------------------------------------------

Unless otherwise specified all code in this release is published with the 
licence conditions below.
----------------------------------------------------------------------------


MIT License

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

----------------------------------------------------------------------------

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
