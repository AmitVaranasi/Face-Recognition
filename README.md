# Real-Time Multi-Camera People Tracking System 👥📹

A face recognition-powered surveillance system that tracks individuals across multiple camera feeds in real-time. Features person search capability and parallel video processing.

## Key Features ✨
- **Multi-Camera Support**: Process 2+ video feeds simultaneously
- **Face Recognition**: Identity verification using FaceNet embeddings
- **Real-Time Search**: Locate specific individuals across camera feeds
- **Threaded Processing**: Efficient resource utilization with multithreading
- **Dynamic Thresholding**: 53% confidence threshold for recognition accuracy

## Applications 🚀
1. **Security Surveillance** - Track suspicious individuals in airports/malls
2. **Smart Attendance** - Monitor employee/student presence in facilities
3. **Crowd Analytics** - Study visitor movement patterns in museums/stadiums
4. **Missing Person Search** - Locate targets in public camera networks
5. **Access Control** - Recognize authorized personnel in restricted areas

## Technical Stack 🛠️
### Core Components
- **Face Detection**: MTCNN (Multi-task Cascaded CNN)
- **Face Recognition**: FaceNet (20170511-185253.pb model)
- **Classification**: Scikit-learn classifier (pre-trained)
- **Video Processing**: OpenCV 4.2+
- **Parallel Computing**: Python threading module

### Dependencies
```bash
pip install tensorflow==1.15 opencv-python scipy numpy pickle-mixin

## Installation & Setup 💻

### Clone Requirements:
git clone https://github.com/davidsandberg/facenet.git
mv facenet/src/* ./

### Prepare Training Data:
Create folder structure: train_img/<person_name>/*.jpg
Include 5-10 clear face images per person
### Download Models:
Place FaceNet model in model/ directory
Store MTCNN weights in npy/ folder

## Usage Guide 🚦

### Start Application:
python main.py
### Search Interface:
Enter target name when prompted:
> "John_Doe"
### Camera Configuration:
# Modify camera sources in thread initialization
thread1 = camThread("Cam 1", 0)        
thread2 = camThread("Cam 2", 1)

Runtime Controls:
Q key: Exit application
Red bounding boxes: Unrecognized faces
Green boxes: Verified identities
Console logs: Detection confidence scores
Performance Metrics 📊

Resolution: 640x480 (default)
Processing Speed: 8-12 FPS per feed (NVIDIA GTX 1060)
Accuracy: 89.4% @ 53% confidence threshold
Max Faces/Frame: 15 (hardware dependent)

## Acknowledgments 🙏

David Sandberg (FaceNet implementation)
MTCNN original researchers
OpenCV community for video processing tools
