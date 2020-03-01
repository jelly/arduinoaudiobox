# Arduino Audio Box

This readme describes how to create an audio sample player with an Arduino, capacitor (470 uF) and 
a small speaker.

## Acquiring wav file.

WAV files can be easily acquired from youtube-dl (be aware of licensing issues) as following

```
youtube-dl --extract-audio --audio-format wav "https://www.youtube.com/watch?$VIDEOID"
```

Use ffmpeg to convert it an unsigned 8 bit PCM encoded with 8000 Hz samping rate WAV file.

```
ffmpeg -i test.wav -bitexact -acodec pcm_u8 -ar 8000 8bit.wav
```

Convert the wav file to a C header for Arduino.
```
./tools/wav2c test.wav test.h sounddata
```

Alternatively use audacity to convert the wav file to a "raw wav" file, this
also allows to raise the volume of the audio file. To convert the wav file to a
unsigned 8 bit PCM encoded with a 8000 Hz sampling rate.

## Inspiration

https://www.instructables.com/id/Talking-Arduino-Playing-a-MP3-With-Arduino-Without/

## Credits

tools/wav2c - Mathieu Brethes

Modified to generate Arduino compatible data

PCM/* Michael Smith <michael@hurts.ca
