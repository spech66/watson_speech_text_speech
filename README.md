# Speech to Text

This module provides a Node.js code to convert voice to text and back to voice using IBM Watson.
The code is based on the [tjbot example]( https://github.com/ibmtjbot/tjbot). 
The german tutorial is found at [SPech.de](http://www.spech.de/blog/article/spracherkennung-chatbot-watson-raspberry-pi)

**This will only run on the Raspberry Pi.**

##How It Works
- Listens for voice commands
- Sends audio from the microphone to the Watson Speech to Text Service - STT to transcribe [Watson Speech to Text](https://www.ibm.com/watson/developercloud/speech-to-text.html)
- Parses the text looking for the attention word
- Once the attention word is recognized the response is sent to [Watson Text to Speech](https://www.ibm.com/watson/developercloud/text-to-speech.html) to generate the audio file.
- The robot speaks the response via the Alsa audio playback tools

##Hardware

Raspberry Pi
USB Microphone

##Build

Install ALSA tools (required for recording audio on Raspberry Pi)

    sudo apt-get install alsa-base alsa-utils

Install Dependencies

    npm install

Add your Bluemix service credentials

    edit config.js
    enter your watson username, password and version.

##Running

Start the application

    sudo node speech_text_speech.js   

> Note the `sudo` command. Root user access is required to control the NeoPixel LEDs.

Now talk to your microphone.

##Dependencies

- [Watson Speech to Text](https://www.ibm.com/watson/developercloud/speech-to-text.html)
- mic npm package for reading audio input

