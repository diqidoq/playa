# playa

## Description

*playa* is a very lightweight recursive directory Linux console audio player, able to simply scan recursively at terminal position for configurated audio formats by default without any additional arguments, or any given folders and subfolder and play the audio from any media file including any video format in a queue under the given path recursively while providing additional media file infos regarding codec, container, size, bitrate, samplerate, compression rate, streaming infos and much more. PLAYA also support to play a playlist file. This fills the gap between GUI audio players incl. bigger console players and some maybe too simple play terminal commands on the other hand, which need more typing to achieve parsing of directories and manage or test different media files regarding audio in a simple, lightweight and fast manner while being smart with unescaped directories or files with special characters.

Simply type ``` playa ``` or ``` playa dir/subdir ``` and let playa play all audio from any media file under the given path recursively (means, it will also play all audio from any media files in ``` dir/subdir/subdir2/etc ``` one after the other.

For me the fastest "I would like to listen music" action on terminal I know of ATM.

## First steps

### Dependencies (at the moment Linux only)

Make sure you have at least mplayer (default on many Linux) or FFmpeg or SoX installed. Under Debian like Linux distros it is provided in the repositories and should be able to install simply via ``` sudo apt-get install mplayer ffmpeg sox ``` etc. Otherwise you can check for downloadabla packages under http://ffmpeg.org.

#### Why mplayer over FFmpeg and SoX in the order ?

Well no need to mention that FFmpeg is THE multimedia format handler/converter library around. A complete, cross-platform solution to record, convert and stream audio and video. But mplayer supports the better player-like feeling in terminal OOTB including easy output driver option support (-ao). The ffplay command of FFmpeg is often not very known by users and has some limitations with complex work-arounds (sdl env variables). At Second, the SoX implemented terminal player named play (which is awesome!) does not support mp3 out of the box (not their fault, license issues) and needs some configuration from the users side. And it also is not that flexible in playing *ANY* formats like FFmpeg and mplayer does. One of the goals of PLAYA. SoX is a great command line Swiss Army Knife (like FFmpeg) and there is a battle going on between FFmpeg and SoX which result in better audio format conversions when it comes to codec/container transcoding for audio files, but for the approach of PLAYA the mplayer then ffmplay then SoX play order is the way to go for the minimum compatibility.

### Get playa

If you have git installed, you can clone playa into your ~/bin or /share directory:

```
git clone https://github.com/diqidoq/playa.git
```

Or you can download the zip file from https://github.com/diqidoq/playa/archive/master.zip, unpack it and navigate into the folder tree for installation.
Simply place the folder named *playa* into any directory of choice for your external command line tools repository. We keep this folder since it holds also config and log files.

## Installation locally

Use your local **bin directory of choice** (see below: [Common bin directories](#commonbindir)) to place a symlinked alias of the execution file (the playa file in the playa folder) in there.

For example: If your local bin directory is ~/bin, then in command line you can do it with ``` ln -s /root/path/playa/playa $HOME/bin/playa ``` and add execution permissions for the playa file by the following terminal command: ``` chmod a+x $HOME/bin/playa/playa ``` .

Make sure your user home bin folder is in the system path by adding this to your ``` .profile ``` .

```
if [ -d "$HOME/bin" ] ; then
    PATH="$HOME/bin:$PATH"
fi
``` 

## Installation globally (requires root priviledges)

Symlink the file named *playa* inside playa folder into your **bin directory of choice** (see below: [Common bin directories](#commonbindir)) and add execution permissions.

For example: If your global bi directory is /usr/local/bin do it by the following terminal commands:

```
sudo ln -s /root/path/playa/playa /usr/local/bin/playa
sudo chmod a+x /usr/local/bin/playa 
```

## <a name="commonbindir"></a>Common bin directories

Note: bin directories are commonly directories added to the enviroment PATH like the following. 

 + ``` $HOME/bin ``` executive directory (if you have this in your PATH enviroment)
 + ``` $HOME/share ``` executive directory (if you have this in your PATH enviroment)
 + ``` /usr/local/bin ``` typical global bin directory for Debian based Linux distros.

## Usage

+ type ``` playa <path/to/folder> ``` to play recursively all music files in side this hierarchy
+ type ``` playa ``` without arguments to play music from terminal position in path recursively
+ press ` CTRL+C ` to simply quit the play queue
+ skipping not supported yet (@TODO)

[!] If FFmpeg or mplayer is not installed, PLAYA falls back to sox, which doesn't support non audio files and requires lame and libsox-fmt-mp3 installed to play mp3.

## Contribute

The autor of this software has started development of this small shell contribution with the help from the #bash community, especially @geirha from #bash IRC and is sharing this for free under the  condition to help by providing reports and contribution to extend the functionality. Feel free to post any suggestions in the issue queue https://github.com/diqidoq/playa/issues or at #bash IRC channel in the freenode network, but beware that the terminal based playa is intended for being lightweight and filling the gap between *real* audio players, already too big terminal audio players and too unsatisfying long typing terminal commands on the other hand, while needing to check and play audio seamlessly from *ANY* multimedia file in folder trees. Common use cases: audio management, research, seamless non stop play the library, and more.

## Credits

This shell application has been developed and tested by @diqidoq under Debian 9 and bash shell v. 4.3. Special thanks goes to the supporters and contributors [ocbtec](https://github.com/ocbtec), [geirha](https://github.com/geirha), @llua, @izabera, [konsolebox](https://github.com/konsolebox) and many more from #bash IRC.

## Alternatives

If playa is not for you or your needs, take a look at this more extended console audio players instead:

+ [MOC](http://moc.daper.net/)
+ [ncmpc](http://www.musicpd.org/clients/ncmpc/)
+ [CMus](https://cmus.github.io/)
+ [mp3blaster](http://mp3blaster.sourceforge.net/)
+ [PyTone](http://www.luga.de/pytone/)
+ [mpg123](http://www.mpg123.de/)
+ [PlayShell](http://playshell.sourceforge.net/) of the awesome [konsolebox](https://github.com/konsolebox) :-)

Or use the play commands from this awesome frameworks:

+ [FFmpeg](https://www.ffmpeg.org/) - Command ``` ffplay ```
+ [SoX](http://sox.sourceforge.net/) - Command ``` play ```
+ [Mplayer](http://www.mplayerhq.hu/design7/news.html) - Command ``` mplayer -novideo ```
