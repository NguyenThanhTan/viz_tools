Visualization code by Tan Nguyen February 2022.

Code is in: Box\DCL_ARCHIVE\viz_tools

## Installation

Install Anaconda.

Create an environment: \
```conda env create -f environment_overlay.yml```

Then activate the environment (named viz): \
```conda activate viz```

## Usage

### Open the app
Fire up either app by: \
```panel serve overlay_data_on_video_1.ipynb``` or \
```panel serve overlay_data_on_video_2.ipynb```

Then open http://localhost:5006/overlay_data_on_video_2 or http://localhost:5006/overlay_data_on_video_1. Initially, if the terminal print out error, it's expected because no files have been given to the app yet. Continue with the app to select appropriate files.

### Input necessary files
Two apps will have Input widgets asking annotation file 
- First app it's *.csv 
- Second app it's *.txt 

Then, based on information from annotation file, possible labels will appear in the Multi-select widgets below Input widgets. Select labels you want to render.

Output video layout can be determined by Grid column widget. Select #columns, then #rows will be inferred based on how many labels you identify in Multi-select widget (and #columns).

Then select input video and fill in output video path (.avi).

### Render preview and video
Click Render preview to see a frame from the to-be-rendered video. Change Multi-select widget or Grid column widget and render preview again if you want to change how the video should look.

Once the preview looks good, you can specify sampling rate and click Draw to render the full video. Default sampling rate is the sampling rate from the input video, if you lower this number, the rendering process will run faster.

## Examples

### First app

This app render a video features (such as hand velocity, or segmentation norm)

If the annotation file (*.csv) doesn't have information about timepoints, it'll infer sampling rate; otherwise it'll use the column named 'frame' to determine timepoints.

Input examples for the first app is: e51_bills.csv and e51_A_cut.mov

Output for the first app is *.avi

### Second app

This app render a video with binary signals (such as event boundaries)

Input examples for the second app is: RedBalloon_clip1_exp59_trimmed_shifted_seconds.txt and RedBalloon_clip1_excerpt.mov

For the second app, output will be *.avi (without audio) and *.mp4 (with audio)
