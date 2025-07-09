CROSS-CAMERA PLAYER IDENTITY MAPPING

Author: Makarand Sunil Kakad
Project Type: Computer Vision + Player Tracking
Status: ✅ Completed

---------------------------------------------
🎯 OBJECTIVE

To track and map football players across two video feeds (broadcast.mp4 and tacticam.mp4) such that each player retains a consistent identity (same player_id) across both views.

---------------------------------------------
📁 FILES & FOLDER STRUCTURE

cross-camera-player-mapping/
├── main.ipynb              → End-to-end notebook (Colab or local)
├── README.txt              → This file
├── report.md / report.pdf  → Project summary

---------------------------------------------
🛠️ SETUP INSTRUCTIONS

Step 1: Upload these files into a /data folder:
- broadcast.mp4
- tacticam.mp4
- best.pt (YOLO model weights)

Step 2: Install dependencies

Run this in Colab or terminal:
pip install ultralytics filterpy scikit-learn opencv-python numpy

---------------------------------------------
🚀 HOW IT WORKS

1. DETECTION & TRACKING
- YOLOv8 detects players frame by frame.
- SORT assigns unique IDs to each player in both videos.

2. FEATURE EXTRACTION
- Visual: RGB color histogram from player crops
- Spatial: Center coordinates of bounding boxes
- Temporal: Motion vectors (delta of position across frames)

3. PLAYER MATCHING
- Cosine similarity is computed across all features.
- tacticam_id → broadcast_id mapping is created.

4. ID VISUALIZATION
- Mapped IDs are drawn onto both videos.
- Output videos:
    • tacticam_mapped_output.mp4
    • broadcast_mapped_output.mp4

---------------------------------------------
📈 TECHNIQUES USED

Detection: YOLOv8 (custom-trained)
Tracking: SORT
Feature Extraction: RGB Histogram + Position + Motion
Matching: Cosine similarity of combined features

---------------------------------------------
🧪 RESULTS

✓ 27 players tracked in broadcast
✓ 28 players tracked in tacticam
✓ Output videos display consistent player IDs across both feeds

---------------------------------------------
⚠️ CHALLENGES

- Lighting and angle differences caused visual noise
- Players occluded or only visible in one camera
- SORT ID switching in crowded scenes

---------------------------------------------
💡 FUTURE WORK

- Try Deep SORT or Re-ID networks
- Sync camera time more precisely
- Use jersey OCR or pose estimation for stronger ID confidence

---------------------------------------------
👩‍💻 AUTHOR

Apeksha Sunil Kakad
GitHub: https://github.com/Apekshakakad

---------------------------------------------
📎 SUBMISSION NOTES

- This project is self-contained and reproducible
- Code runs in `main.ipynb`
- Make sure videos and model weights are added manually

