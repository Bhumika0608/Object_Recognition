This project implements a real-time 2D object recognition pipeline built from scratch using classical image processing, feature engineering, and machine learning — along with an extension into deep-learning-based embeddings.

Key Objectives

✔ Real-time segmentation and region extraction

✔ Rotation/scale/translation-invariant shape feature extraction

✔ Automated feature database creation from live camera input

✔ Multi-classifier recognition with robustness improvements

✔ Few-shot embedding-based classification.

System Architecture

| Stage                               | Description                                                                        |
| ----------------------------------- | ---------------------------------------------------------------------------------- |
| **1️⃣ Thresholding**                | Fixed Threshold, K-Means, Saturation-Based & Otsu’s method for object segmentation |
| **2️⃣ Morphological Cleanup**       | Remove noise using erosion, dilation, opening/closing, gradient, etc.              |
| **3️⃣ Connected Components**        | Identify object regions & compute stats (area, centroid, bounding box)             |
| **4️⃣ Feature Extraction**          | Geometric + Hu Moments (19-dimensional invariant feature vector)                   |
| **5️⃣ Interactive Training Module** | Stores labeled features to CSV database from real-time video                       |
| **6️⃣ Live Classification System**  | Ensemble using scaled Euclidean, Manhattan, Cosine, and KNN                        |
| **7️⃣ Performance Evaluation**      | Confusion matrix & per-class accuracy                                              |
| **8️⃣ Extension**                   | ResNet18 embedding-based few-shot classification                    |

Results:

✔ Overall Accuracy: 90% (27 correct out of 30 samples)

✔ Number of Object Classes: 5 tested (Bottle, Can, Compass, Level, Screwdriver)

✔ Per-Class Performance:

    Object	Accuracy

    Bottle	83.3%

    Can	83.3%

    Compass	100%

    Level	83.3%

    Screwdriver	100%

✔  Sample Results: 



✔  Requirements
Build Tools

    macOS Monterey / Ventura / Sonoma

    CMake ≥ 3.10

    Clang / Apple LLVM Toolchain (comes with macOS)

    C++17 compiler support

Xcode Command Line Tools

    xcode-select --install

Required Dependencies
1️⃣ OpenCV 4.x

Install via Homebrew:

    brew install opencv


This automatically places OpenCV in:

    /opt/homebrew/opt/opencv/


▶️ Quick Start
Automated Build (Recommended)

From the project root:

    ./build_project.sh


This will:

✔ Configure with CMake
✔ Build the project
✔ Output executable to bin/ directory

Manual Build Using CMake

    mkdir build

    cd build

    cmake ..

    make -j4

    ./ObjectRecognition   # Run the application

🎥 Camera Permissions (Important)

macOS may block camera access by default.

Enable:
System Settings → Privacy & Security → Camera → Allow for Terminal / IDE

