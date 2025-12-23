# AI & Computer Vision–Enhanced Classroom Observation Tool (COPUS-Style)

This repository contains a **research-grade, privacy-aware classroom observation system** that uses **computer vision and AI** to analyze classroom videos and generate **COPUS-style instructional and student engagement codes** at **2‑minute intervals**.

The tool is designed to support **STEM education research**, **faculty professional development**, and **equity-focused classroom analytics**, while maintaining **transparency and privacy by design**.

---

## 🚀 Key Features

- 🎥 **Video-based classroom observation**
- 🧠 **AI-powered analysis** using YOLOv8 + multi-object tracking
- 🧑‍🏫 Automatic **instructor vs. student role inference**
- 📊 **COPUS-style codes** aggregated per **2-minute interval**
- 🔒 **Face blurring enabled by default** for privacy protection
- 📁 **Dashboard-ready outputs**:
  - CSV (analysis-friendly)
  - JSON (web dashboard / visualization-ready)
- 📈 **Automated plots** for classroom dynamics and engagement trends
- 🧩 Modular, transparent heuristics (easy to replace with trained models)

---

## 🧠 COPUS-Style Outputs

The system generates **proxy COPUS-style codes** based on observable visual signals such as motion, spatial clustering, and instructor dominance.

### Instructor Codes (subset)
- `Lec` – Lecturing
- `FUp` – Follow-up / feedback
- `MG` – Moving & guiding
- `Adm` – Administration / transitions
- `Unk` – Uncertain / mixed

### Student Codes (subset)
- `Lis` – Listening
- `Grp` – Group work
- `Ind` – Individual work
- `AsQ` – Asking questions
- `Unk` – Uncertain / mixed

> ⚠️ **Important:**  
> COPUS is traditionally human-coded. This tool provides **transparent, AI-based proxy codes**. For publication-grade validity, calibrate against human COPUS annotations and report agreement metrics (e.g., Cohen’s κ, macro‑F1).

---

## 📂 Repository Structure

```
.
├── Classroom_Observation_COPUS.ipynb   # Main research-grade Jupyter notebook
├── outputs_copus/
│   ├── annotated_blurred.mp4           # Annotated + face-blurred video
│   ├── copus_intervals.csv              # Interval-level COPUS-style codes
│   ├── copus_intervals.json             # Dashboard-ready JSON
│   └── plots/
│       ├── signals_over_time.png
│       ├── lecture_vs_groupwork.png
│       ├── instructor_code_frequency.png
│       └── student_code_frequency.png
└── README.md
```

---

## ⚙️ Installation

### Requirements
- Python 3.9+
- Recommended: GPU for faster inference

### Install dependencies
```bash
pip install ultralytics opencv-python pandas numpy matplotlib
```

YOLOv8 weights will be downloaded automatically on first run.

---

## ▶️ How to Run

1. Place your classroom video (e.g., `classroom.mp4`) in the project directory.
2. Open the notebook:
```bash
jupyter notebook Classroom_Observation_COPUS.ipynb
```
3. Set the video path in the configuration cell:
```python
VIDEO_PATH = "classroom.mp4"
```
4. Run all cells.

Outputs will be saved automatically to `outputs_copus/`.

---

## 🔐 Privacy & Ethics

This project is built with **Trustworthy AI principles**:

- ✅ **Face blurring enabled by default**
- ✅ No identity recognition or biometric storage
- ✅ Aggregated, interval-level outputs only
- ✅ Designed for IRB-compliant educational research

For real deployments, consider:
- On-device processing
- Access control for raw videos
- Exporting only aggregated statistics

---

## 📊 Dashboard Integration

The exported `copus_intervals.json` is structured for direct use in:
- React dashboards
- Streamlit apps
- Plotly Dash
- Tableau / PowerBI (via JSON import)

Each interval contains:
- Time bounds
- Engagement metrics
- Instructor COPUS-style codes
- Student COPUS-style codes

---

## 🔬 Research Extensions (Future Work)

- Train temporal models (TCN / Transformer) on labeled COPUS data
- Add speech/activity fusion (audio + vision)
- Report inter-rater agreement vs. human coders
- Extend to DEI-focused participation analysis
- Real-time classroom feedback systems

---

## 📜 Citation

If you use this work in academic research, please cite:

```
Adeika, B. (2025).
AI and Computer Vision–Enhanced Classroom Observation Tool for COPUS-Style Analysis.
GitHub repository.
```

---

## 🤝 License

This project is released for **research and educational use**.  
Commercial use may require additional permissions.

---

## ✨ Author

**Blessing Adeika**  
PhD Researcher — Trustworthy AI & Computer Vision  
Morgan State University

---

If you’d like help adding:
- a **demo dashboard**
- a **methods section for a paper**
- or **EB2/EB1-ready project descriptions**

just say the word.
