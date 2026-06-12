# RehabIris 👁️💪

### Smart Physiotherapy Application

RehabIris is an intelligent, browser-based physiotherapy assistant that provides real-time exercise guidance using AI-powered pose estimation. It empowers users to perform rehabilitation exercises safely at home with instant corrective feedback and data-driven progress analytics.

---

## 📌 Problem

Physiotherapy requires consistent practice and precise posture. However, many patients perform recovery exercises at home without professional supervision, leading to incorrect movements, delayed recovery, or further injury. Existing digital rehabilitation systems are often expensive, require proprietary hardware, and lack accessibility.

---

## 💡 Solution

RehabIris bridges this gap by delivering a real-time, AI-driven rehabilitation ecosystem that runs entirely within a standard web browser. By leveraging edge-AI to track user movements and analyze anatomical angles, the system provides instant corrective feedback while compiling clinical-grade progress reports.

---

## ✨ Features

* **Real-Time Pose Estimation:** Tracks 33 body joint keypoints simultaneously.
* **Biomechanical Analysis:** Real-time calculation of joint angles and posture alignment.
* **Instant Audio/Visual Feedback:** Immediate cues to correct form during exercise sets.
* **Predictive Analytics & Progress Tracking:** Visualizes recovery curves and consistency metrics over time.
* **Automated Clinical Reports:** Generates downloadable PDF medical reports for physiotherapists.
* **Edge Computing:** Runs completely in-browser with hardware acceleration—no data privacy issues or external hardware needed.
* **Secure Infrastructure:** User authentication and historical data logging.

---

## System Worflow
User Authentication: The user logs in securely via Firebase Auth, loading their customized historical rehabilitation profile and assigned routine.

Edge Video Capture: The application streams live video from the user's webcam. This stream is processed entirely locally within the browser sandbox for absolute privacy.

Keypoint Extraction: TensorFlow.js utilizes WebGL hardware acceleration to map and track 33 anatomical landmarks frame-by-frame.

Kinematic Evaluation: The biomechanical engine computes geometric vectors and angles between joints, immediately flagging deviations from standard physical therapy baselines.

Reactive Feedback Loops: The instant feedback engine fires contextual UI overlays and real-time audio cues (e.g., "Straighten your back", "Lower your knee") to guide the user mid-rep.

Telemetry Logging: Performance metrics, posture accuracy scores, session duration, and repetition counts are securely synced to the Firestore Data Hub.

Insight & Report Generation: The data engine runs local analytical summaries to visualize recovery trends via interactive charts and compile downloadable clinical PDFs.
---

## Tech Stack

LayerTechnologies UsedPurposeFrontend CoreReact, TypeScript, ViteBuilds a fast, type-safe, component-driven Single Page Application (SPA).AI & Computer VisionTensorFlow.js, MediaPipe, WebGLPowers real-time, hardware-accelerated 33-point body tracking directly on the client edge.UI & AnimationTailwind CSS, Framer Motion, Lucide IconsDelivers a fluid, modern, accessible dashboard with smooth reactive feedback states.Backend & DatabaseFirebase Auth, Firestore Cloud DatabaseManages secure patient authentication and real-time telemetry data logging.Data Viz & ReportingRecharts, jsPDF, html2canvasRenders responsive analytics recovery curves and handles automated medical PDF generation.
---

## Installation
Clone the repository to your local machine:

Bash
git clone [https://github.com/your-username/RehabIris.git](https://github.com/your-username/RehabIris.git)
cd RehabIris
Install all required Node modules specified in the package.json:

Bash
npm install
# or
yarn install
Create a .env file in the root directory and add your Firebase configuration credentials:  

Code snippet
VITE_FIREBASE_API_KEY=your_api_key_here
VITE_FIREBASE_AUTH_DOMAIN=your_auth_domain_here
VITE_FIREBASE_PROJECT_ID=your_project_id_here
VITE_FIREBASE_STORAGE_BUCKET=your_storage_bucket_here
VITE_FIREBASE_MESSAGING_SENDER_ID=your_messaging_sender_id_here
VITE_FIREBASE_APP_ID=your_app_id_here
Run the local Vite development server:

Bash
npm run dev
# or
yarn dev
Open your browser and navigate to http://localhost:5173. Make sure to grant webcam permissions when prompted!


## 🏗️ Architecture & Data Flow

```text
[User / Webcam] ──> [TensorFlow.js (Pose Detection)] ──> [Biomechanical Vector Analysis] 
                                                                    │
[UI Dashboard] <── [Firebase Firestore Data Hub] <── [Instant Feedback Engine]
