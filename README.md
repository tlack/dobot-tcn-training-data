# dobot-tcn-training-data
Training data for Time Contrastive Network experiments

## what 

To train a contrastive network, you need alike and dissimilar examples.

Here are some I am releasing from a work in progress, (Dobot TCN)[https://github.com/tlack/dobot-tcn/].

#### v2/ dataset

v2/ contains images of a single-axis servo "robot arm" rotating to randomly chosen locations, 
accompanied by a photo from two cameras (called `rpi` and `rpzw`).

There are four folders, corresponding to four different camera positions.

Each folder contains 200 observations.

Each observation consists of two jpeg images and one .json file.

For example:

```
data/position1$ file 40-rpi.jpg
40-rpi.jpg: JPEG image data, Exif standard: [TIFF image data, big-endian, direntries=10, height=0, manufacturer=RaspberryPi, model=RP_ov5647, xresolution=156, yresolution=164, resolutionunit=2, datetime=2020:08:23 20:49:10, width=0], baseline, precision 8, 640x480, components 3
data/position1$ file 40-rpzw.jpg
40-rpzw.jpg: JPEG image data, Exif standard: [TIFF image data, big-endian, direntries=10, height=0, manufacturer=RaspberryPi, model=RP_imx219, xresolution=156, yresolution=164, resolutionunit=2, datetime=2020:08:23 20:49:11, width=0], baseline, precision 8, 640x480, components 3
data/position2$ cat 40-joints.json
{"from": {"1": 5}, "to": {"1": -59}, "goal": {"1": -60}, "exp_config": {"SWEEP_RANGE": 90, "AXIS_REPS": 2, "N_EXAMPLES": 200, "JOINT_RANGES": {"1": [-60, 60], "2": [-60, 60]}}}
```

The `to` value here specifies the position of the joint are shown in the video. 

`from` specifies where the joint was positioned before the move and `goal` is where we
wanted it to go. I don't think either are interesting from the standpoint of the actual
observation.

`exp_config` specifies the configuration of this experiment. The `v2/` dataset should all
be the same in this regard. (The unreleased `v1/` was improperly controlled.)

## why

Members of the (AI Hackers Discord server)[https://discord.gg/zErMBh] requested access to the training 
data I was attempting to use for my experiments

## how to use

