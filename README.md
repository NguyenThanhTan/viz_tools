Visualization code by Tan Nguyen February 2022.

Code is in: Box\DCL_ARCHIVE\viz_tools

##Installation

Install anaconda.

Create an environment: \
```conda env create -f environment_overlay.yml```

Then activate the environment (named viz): \
```conda activate viz```

Fire up either app by: \
```panel serve overlay_data_on_video_1.ipynb``` or \
```panel serve overlay_data_on_video_2.ipynb```

The open http://localhost:5006/overlay_data_on_video_2. Initially, if the terminal print out error, it's expected because no files have been given to the app yet. Continue with the app to select appropriate files.

Two apps will have Input widgets asking annotation file 
- First app it's *.csv 
- Second app it's *.txt 
- Then, based on information from annotation file, possible labels will appear in the Multi-select widgets below Input widgets. 
- Output format can be determined by Grid column widget - select #columns, then #rows will be inferred based on how many labels you identify in Multi-select widget (and #columns)
- Then select input video and fill in output video path (.avi).
- Click Render preview to see a frame from the to-be-rendered video.
- When the preview looks good, you can specify sampling rate and click Draw to render the full video. Default sampling rate is the sampling rate from the input video, if you lower this number, the rendering process will run faster.

For the first app, if the annotation file (*.csv) doesn't have information about timepoints, it'll infer sampling rate; otherwise it'll use the column named 'frame' to determine timepoints.

Input examples for the first app is: e51_bills.csv and e51_A_cut.mov

Input examples for the second app is: RedBalloon_clip1_exp59_trimmed_shifted_seconds.txt and RedBalloon_clip1_excerpt.mov

For the second app, output will be *.avi (without audio) and *.mp4 (with audio)