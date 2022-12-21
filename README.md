# Slowed & Reverb Music Video Maker

## About

Creates a .mp4 music video in the style of slowed and reverb from given URL of any music on YouTube Music and any choice of GIF with a Jupyter notebook.

### Original music: 
[<img src="https://github.com/asherchok/snr/blob/main/instructions/ori.PNG">](https://youtu.be/PIszx-GuPmE "Watch it now on YouTube")

### Modified music from this work:
[<img src="https://github.com/asherchok/snr/blob/main/instructions/edited.PNG">](https://youtu.be/O1xS9EFrhzA "Watch it now on YouTube")

### More samples can be found [here](https://www.youtube.com/channel/UCep3hGmnQ2Nxt5oGuBZ4BBw)

## References to project:
The following sources were used to achieve the goal of this project:
- [pedalboard python library by Spotify’s Audio Intelligence Lab](https://spotify.github.io/pedalboard/)
- [File Chooser widget](https://pypi.org/project/ipyfilechooser/)
- [Making videos with Moviepy python library](https://pypi.org/project/moviepy/)

## Installation
This work is done in `Python 3.10.5`. To install dependencies, run `pip install -r requirements.txt` on PowerShell Terminal. Save `textclipfonts.txt` into the same location where `snr-generator.ipynb` is saved at to allow changing the text font on the final generated video.

To allow the text title to be added into the video, **ImageMagick** has to be installed to the local machine. Get ImageMagick [here](https://imagemagick.org/script/download.php). On the ImageMagick installation window, check the following two options:
- Associate supported file extensions with ImageMagick
- Install legacy utilities (e.g. convert)

![alt text](https://github.com/asherchok/snr/blob/main/imagemagickoptions.png?raw=true)

## How to use
Open the file `snr-generator.ipynb` on  [Jupyter notebook](https://jupyter.org/install). The script needs a designated directory to save the final output `.mp4` file. To do this, run the first code block as shown below and paste file directory in the box without \ at the end of the directory address. For example, `C:\Users\user\Downloads` instead of `C:\Users\user\Downloads\`.

![alt text](https://github.com/asherchok/snr/blob/main/instructions/ins-1.PNG?raw=true)

Run the second block. You will be asked to paste any YouTube music (or any YouTube video) URL link below. The script will first download a `.webm` extension of the designated URL link, then convert it to `.mp3`, and then deletes the `.webm` file in a newly created `\temp\` folder in the assigned directory.

![alt text](https://github.com/asherchok/snr/blob/main/instructions/ins-2.PNG?raw=true)

After the audio has been downloaded, the code block will modify the downloaded audio with `speed = 0.85` and `reverb_rate = 0.1`. Changing the values of these two variables will re-run the code block. Setting the variables `speed = 1.0` and `reverb_rate = 0` will show the original unmodified `.mp3` file. To slow down the audio, use the slider and reduce `speed` value less than `1.0`. To speed up the audio, use the slider and increase `speed` value more than `1.0`. If `reverb_rate` is set to 0, then the reverb effect is removed from the audio. Assigning a non-zero value to `reverb_rate` applies a roomsize effect on the audio.

Like the speed and reverb settings for the audio? Proceed to the next code block below. You will be asked to select a GIF file that will be looped in the entire video. Note that the file chooser window will display the location where `snr-generator.ipynb` is saved at. The next block is entirely optional. Running it will simply show the GIF that you had selected on the previous block and skipping it does not affect the rest of the process.

![alt text](https://github.com/asherchok/snr/blob/main/instructions/ins-3.PNG?raw=true)

Run the next block after the `(Optional) ... ` code block to assign a font to the video. The default font in this notebook is set to `Brush-Script-MT-Italic` but can be changed to other fonts.

![alt text](https://github.com/asherchok/snr/blob/main/instructions/ins-4.PNG?raw=true)

By default, the text on the final `.mp4` file will show `{YouTube video title from URL}` + `(Slowed & Reverb)`. To manually add text into the video, modify the line
```
name_caption = filename_abbrv.replace(PATH + '\\', "") + ' (slowed & Reverbed)'
```
into something else. For example, a video with custom title would be `name_caption = 'Symphony No. 5 (speed up version)''. The apostrophe must be wrapped around the name or else `name_caption` will not pass the input as string.

Finally, run this block and get the final output `.mp4` file. The output file will be saved at the assigned directory from the first code block and the `\temp\` folder will be deleted.

![alt text](https://github.com/asherchok/snr/blob/main/instructions/ins-5.PNG?raw=true)

## License
MIT
