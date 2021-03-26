# Heart-Synth
A synthesizer/sequencer that is triggered by the user’s heartbeat!

NOTE: This project requires additional components such as Arduino and photosensitive heart-monitor. 

I decided to create a synthesizer/sequencer that is triggered by the user’s heartbeat. All the user has to do is put on the heart monitor on their little finger, raise the threshold knob until they hear a sound, and then it will start to play through a pre-decided sequence of notes, playing a note every time the heart monitor senses a heartbeat. Four LEDs will also light up, indicating the position of the sequence of notes. There is also a volume knob and an audio-out jack. 

![Link to picture](https://sites.google.com/a/nyu.edu/nils-digital-electronics/_/rsrc/1449787979437/home/final-project-blog/12348613_10153825337564216_852042241_n%20%281%29.jpg)

Here is a short demo video of Heart-Synth in action:
[![Heart-Synth Demo](https://www.youtube.com/watch?v=8kncr2PZEvg/0.jpg)](https://www.youtube.com/watch?v=8kncr2PZEvg)


## Project explanation/process journal: 

The heart monitor is a non-invasive optical pulse sensor that can accurately sense when blood pulses through the body, which is translated into voltage changes that are picked up by the Arduino microcontroller, which when plotted over time look like this: 

![Link to picture](https://sites.google.com/a/nyu.edu/nils-digital-electronics/_/rsrc/1449786362171/home/final-project-blog/Screen%20Shot%202015-12-03%20at%205.27.50%20PM.png?height=207&width=320)

There is also a threshold potentiometer that decides what value will count as a “heartbeat,” and trigger an action in the code. The user has to find the sweet spot where the threshold is low enough that it can catch the voltage spikes, but high enough so that it doesn’t catch any noise that is unrelated to the heartbeat.

![Link to picture](https://3586f828-a-a28aa00e-s-sites.googlegroups.com/a/nyu.edu/nils-digital-electronics/home/lab-12/Screen%20Shot%202015-12-03%20at%205.28.01%20PM.png?attachauth=ANoY7coovw9iP07RaDWptB9YwwAzkPFxqb_qn0IAcLu0tSnvNodAGVVI1OaipZkKhESbuDd3CLYM5zMTg1J8HQZ0BMlPxxYQbnTzYM8CKtchWiVWjZj835R7FuJe_yop8JCNWWfT4ScHb-cNl8NFiAmPKesZ3gH2tpGZZFpomhOMhCLDKumNCpfO_IkmHSL51TNFUcWSyziupdGSU8bHidZ283argxdD9Nnqm5R4loYfHGb7kiWD2g5CDOxP5EBCne8iFilP9SylFSMxgiHqxPR6B7KOat6UcQ%3D%3D&attredirects=0&height=193&width=320)

![Link to picture](https://3586f828-a-a28aa00e-s-sites.googlegroups.com/a/nyu.edu/nils-digital-electronics/home/lab-12/Screen%20Shot%202015-12-03%20at%205.28.29%20PM.png?attachauth=ANoY7cq8ernfgUVrY9Q1C9C_CPNFZQUeH4j5aeVb7YYGXS4xzYbyXuX2NbGcNkNND6IGD1tb4ePk3bIQQ10QmIw0RnTMbpLkT7UsVQyOXI9XHeGhzA5s7HzsLjmSXna9VZKfUZzmct9nR4_Hx-u3TzIzcvBUuSE0OrY5mDc3jpXVVUq0BWM4_RNfYKitKsGmfmI4VqQ9askR_NeOl9zz4ZoF7RzOOOZnxwGRQeBynjDrXWCB969Mg6oqS1CC1a04iyO7LyMN7yew2GfxkDl0wYEOaoFXjiyqsA%3D%3D&attredirects=0&height=193&width=320)

![Link to picture](https://3586f828-a-a28aa00e-s-sites.googlegroups.com/a/nyu.edu/nils-digital-electronics/home/lab-12/Screen%20Shot%202015-12-03%20at%205.28.18%20PM.png?attachauth=ANoY7crySMxn_2buLlCfmx9RCXAhZzFz0kf3PEyojiw4tEc2bZkPdMKXH_RIdgDcXiuyPJaHBm2Ul-EZK20ae3kAzZvXywi_X_1YVq2UVgoKWHGCWBGoKBESZrYlcC6XmpPchBENcMHhTRof7mA7Bee2KhKOD_GQt73naIw7oaLtbS4JyPQI-yG2TjXMo3EtoPRJhMPSGVgsyMQF1HDJnUWI3oiqNsljphRoltzvKZXWwacVBPfXLlJPOX4ZcNDxrVtd6I6UPaQzoAXgqNhDPyetF0Rd8oSwcg%3D%3D&attredirects=0&height=193&width=320)

(^Just right!)

The “action” previously mentioned is what would be referred to in synthesizers/sequencers as CV control voltage. In the code, there is a variable named “counter” that keeps track of the position of the sequence of notes, from 1-4, and then loops. +1 is added to the counter every time the program senses a heartbeat, and the LEDs are given names from 1-4 as well, and are triggered accordingly to give a visual representation of the sequence. 
