# Myhandbrake

A script that uses handbrake to encode media files using sensible presets.

## Synopsis

This scripts reduces the size of DVDs and other media considerably, by using HandBrake CLI  to encode it into MP4/MKV using x264.

## Installation

The script requires HandBrake CLI:

    > sudo add-apt-repository ppa:stebbins/handbrake-releases
    > sudo apt-get update
    > sudo apt-get install handbrake-cli

## Usage

    > ./myhandbrake -i <input> -o <output> [options]

| Option | Description |
| --- |--- |
-i,--input <input>       | Input file or folder |
-o,--output <output>     | The extension of the outputfile determines its container |
-s,--speed <speed>       | Speed indicators for x264 |
-p,--preview <seconds>   | Create preview starting at <seconds> |
-d,--duration <seconds>  | Set duration of preview in seconds  |
-a,--audio <tracks>      | Comma separated list of audio tracks, e.g. "1,2,5" |
-u,--subtitle <tracks>   | Comma separated list of subtitle tracks, e.g. "1,4" |
-q,--quality <RF-factor> | Quality RF factor, 0 is lossless, 50 is unwatchable  |
-h,--help                | Print these options |

## Example

The following command creates an encoding preview file `myvideo.mp4` of 15 seconds from a DVD directory hierarchy. Use the preview functionality to tune encoding options like quality.

    > ./myhandbrake                           \
        --input VIDEO_TS --output myvideo.mp4 \  # determine input and output
        --quality 18 --speed slow             \  # speed influences quality, encode slow
        --preview 400 --duration 15           \  # encode starting at 400s for 15s
        --audio "2,1" --subtitle "4,2"           # add 2 audio and subtitle tracks

