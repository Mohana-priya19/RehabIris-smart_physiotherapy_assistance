# RehabIris 👁️💪
### Smart Physiotherapy Application

RehabIris is an intelligent, browser-based physiotherapy assistant that provides real-time exercise guidance using AI-powered pose estimation. It empowers users to perform rehabilitation exercises safely at home with instant corrective feedback and data-driven progress analytics.

---

## 📌 Problem
Physiotherapy requires consistent practice and precise posture. However, many patients perform recovery exercises at home without professional supervision, leading to incorrect movements, delayed recovery, or further injury. Existing digital rehabilitation systems are often expensive, require proprietary hardware, and lack accessibility.

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

## 🏗️ Architecture & Data Flow

[User / Webcam] ──> [TensorFlow.js (Pose Detection)] ──> [Biomechanical Vector Analysis]
│
[UI Dashboard]  <── [Firebase Firestore Data Hub]    <── [Instant Feedback Engine]


### System Workflow
1.  **User Authentication:** User logs in securely via Firebase Auth, loading their historical rehabilitation profile.
2.  **Edge Video Capture:** The application streams live video from the user's webcam (processed locally for absolute privacy).
3.  **Keypoint Extraction:** TensorFlow.js utilizes WebGL acceleration to map 33 anatomical landmarks frame-by-frame.
4.  **Kinematic Evaluation:** The system computes geometric angles between joints and flags deviations from standard therapeutic baselines.
5.  **Reactive Feedback loops:** Instant UI/Audio prompts instruct the user to adjust their posture (e.g., *"Straighten your back"*, *"Lower your knee"*).
6.  **Telemetry Logging:** Performance metrics, accuracy scores, and repetition counts are synced to the Firestore Database.
7.  **Insight & Report Generation:** The data engine runs analytical summaries to generate recovery trends, rendering interactive charts and exportable PDFs.

---

## 🛠️ Tech Stack

| Layer | Technologies Used |
| :--- | :--- |
| **Frontend Core** | React, TypeScript, Vite |
| **AI & Computer Vision** | TensorFlow.js, MediaPipe Pose Detection, WebGL Acceleration |
| **UI & Animation** | Tailwind CSS, Framer Motion, Lucide Icons |
| **Backend & Database** | Firebase Auth, Firestore Cloud Database |
| **Data Viz & Reporting** | Recharts, jsPDF, html2canvas, React Markdown |

---

## 🚀 Getting Started

### Prerequisites
* Node.js (v18 or higher)
* npm or yarn

### Installation
1
