# Playa

## Description

PLAYA is a simple terminal based folder/subfolder audio scanner/player based on FFmpeg, to play all audio from any media file including all audio and audio from video in a queue under the given path recursively.

## First steps

### FFmpeg

Make sure you have FFmpeg installed. Under Debian like Linux distros it is provided in the repositories and should be able to install simply via ``` sudo apt-get install ffmpeg ```. Otherwise you can check for downloadabla packages under http://ffmpeg.org.

#### Why no additional sox or other lib support ?
Well no need to mention that FFmpeg is THE multimedia format handler library around. A complete, cross-platform solution to record, convert and stream audio and video. At Second, the sox implemented terminal player does not support mp3 out of the box and needs some configuration from the users side. And it also is not that flexible in playing any formats like FFmpeg does. One of the goals of PLAYA. Sox is a great library and there is a battle going on between FFmpeg and Sox which libraries result in better audio format conversions when it comes to codec/container transcoding for audiophiles, but for the approach of PLAYA the ffmplay (any file) pipe is unbeatable.

### Get playa

If you have git installed, you can clone playa:

```
git clone https://github.com/diqidoq/playa.git
```

Or you can download the zip file from https://github.com/diqidoq/playa/archive/master.zip unpack it and navigate into the folder tree for installation.

## Installation locally

Simply drag and drop the file named *playa* out of the playa folder into your ``` ~/bin ``` ($HOME/bin) directory or do it via terminal from within the playa folder, which lies where you have playa downloaded or unpacked:

```
cp playa ~/bin/
```

Add execution permissions by the following terminal command:

```
chmod a+x ~/bin/playa
```

Make sure your user home bin folder is in the system path by adding this to your ``` .profile ```

```
if [ -d "$HOME/bin" ] ; then
    PATH="$HOME/bin:$PATH"
fi
```

## Installation globally

Copy the file named *playa* into your ``` /usr/local/bin ``` directory (requires root permissions):

```
sudo cp playa /usr/local/bin/
```

Add execution permissions by the following terminal command:

```
sudo chmod a+x /usr/local/bin/playa
```

## Usage

+ type ``` playa <path/to/folder> ``` to play recursively all music files in side this hierarchy
+ type ``` playa ``` without arguments to play music from terminal position in path recursively
+ press ` CTRL+C ` to simply quit the play queue
+ skipping not supported yet (@TODO)

## Contribute

The autor of this software has developed it with the help from the #bash community, especially @geirha from #bash IRC and is sharing this for free under the condition to provide reports and contribution to extend the functionality. Feel free to post suggestions in the issue queue https://github.com/diqidoq/playa/issues or at #bash IRC channel in the freenode network, but beware that the terminal based playa is intended for being lightweight and filling the gap between *real* audio players, already too big terminal audio players and too unsatisfying long typing terminal commands on the other hand, while needing to check and play audio seamlessly from *ANY* multimedia file in folder trees. Common use cases: audio management, research, seamless non stop play the library, and more.

## credits

The software has been developed and tested by @diqidoq under Debian 9 and bash. Special thanks goes to the supporters and contributors [ocbtec](https://github.com/ocbtec), [geirha](https://github.com/geirha), @llua, @izabera, @konsolebix and many more from #bash IRC.
