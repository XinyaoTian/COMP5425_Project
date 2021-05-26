# Manual Word-level ASL Recognition 
Written by Xinyao Tian

If there's any concern please feel free to email me: xtia8647@uni.sydney.edu.au

### Project Overview
This is a operating manuel for our COMP5425 Group Assignment

The Group Project working directory could be found and downloaded through this link:
https://drive.google.com/drive/u/0/folders/1dBCmJDlkLv4aVWQ4cJ_TE8yz1iN0TTSw

Please entering the folder "5425_GroupProject" to see the entire project we did.

### Section of this project
The whole project consists of four parts:

1. The WLASL Dataset. Codes in this section is mainly setting up the WLASL100 dataset
 accoring to the paper mentioned in the Final report.
 
2. The i3D Model Training and Testing. This part is the main process for training a model which could predict words from raw videos.

The code for training the model could be path in this path:

And Also, the model has been trained could be found in this path:

3. The Pose Reranking. Since the paper only could get top-10 results in a high percentage,
we would like to improve the performance of top-1 and top-5 performance by what we've leant
through this course. This section is an effort of that.

4. The PoseEstimation. This is similar to our Assignment2 , but we are using another pose-extraction model
from OpenPose to extract the coordinators since all the videos in WLASL100 are hlaf-bodies.

5. The video-skeleton presenting. This part could show the detected poses in all frames from the videos.


### Set up the WLASL Dataset and the Environment
Although the dataset has been set properly already, we still provide the method on how to set up.

The Dataset could be seen through WLASL/data/

1. Set up the whole dataset
```bash
cd start_kit
python video_downloader.py
```

2.Conduct preprocessing
```bash
python preprocess.py
```

3.You should expect to see video samples under directory videos/
```bash
cd WLASL/start_kit/videos
```


### Training and Testing

1. Enter the working directory
```bash
cd WLASL
mkdir data
```

2. Put all videos under data/
```bash
cp WLASL100 -r data/
```

3. Training the model
```bash
cd code/I3D/
python train_i3d.py

```
You could train models in different dataset by altering the parameter in this file.

4. Testing the model
```bash
cd code/I3D/
python test_i3d.py

```
Also, you could train models in different dataset by altering the parameter in this file.

5. Get the well-trained model

The model trained could be seen through 5425_GroupProject/archived/asl100

```bash
cd 5425_GroupProject/archived/asl100
```

### Run the re-ranking method to get the re-ranking result within the top-10 standard gesture

1. Enter the directory 5425_GroupProject/PoseRanking

```bash
cd 5425_GroupProject/PoseRanking
```

2. Run the notebook to see the result of similarity comparison between the top-10 standards

3. to run Get_Pose_Vectors.ipynb:
- run cell 1 to get access to my gdrive
- ignore cell 2 if you're going to use a different set of videos (this cell is just to download my testing set)
- change the string in cell 3 to the location of the folder containing the videos that you want to run the pose estimator on
- run cell 4 and it will print the dictionary containing the poses extracted from the videos in the folder you wrote in cell 3

### Run the half-body pose estimation

1. Enter the directory 5425_GroupProject/PoseEstimation
```bash
cd 5425_GroupProject/PoseEstimation/
```

2. Run the corresponding notebook.

### Run the demonstration program

1. Enter the directory 5425_GroupProject/VideoSkeletonDraw/

```bash
cd 5425_GroupProject/VideoSkeletonDraw/
```

2. Run the notebook, and there will be a video showing the skeleton of the target video


### The END

That's the end of our project.

We would like to appreciate the whole teaching staff in COMP5425 for their 
great effort of guiding us, sincerely.










