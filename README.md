# PixelCanvasBot

This is a functional bot for pixelcanvas.io.
We will not provide you with a faster drawing.
It does not allow you to easily draw your image. You need to spend some effort.
This bot can draw images that you can't normally draw on your place.
 
### What you can do with this?
Well, you can draw some image and try replicate in pixelcanvas.io. You can combine with your friends or clan, whatever for combine forces to draw more quickly or defend your 'territory'.

### I can use any image and this bot will draw for me?
You can use any image. 
Converted your image colors to nearest PixelCanvas.io color for every pixel.
Conversion result images if not exist in ./img/.cache folder created.
You can interfere with this file or you can preview it to be drawn.

# Installation

## get python
install python for yours operation systems in here https://www.python.org/downloads/release/python-2713/
Recomments 'Python 2.7' 32bit versions,
Important Python 3 not supported (Help wanted a few critical error) 

## Download bot

### With git
PixelCanvas.io frequently changes the API validation system.
We are updated after we notice. It can be a bit late, we can not guarantee it in any way. Recommend GIT for the current use

#### If you have not installed git?
* get git and install from https://git-scm.com/downloads

#### Clone bot
Open Terminal (git bash, cmd vs.)
enter this command

* git clone https://github.com/RogerioBlanco/PixelCanvasBot.git

### Optional downlad from release
https://github.com/RogerioBlanco/PixelCanvasBot/archive/v1.0.zip

## Setup bot 
go bot directory

* cd PixelCanvasBot
* python ./setup.py

# Using

## Geting yours fingerprint Chrome or chromium
* go http://pixelcanvas.io/@0,0
* press **F12**
* open **network** tab
* in **filter** input paste '**pixel**'
* put yours pixel any coordinates
* click request name *pixel*
* open **headers** tab
* your fingerprint is under **Request Playload**

![image](https://user-images.githubusercontent.com/12828465/28237968-24ca07cc-694a-11e7-9df3-32b4d737b44e.png)

## Easy to use, only required parameters:

* python ./main.py -i image.png -f $FINGERPRINT$ -x 0 -y 0

## What is each parameter? 
    Need to help?
    Try it 'python ./main.py --help' maybe more usefull.
* [required] **-i** or **--image**          it is the image you want to draw.

* [required] **-f** or **--fingerprint**    it is your unique code. You can get in the requisition when you open Chrome DevTools.

* [required] **-x** or **--start_x**        it is the point X axis what you want to begin. Ex: 156

* [required] **-y** or **--start_y**        it is the point y axis what you want to begin. Ex: -4000

* [optional] **--colors_ignored**           Ignored current image colors For example image only black and red colors painting. Ex: 0 1 2   4   6 7 8 9 10 11 12 13 15

* [optional] **--colors_not_overwrite**     Ignored pixelcanvas.io colors For example only black colors removing if this image image not equals black. Ex: 0 1 2   4 5 6 7 8 9 10 11 12 13 15

* [optional] **--draw_strategy**            draw strategy default by: *randomize* Avaiable strategy list : 

    * *linear* :    line by line paint, 

    * *qf* :        Quickfill line by line. Will draw a 3x3 square in this order:

            | 1 | 6 | 2 |
            | 7 | 3 | 8 |
            | 4 | 9 | 5 |

    * *randomize* : pixel paint random coordinates, 
    
    * *status* :    not painted only list paint status --support colors ignored parameters, don't suppurt sketch mode--
    
    * *sketch* :    Don't fill image drawing image only bordes. see more information https://github.com/RogerioBlanco/PixelCanvasBot/issues/6
    
    * *detect* :    Wait time detector. Don't fill image drawing random color pixel to random coordinates evry time. Ignore start point and ignore image. this strategy return wait time in any coordinates with pixelcanvas.io
    
    * *tlc* :       Print start fill Top Left Corner -randomize tracking select all pixel-
        
    * *trc* :       Print start fill Top Right Corner -randomize tracking select all pixel-
        
    * *blc* :       Print start fill Bottom Left Corner -randomize tracking select all pixel-
        
    * *brc* :       Print start fill Bottom Right Corner -randomize tracking select all pixel-

    * *cnb* :       Print start fill Centre North Boundary -randomize tracking select all pixel-

    * *csb* :       Print start fill Centre South Boundary -randomize tracking select all pixel-

    * *cwb* :       Print start fill Centre West Boundary -randomize tracking select all pixel-

    * *ceb* :       Print start fill Centre East Boundary -randomize tracking select all pixel-

    * *cpd* :       Print start fill Centre Point Domain -randomize tracking select all pixel-
#### Note:
The rcm-domain based strategyes are defined using a number of reference points shown in the figure below:
![image](http://cordex-australasia.wdfiles.com/local--files/rcm-domains/CORDEXDomainDef.jpg)
Good and half randomize drawing but maybe a big image bad performance problems.  

#### Detect mode maybe alternative using. RANDOM COLOR BOMP, need 2 parameters
For example this result for *--draw_strategy detect --detect_area_min_range 4800 --detect_area_max_range 4825* parameters.
visit at http://pixelcanvas.io/@4800,4800    
    
* [optional] **--mode_defensive**           is the mode who put the program mode deamon. Default: True

* [optional] **--proxy_url**                it is you proxy. Ex: proxy.yourcompany.com:8080

* [optional] **--proxy_auth**               it is your credentials for the proxy. Ex: username:password

* [optional] **--round_sensitive**          it is color rounding sensitive option. Need this number > 0 ex: 3

* [optional] **--image_brightness**         it is change image brignets, Support negative values ex: 15 or -15
#### Note:
*--round_sensitive* *--image_brightness* parameters to You can change the degree of rounding precision,
or you can make the picture that is to be drawn darker - lighter.
see work result: https://github.com/RogerioBlanco/PixelCanvasBot/issues/45


* [optional] **--detect_area_min_range**     Support negative values ex: 3000 or -3000 Default -3000 max avaliable value 999999 / -999999

* [optional] **--detect_area_max_range**     Support negative values ex: 3000 or -3000 Default 3000 max avaliable value 999999 / -999999
#### Note:
*--detect_area_min_range* *--detect_area_max_range* parameters only work at *detect* strategyes

* [optional] **--QR_text**     Your url or some text value Generate PNG image this bots ./img/QRcode.png images And drawing new generatied image to other parameters.
Important this value changing image file and ignoring *-i* parameters value For example '-i j:\\asfdas --QR_text http://github.com' Working with QRcode image. 

* [optional] **--QR_scale**    QRcode image size Default 3 this value pxel based. '1' to min image size 

# Update bot with last changes
### Clear local changes (if you changes source code) 
* git reset --hard
### Update from server server
* git pull -ff
# External: thanks for reference
https://github.com/possatti/pixelbot/blob/master/README.md 
