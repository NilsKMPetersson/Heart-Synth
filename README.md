# Heart-Synth
A synthesizer/sequencer, triggered by the user’s heartbeat

~~Welcome to Heart-Synth, where your heartbeat doesn't just keep you alive—it makes music! ~~
<strong>[Short video demo of Heart-Synth in action](https://www.youtube.com/watch?v=8kncr2PZEvg)</strong> 



NOTE: This project requires additional components such as Arduino and photosensitive heart-monitor. 

All the user has to do is put on the heart monitor on their pinky finger, raise the threshold knob until they hear a sound, and then it will start to play through a pre-decided sequence of notes, playing a note every time the heart monitor senses a heartbeat. Four LEDs will also light up, indicating the position of the synth sequence. There is also a volume knob and an audio-out jack. 


![Link to picture](https://user-images.githubusercontent.com/43551833/112672972-8d9c2500-8e3a-11eb-89b1-0037e6d4fb78.png)



## Project explanation/process journal: 

The heart monitor is a non-invasive optical pulse sensor that can accurately sense when blood pulses through the body, which is translated into voltage changes that are picked up by the Arduino microcontroller. Given the *not-so-professional* nature of this particular heart beat monitor, there is also a threshold potentiometer to calibrate its sensitivity. The user has to find the sweet spot where the threshold is low enough that it can catch the voltage spikes, but high enough so that it doesn’t catch any noise that is unrelated to the heartbeat.


A heartbeat will trigger a "gate," which both plays a note, and moves a step forward in the sequencer. The sequence loops by default after step 4. The LED displays the current position of the sequence. 

Have fun! 
