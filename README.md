# TwitchPeakHighlight [![Python 3.6+](https://img.shields.io/badge/python-3.6-blue.svg)](https://www.python.org/downloads/release/python-360/)

Generate a highlight compilation video from an input video where audio volume peaks above a threshold.

See a full breakdown on my website [aaroncunliffe.dev/projects/twitchpeakhighlight](https://aaroncunliffe.dev/projects/twitchpeakhighlight)

## Where did the idea come from?
The idea for this project came about because I watch a Twitch streamer called [The Happy Hob](https://twitch.tv/the_happy_hob)
that attempts to complete games without being hit, if he gets hit, he has to start again and loses hours of progress.
He gets quite vocal when he gets hit, I had the idea that I could make a compilation of his hits.

<img src="https://github.com/aaroncunliffe/TwitchPeakHighlight/blob/master/output/waveform.png?raw=true" width="300"> 

The above image shows peak detection of a 30 second clip mapped using matplotlib

Youtube video of an example output given a 4 hour 22 minute input vod [here](https://www.youtube.com/watch?v=lkPgpP4K-r0&feature=youtu.be). As you can see the detection includes a lot of random sounds that are not necessarily interesting (banging desk, dropping things etc), see future work for mentions about algorithm improvements

## Built With
* [librosa](https://librosa.github.io/librosa/) - Audio analysis and peak detection
* [moviepy](https://zulko.github.io/moviepy/) - Video clip compilation and final generation
* [matplotlib](https://matplotlib.org/) - Graphing the detection points

## Learning Points
* Audio Analysis
* Video generation using Python

## Future Plans
* Improve Detection algorithm - As you can see by the video above, it currently picks up any noise above the threshold, including movement or knocking the microphone a slightly improvement would be to require multiple Detection points in a set timeframe.
* More efficient processing - Twitch vods are very large, this means loading them in fixed chunks for the detection algorithm to pass over, this is quite inefficient. 
* Dynamic thresholds - currently the detection threshold is hard coded and needs to be tweaked with the input file to fix over or under detection.
