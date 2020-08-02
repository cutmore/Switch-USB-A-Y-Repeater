## A/Y Repeater

Automatically press A/Y then repeat on Nintendo Switch using an Arduino Leonardo via USB input

[![IMAGE ALT TEXT HERE](https://i.ibb.co/8jKBBkz/883-04.jpg)](https://www.youtube.com/watch?v=udo8mv5oarg)

## How to install Window

This has been tried and Tested on Windows 10 platform, in theory you can achieve the belwo on any platform - but for now the guide is focused on the most common OS. :)

#### 1. Windows Subsystem for Linux

Enable

![IMAGE ALT TEXT HERE](https://raw.githubusercontent.com/cutmore/Switch-USB-A-Y-Repeater/master/Images_for_readme/Windows_Features.png)

#### 2. Ubuntu from Windows Store

Install.

![IMAGE ALT TEXT HERE](https://raw.githubusercontent.com/cutmore/Switch-USB-A-Y-Repeater/master/Images_for_readme/Ubuntu.png)

#### 3. Open Ubuntu

Should be presented within something similar to below:

If this is your firstname running, you may be asked to set up some user information - please do this.

*INSERT IMAGE HERE*

#### 4. Install required libraries

sudo apt-get install make gcc-avr avrdude avr-libc 

![IMAGE ALT TEXT HERE]https://raw.githubusercontent.com/cutmore/Switch-USB-A-Y-Repeater/master/Images_for_readme/apt_get_install.png

<div class="text-white bg-red mb-2">
  .text-white on .bg-red
</div>

#### 5. MAKE

Go to the directory where you installed the repository and type 'make', if should complete with no errors.

*INSERT IMAGE HERE*

This will create a Joytick.hex, please copy this somewhere into the Windows Directories, as you will need to access this in a little bit.

(TIP: Windows Directories are found at /mnt/c/)

#### 6. Install Arduino IDE

https://www.arduino.cc/

#### 7. Open IDE, and Enable Verbose During Upload

File -> Preferences:

Show verbose output during: upload <- Tick this

*INSERT IMAGE HERE*

#### 8. Ensure Arduino is recongised

Selct the right Arduion, and COM port and upload any old random sketch to Arduion

#### 9. AVRDUDE

Search the log, you're looking for something that looks like the below

*INSERT IMAGE HERE*

C:\Program Files (x86)\Arduino\hardware\tools\avr/bin/avrdude -CC:\Program Files (x86)\Arduino\hardware\tools\avr/etc/avrdude.conf -v -patmega32u4 -cavr109 -PCOM6 -b57600 -D -Uflash:w:C:\Users\chris\AppData\Local\Temp\arduino_build_650835/sketch_jul09a.ino.hex:i 

You'll then need to start making this appropriate for you:
(As an example below)

avrdude.exe -CC:\Program Files (x86)\Arduino\hardware\tools\avr/etc/avrdude.conf -v -patmega32u4 -cavr109 -PCOM6 -b57600 -D -Uflash:w:C:\Users\chris\AVRDUDE\Joystick.hex:i 

#### 10. Upload to board

You'll need to hit the reset button on the Leonardo, and then execute the above avrdude command that you've just built.

Arduino must be in reset mode for this to work.
(Arduino IDE is able to put the board into upload mode, but as we're using avrdude directly - we must do this manually)

*INSERT VIDEO HERE*

