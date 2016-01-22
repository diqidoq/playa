# playa
A simple terminal based folder/subfolder audio scanner/player based on FFmpeg, to play all audio from any media file including all audio and video in a queue under the given path recursively.

### Installation locally

Simply drag and drop the file named *playa* in your ``` ~/bin ``` ($HOME/bin) directory or do it via terminal from the folder where you have playa downloaded:

```
cp playa ~/bin/
```

Add execution permissions by the following terminal command:

```
chmod a+x ~/bin/playa
```

### Installation globally

Copy the file named *playa* into your ``` /usr/local/bin ``` directory (requires root permissions):

```
sudo cp playa /usr/local/bin/
```

Add execution permissions by the following terminal command:

```
sudo chmod a+x /usr/local/bin/playa
```

### Usage

+ type: playa <path/to/folder> to play recursively all music files in side this hierarchy
+ type: playa only to look and play music directly from the position in path your terminal points to
+ press: CTRL+C to simply quit the play queue
