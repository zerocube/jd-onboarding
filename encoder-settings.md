# Encoder Settings

This page has everything you need to get your encoder up and running.
If required, your project contact will let you know if any of the below settings need to be amended.

## OBS

### Step 0: Download OBS!

OBS runs on Mac, Windows, and Linux - And can be downloaded here: https://obsproject.com/download

Open it up once you're ready to move on to the next step.

### Step 1: Configure OBS

For most setups, you can use the profile method below.

#### With a Profile

Inside the `obs_profiles` directory there is a zip file.

Once you've extracted it somewhere on your system, import the profile into OBS.  
(Menubar: `Profile` -> `Import`).

Then head on over to step 2 to [set up your scenes](#step-2-set-up-your-scenes)!

#### Manually

In the main OBS window, click `Settings`.

##### Stream

Because this information is generated on an as-needed basis, your project contact will send you the information you'll
need to put in here.

##### Output

Note: Depending on the encoder available on your system, some options may not be available.
Please enter all applicable values, and disregard the rest.
If you are uncertain, please reach out to your project contact with a screenshot of this dialog.

```
Encoder:                    H.264 (aka libx264 - Also NVidia NVENC H.264, Apple Hardware H.264, et al.)
Bitrate:                    50% of available upload speed
CBR (if available):         Yes - Use above bitrate
Keyframe Interval:          1
Rate Limit (if available):  Yes
Profile:                    Main
Preset:                     zerolatency / Low-Latency Performance
```

##### Video

```
Base (Canvas) Resolution:       1920x1080
Output (Scaled) Resolution:     1920x1080
Framerate / Common FPS Values:  29.97
```

##### Advanced

###### Automatically Reconnect
```
Automatically Reconnect:  Enable
Retry Delay:              3s
Maximum Retries:          30
```

###### Network

```
Dynamically change bitrate to manage congestion: Checked / Enabled
```

### Step 2: Set up your scene(s)

Your project contact should outline instructions and setup requirements.
Please reach out to them if you have any questions about this step.

## ffmpeg

Note: This option is for advanced users only, that are confident using and debugging the `ffmpeg` utility on the command
line.

```bash
export VIDEO_BITRATE="2500k" # Set to 50% of available upload speed
export INPUT="device-here"
export RTMP_ENDPOINT="from-project-contact"

ffmpeg -i "${INPUT} -c:v libx264 -c:a aac -b:v "${VIDEO_BITRATE}" -f flv "${RTMP_ENDPOINT}
```

Depending on what your source is, you may want to consider:

  1. Using `-c copy` if the input streams are already in the H.264/AAC format
  1. Using `-re` if playing back a local video file
  1. Using hardware acceleration to improve performance if available: https://trac.ffmpeg.org/wiki/HWAccelIntro

To help debug issues, you may also want to consider debugging with a local RTMP server:

```bash
ffplay -listen 1 'rtmp://localhost:1935?listen'
```

Which you can then stream to by replacing `$RTMP_ENDPOINT` with 'rtmp://localhost:1935'
