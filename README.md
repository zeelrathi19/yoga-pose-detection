Yoga Pose Detection and Classification
A real-time yoga pose detection and classification system using MediaPipe and OpenCV that helps 
users perform yoga asanas correctly by providing instant feedback.

Overview
This project implements a machine learning-based yoga pose estimation system that can detect and classify yoga poses in real-time using computer vision techniques. The system aims to help people practice yoga correctly at home, especially useful during situations like COVID-19 when access to instructors is limited.

Features

- Real-time pose detection using MediaPipe's BlazePose
- Pose classification for 3 different yoga asanas
- Live feedback through webcam
- High accuracy pose recognition (100% on tested poses)
- User-friendly interface with pose landmarks visualization

Supported Yoga Poses

1. Warrior II Pose (Virabhadrasana II)
2. Tree Pose (Vrikshasana)
3. T Pose (Standing T)

Technology Stack

- Python 3.7+
- OpenCV - Computer vision operations
- MediaPipe - Pose landmark detection
- NumPy - Numerical computations
- Math - Mathematical operations

Requirements
- opencv-python>=4.5.0
- mediapipe>=0.8.0
- numpy>=1.21.0
- matplotlib>=3.3.0

Installation

Clone the repository
git clone https://github.com/yourusername/yoga-pose-detection.git
cd yoga-pose-detection

Create a virtual environment (recommended)
python -m venv yoga_env
source yoga_env/bin/activate  # On Windows: yoga_env\Scripts\activate

Install dependencies
pip install -r requirements.txt


Usage
Real-time Pose Detection
Run the main script to start real-time pose detection:
python yoga_pose_detection.py

- The application will open your default camera
- Stand 2-4 meters away from the camera for optimal detection
- Perform any of the supported yoga poses
- The system will display the detected pose name on screen
- Press 'ESC' to exit the application

Key Functions

- detectPose() - Detects pose landmarks using MediaPipe
- classifyPose() - Classifies the detected pose using angle heuristics
- Real-time processing with optimized performance

How It Works
1. Feature Extraction

- Videos/images are processed frame by frame
- MediaPipe extracts 33 key body landmarks
- Joint angles are calculated for pose analysis

2. Classification

- Angles are compared with reference pose data
- Classification based on angle heuristics
- Real-time pose identification

3. Feedback Generation

- Instant visual feedback with pose labels
- Landmark visualization for pose guidance

Technical Approach
- The system uses MediaPipe's 2-Step Detection method:

- Detection: Locates person in the first frame
- Tracking: Efficiently tracks landmarks in subsequent frames
- Optimization: Reduces computational overhead

📈 Performance

- Accuracy: 100% on tested yoga poses
- Real-time processing: Optimized for live video streams
- Efficiency: Uses MediaPipe's lightweight pose detection

Model Configuration
pose_video = mp_pose.Pose(
    static_image_mode=False,
    min_detection_confidence=0.5,
    model_complexity=1
)

Contributing
Contributions are welcome! Here are some ways you can contribute:

- Add more yoga poses - Extend the classification to include additional asanas
- Improve accuracy - Enhance the angle calculation algorithms
- Add voice feedback - Implement audio guidance
- Mobile support - Create a mobile app version
- Better UI - Improve the user interface

Steps to Contribute:

- Fork the repository
- Create a feature branch (git checkout -b feature/new-pose)
- Commit your changes (git commit -am 'Add new yoga pose')
- Push to the branch (git push origin feature/new-pose)
- Create a Pull Request

🔮 Future Enhancements

 - Voice feedback for pose corrections
 - More yoga poses (target: 20+ asanas)
 - Pose scoring system with detailed feedback
 - Mobile application for iOS/Android
 - Multi-person detection support
 - Progress tracking and analytics
 - Custom pose creation feature

Research Background
This project is based on research in human pose estimation and computer vision. Key references include:

- MediaPipe Pose estimation framework
- BlazePose: On-device Real-time Body Pose tracking
- Various yoga pose classification methodologies

Limitations

- Single person detection only
- Optimal distance: Works best at 2-4 meters from camera
- Front view: Currently supports front-facing poses only
- Lighting conditions: Requires adequate lighting for accurate detection

Author
Zeel Rathi

- M.Sc. (Integrated) AIML Student
- Gujarat University
- Department of AIML & Data Science

Acknowledgments

MediaPipe team for the excellent pose detection framework
OpenCV community for computer vision tools
Gujarat University for academic support
Yoga community for pose references and validation

⭐ If you found this project helpful, please give it a star! ⭐
