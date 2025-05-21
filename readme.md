# 🦖 Marker-Based Web AR Application – Mixed Reality Project

This project is a simple **marker-based Augmented Reality (AR) web app** developed for the SE4010 – Current Trends in Software Engineering course (Assignment 3 – Mixed Reality). It uses **A-Frame** and **AR.js** to render 3D models on custom image markers through the browser.

## 📌 Overview

The AR experience showcases multiple 3D models (dinosaurs, creatures, and scenery) placed on unique markers. When a marker is detected through the webcam or mobile camera, the corresponding 3D model is displayed with gesture support to **rotate** and **scale** it.

Each model corresponds to a specific marker and represents a scene object selected by the group.

## 🔧 Technologies Used

- [A-Frame](https://aframe.io/)
- [AR.js](https://github.com/AR-js-org/AR.js)
- [aframe-extras](https://github.com/donmccurdy/aframe-extras)
- HTML, JavaScript, GLB 3D Models

## 📂 Folder Structure

```
/ar-gesture-project
│
├── index.html                      # Main application file
├── styles.css                      # Custom styling
├── README.md                       # Project documentation
│
├── images/                         # Marker images (PNG format)
│   ├── pattern-dino.png
│   ├── pattern-macrothorax.png
│   ├── pattern-palm-tree.png
│   ├── pattern-quetzalcoatlus.png
│   └── pattern-spinoceratops.png
│
├── markers/                        # Pattern files for AR.js
│   ├── pattern-dino.patt
│   ├── pattern-macrothorax.patt
│   ├── pattern-palm-tree.patt
│   ├── pattern-quetzalcoatlus.patt
│   └── pattern-spinoceratops.patt
│
├── models/                         # 3D model files (GLB format)
│   ├── macrothorax.glb
│   ├── momma_dino_remake.glb
│   ├── quetzalcoatlus.glb
│   ├── realistic_palm_tree_2_free.glb
│   ├── realistic_palm_tree_4_free.glb
│   └── spinoceratops.glb
│
└── scripts/                        # JavaScript files for gesture support
    ├── gesture-detector.js         # Detects touch gestures
    └── gesture-handler.js          # Handles scaling and rotation gestures
```

## 📱 Features

- 🧠 **Marker-based AR**: Uses image markers to trigger model placement.
- ✋ **Gesture Interaction**: Pinch to scale, drag to rotate the model.
- 📦 **Multiple 3D Models**: Dino, Spinoceratops, Quetzalcoatlus, Palm Tree, and more.
- ⚙️ **Cross-platform**: Runs in mobile and desktop browsers (requires camera and HTTPS).

## 🚀 Deployment

### GitHub Pages
This project can be hosted using **GitHub Pages**:

1. Push the full folder to a GitHub repository.
2. Go to **Settings > Pages**, and select the root of the `main` branch.
3. Update asset paths (models and markers) to use relative URLs like:
   ```html
   src="./models/model.glb"
   url="./markers/pattern-dino.patt"
   ```
4. Open the deployed site in a camera-enabled browser (mobile or desktop).

### Local Development with HTTPS

AR applications require HTTPS to access the camera. For local development, use the `ws` package:

1. Install the local-web-server package:
   ```bash
   npm install -g local-web-server
   ```

2. Run with HTTPS enabled on port 8060:
   ```bash
   ws --https --port 8060
   ```

3. Open in your browser at `https://localhost:8060`

4. Accept the self-signed certificate warning in your browser

## 🧠 Assignment Requirements Checklist

* ✅ Custom image markers
* ✅ Multiple 3D models representing a themed scene
* ✅ Gesture interaction (scale, rotate)
* ✅ Creative element: interaction and model variety
* ✅ Works cross-device with smooth marker tracking

## 🎥 Demo

A short video demo (max 5 minutes) is included in the assignment submission to showcase functionality.

## 📄 Report

A 2–3 page report includes:
* Development process
* Group member contributions
* Screenshots of the working AR app
* Creative elements used

## ✨ Contributors

* Each group member contributed one 3D model and participated in integration and testing.

## 🔒 Note 

Run locally using a web server or deploy to GitHub Pages. Camera access will not work from local file paths (`file://`).

## 🛠️ Converting Models to GLB Format

### ✅ Option 1: Using gltf-transform (Recommended)

#### Step 1: Install gltf-transform CLI
```bash
npm install -g @gltf-transform/cli
```

#### Step 2: Combine to .glb
```bash
gltf-transform copy scene.gltf scene.glb
```

This will:
- Embed the scene.bin
- Embed all textures
- Output a single .glb file