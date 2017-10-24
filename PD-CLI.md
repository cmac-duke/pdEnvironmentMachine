Running Pure Data from the CLI

Copy a patch from your mac/pc to your Pi:
scp ~/Desktop/filename.pd pi@ipAddress:~/Desktop/filename.pd

on your pi (via SSH): 
sudo apt-get install pure-data

Follow (replacing “nicorette.pd” with your patch name):
https://guitarextended.wordpress.com/2012/08/28/running-pd-on-a-headless-raspberry-pi/

Give your CPU more memory (we don’t need the GPU — lower the RAM allotment to 16)
https://guitarextended.wordpress.com/2012/09/11/setting-up-the-raspberry-pi-for-pd-1-allocate-more-ram-to-cpu/

sudo reboot

if experiencing substantial noise, try updating audio drivers: https://www.raspberrypi.org/forums/viewtopic.php?f=29&t=136445 
sudo rpi-update

In /boot/config.txt add the following line:
Code: Select all
audio_pwm_mode=2
Before using the audio for the first time, you should run amixer cset numid=3 1 to ensure that HDMI is not selected as the audio output path. OMXplayer should be forced to use "local" as the sound output route.
