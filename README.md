# rolandPK-5onRPI
Headless synthesizer on RPI for Roland PK-5 midi pedals.

Hardware:
*Raspberry PI 3
*Roland PK-5
*Miditech midilink mini

RPI OS Raspbian
Libs:
Fluidsynth
libasound2-dev Alsa (https://github.com/alsa-project)
XXXXXXXXXXlib2

A soundbank for organ sounds is imported into fluidsynth, most projects feature a hammond organ soundbank. I want this project to complete our casio privia organ sound so we try to find a soundbank that is matching to that soundbank.

Fluidsynth default drivers are 'jack', these are not supported on Raspbian so we change this to Alsa, alsa is included in the libasound2-dev library.

prompt: fluidsynth -a alsa -m alsa_seq

Python version:
>>> import fluidsynth
>>> import time
>>> fs = fluidsynth.Synth()
>>> fs.start(driver='alsa')

When trying the hardware on a PC with fruityloops, the default windows drivers had too much latency for a meaningful playing experience.
I managed to change to better sound drivers on the PC to get an ok latency. This is ofcourse equally important when on a linux platform.

To do:
*Setup the midi signal input
*Read the midi signal in fluidsynth
*Make convenient daemon start process and settings

Known possible issues: Bad USB jacks give spike midi signals, these are very unpleasant to listen to. If you experience this you should replace the USB jack.
