<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:00F7FF,100:7B2FF7&height=200&section=header&text=Doan%20Anh%20Quan&fontSize=56&fontColor=ffffff&fontAlignY=36&desc=AI%20Engineer%20%C2%B7%20Computer%20Vision%20%C2%B7%20Perception&descAlignY=58&descSize=18&animation=fadeIn" alt="Doan Anh Quan" />

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=24&pause=1000&color=00F7FF&center=true&vCenter=true&width=720&lines=Xin+chao!+I'm+Doan+Anh+Quan;AI+Engineer+with+a+Computer+Vision+focus;AI+in+Action+K4+-+Track+4%3A+Perception;Teaching+cameras+to+spot+sleepy+drivers;Professional+false-alarm+hunter;Open+to+AI+Engineer+%28CV%29+internships" alt="Typing intro" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/📍-Ho_Chi_Minh_City-7B2FF7?style=flat-square" alt="Location" />
  <img src="https://img.shields.io/badge/🎓-HCMUS_'27-00A3FF?style=flat-square" alt="HCMUS" />
  <img src="https://img.shields.io/badge/🚗-AI_in_Action_K4-00C2D1?style=flat-square" alt="AI in Action K4" />
  <img src="https://img.shields.io/badge/🟢-Open_to_AI_Engineer_(CV)_internships-2EA44F?style=flat-square" alt="Open to AI Engineer (CV) internships" />
  <img src="https://komarev.com/ghpvc/?username=doananhquan26072005&label=Profile%20views&color=7b2ff7&style=flat-square" alt="Profile views" />
</p>

---

## 👋 `whoami`

```python
class DoanAnhQuan:
    """AI engineer in the making: computer vision first, false alarms counted for fun."""

    role = "AI Engineer · Computer Vision"
    based_in = "Ho Chi Minh City, Vietnam 🇻🇳"
    education = {
        "HCMUS, VNU-HCM": "B.Sc. Math & CS · 2023 – 2027 · GPA 3.63/4.0",
        "AI in Action K4": "VinUni × Vingroup · Track 4: Perception for AD & Robotics",
    }
    working_on = ["DriverGuard 🚗💤", "Vietnamese Sign Language recognition 🤟"]
    looking_for = ["AI Engineer (Computer Vision)", "Perception / Autonomous Driving"]
    speaks = {"Vietnamese": "native", "English": "TOEIC L&R 870"}

    def evaluate(self, model):
        # accuracy alone never gets the last word
        return model.accuracy, model.false_alarms_per_hour
```

## 🔭 Right now (Oct 2026)

- 🚗 Joined **AI in Action** cohort 4 (VinUni × Vingroup), a 12-week full-time applied AI program, on **Track 4: Perception for Autonomous Driving & Robotics**
- 💤 Shipping **DriverGuard**, our build-phase project: an on-device driver monitoring system
- 🤟 Running experiments for my graduation thesis on **Vietnamese Sign Language** recognition
- 🔍 Looking for an **AI Engineer internship** focused on computer vision, from model to deployed product (perception / autonomous driving is a big plus)

---

## 🛠️ Featured projects

### 🚗 DriverGuard: on-device driver drowsiness & distraction monitoring
`team of 4 · main contributor · AI in Action build phase · 2026`

[![Demo](https://img.shields.io/badge/Demo-YouTube-FF0000?style=flat-square&logo=youtube&logoColor=white)](https://youtu.be/3y0aOBudGyk)
[![Live](https://img.shields.io/badge/Live-Railway-0B0D0E?style=flat-square&logo=railway&logoColor=white)](https://c4-app-135.up.railway.app)
[![Repo](https://img.shields.io/badge/Repo-driverguard-181717?style=flat-square&logo=github)](https://github.com/doananhquan26072005/driverguard)

> Camera → MediaPipe + YOLOv8n → eye-state CNN → drowsiness & distraction branches → risk engine → 4-level alerts (L0–L3).
> Faces never leave the device. Only JSON metadata goes to the server.

- ⚡ **~146 FPS** on a laptop CPU · 🎯 catches **78.9%** of microsleeps on FL3D
- 🚨 **False-alarm suppression** in the risk engine: frame-level PERCLOS, no alerts while the car is stopped, EAR/CNN anti-flicker, escalation rules (yawn → nod goes straight to L3)
- 🌐 **Runs in the browser**: Pyodide, YOLO in a Web Worker, WebGPU, watchdog
- 📏 **Evaluation harness** on 5 datasets (FL3D, SUST-DDD, YawDD, UTA-RLDD, 3MDAD) reporting false alarms per hour with Poisson confidence intervals
- 🗄️ **FastAPI backend**: trip reports, audit log, versioned thresholds, fleet heartbeat, data retention & export

### 🤟 Vietnamese Sign Language Recognition (graduation thesis)
`in progress · defense mid-2027`

- From sign video to a Vietnamese sentence in three stages: pose features → temporal segmentation of continuous signing (sliding window, temporal IoU, T-NMS) → gloss-to-text translation
- Pose input of 76 joints × 3 coordinates, shoulder-normalized, on the VSL400 dataset (472 classes)
- Ablation ladder: **SPOTER** baseline → **K-SPOTER** (multi-stream + cross-stream attention fusion) → **Hybrid GCN-Transformer** (adaptive spatial graph) → **Unified K-SPOTER** (proposed)
- 🧪 Results coming once the experiments settle

### ✍️ Vietnamese Text Correction
`team lead · 4 people · NLP course · 06/2026` · [repo](https://github.com/doananhquan26072005/Correct-spelling-errors-project)

- Cleans up social-media Vietnamese (`khum bjet` → `không biết`) on 70K sentence pairs: Transformer diacritic restoration → teencode expansion → KenLM error detection → SymSpell candidates → LightGBM LambdaRank reranking
- I built the correction module: KenLM trigram plus a 7-feature ranker (Telex-weighted edit distance, LM score, n-gram counts, Word2Vec, length ratio)
- 🎯 Precision **89.64%** · F0.5 **79.40%** (tuned so it doesn't over-correct) · WER **18.07%** on test

### 🛑 Traffic Sign Recognition: Siamese Network + KNN
`main author · 3 people · 11/2025` · [repo](https://github.com/doananhquan26072005/traffic-sign-detection)

- HSI thresholding (Otsu + color masks) and contours to find signs, then a Siamese CNN with contrastive loss → 300-d embeddings
- KNN (k=5) on embeddings, so a new sign class can be added **without retraining**
- 🎯 Accuracy **79.3%** · macro F1 **0.806** on GTSRB test (12,630 images, 43 classes)

### 🧪 AI in Action labs
[repo](https://github.com/doananhquan26072005/ai-thuc-chien-k4) · daily lab forks live on my cohort account [@DAQuan-VinAI](https://github.com/DAQuan-VinAI)

- **Phase 1:** LLM APIs, agents & tool calling, RAG, multi-agent with MCP / A2A, data observability, guardrails with red team vs. blue team, cloud deployment, LLMOps, AI evaluation
- **Track 4:** neural nets & CNNs, 2D perception (detection, segmentation, keypoints), Kalman filters, point clouds, tracking & forecasting, BEV & sensor fusion on Waymo

<details>
<summary>📂 <b>More projects & coursework</b></summary>
<br />

| Repo | What it is |
|---|---|
| [Detect-and-separate-characters-on-license-plates](https://github.com/doananhquan26072005/Detect-and-separate-characters-on-license-plates) | License plate localization and character segmentation |
| [Weather_prediction](https://github.com/doananhquan26072005/Weather_prediction) | Time-series weather forecasting |
| [Debt-calculation-bot](https://github.com/doananhquan26072005/Debt-calculation-bot) | 💸 A Discord bot that works out who owes whom in a group |
| [Fostering-excellent-national-students](https://github.com/doananhquan26072005/Fostering-excellent-national-students) | Algorithm solutions from provincial-team training for the National Olympiad |
| [Machine-Learning](https://github.com/doananhquan26072005/Machine-Learning) · [Pattern-Recognition](https://github.com/doananhquan26072005/Pattern-Recognition) · [Image-Processing](https://github.com/doananhquan26072005/Image-Processing) · [Natural-Language-Processing](https://github.com/doananhquan26072005/Natural-Language-Processing) | HCMUS coursework |
| [Data-Mining](https://github.com/doananhquan26072005/Data-Mining) · [Numerical-Methods-for-Data-Science](https://github.com/doananhquan26072005/Numerical-Methods-for-Data-Science) · [Introduction-to-Artificial-Intelligence](https://github.com/doananhquan26072005/Introduction-to-Artificial-Intelligence) · [SQL](https://github.com/doananhquan26072005/SQL) · [MATLAB](https://github.com/doananhquan26072005/MATLAB) | HCMUS coursework |

</details>

---

## 💼 Experience

**RLHF Data Contributor · Outlier (Scale AI)** · remote · 05/2024 – 01/2025

Ranked pairs of LLM responses on 6 quality criteria across 10+ domains to build RLHF preference data. Rewrote model answers and rated voice samples under QA/QC review.

---

## 🧰 Tech stack

<p align="center">
  <img src="https://skillicons.dev/icons?i=py,cpp,c,r,matlab,latex&perline=6" alt="Languages" /><br />
  <img src="https://skillicons.dev/icons?i=pytorch,opencv,sklearn,fastapi,docker,react,ts,git,github,vscode&perline=10" alt="Frameworks and tools" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/MediaPipe-0097A7?style=flat-square&logo=mediapipe&logoColor=white" alt="MediaPipe" />
  <img src="https://img.shields.io/badge/YOLOv8-111F68?style=flat-square&logo=ultralytics&logoColor=white" alt="YOLOv8" />
  <img src="https://img.shields.io/badge/ONNX_Runtime-005CED?style=flat-square&logo=onnx&logoColor=white" alt="ONNX Runtime" />
  <img src="https://img.shields.io/badge/WebGPU-005A9C?style=flat-square&logo=webgpu&logoColor=white" alt="WebGPU" />
  <img src="https://img.shields.io/badge/Pyodide-3776AB?style=flat-square" alt="Pyodide" />
  <img src="https://img.shields.io/badge/LightGBM-02569B?style=flat-square" alt="LightGBM" />
  <img src="https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white" alt="NumPy" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white" alt="Pandas" />
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white" alt="Jupyter" />
  <img src="https://img.shields.io/badge/Kaggle-20BEFF?style=flat-square&logo=kaggle&logoColor=white" alt="Kaggle" />
  <img src="https://img.shields.io/badge/Colab-F9AB00?style=flat-square&logo=googlecolab&logoColor=white" alt="Google Colab" />
</p>

<p align="center">
  🧮 <b>Math:</b> Linear Algebra · Probability & Statistics · Calculus · Differential Equations
</p>

---

## 🏆 Before all the AI

- 🏫 Alumnus of the Informatics-specialized class at **Le Quy Don High School for the Gifted (Khanh Hoa)**
- 🧩 Trained with the provincial team preparing for the **National High School Olympiad in Informatics**
- ⚔️ Problem solving on **Codeforces** and **VNOI**

---

## 📊 GitHub stats

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api?username=doananhquan26072005&show_icons=true&include_all_commits=true&hide_border=true&theme=tokyonight" />
    <img height="165" src="https://github-readme-stats.vercel.app/api?username=doananhquan26072005&show_icons=true&include_all_commits=true&hide_border=true" alt="GitHub stats" />
  </picture>
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api/top-langs/?username=doananhquan26072005&layout=compact&langs_count=6&hide_border=true&theme=tokyonight" />
    <img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=doananhquan26072005&layout=compact&langs_count=6&hide_border=true" alt="Top languages" />
  </picture>
</p>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://streak-stats.demolab.com?user=doananhquan26072005&hide_border=true&theme=tokyonight" />
    <img src="https://streak-stats.demolab.com?user=doananhquan26072005&hide_border=true" alt="GitHub streak" />
  </picture>
</p>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/doananhquan26072005/doananhquan26072005/output/github-snake-dark.svg" />
    <img src="https://raw.githubusercontent.com/doananhquan26072005/doananhquan26072005/output/github-snake.svg" alt="Snake eating my contribution graph" />
  </picture>
</p>

---

## 🎲 Fun facts

- 🏋️ My models train on Kaggle and Colab. I train at the gym.
- 📚 Reading books to widen my view, 🎮 gaming, and 🎬 over-analyzing films
- 🚨 Ask me about false alarms per hour. I come with confidence intervals.

---

## 📫 Let's connect

<p align="center">
  <a href="https://www.linkedin.com/in/anh-qu%C3%A2n-%C4%91o%C3%A0n-a497853a2/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge" alt="LinkedIn" /></a>
  <a href="mailto:doananhquan26072005@gmail.com"><img src="https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
  <a href="https://www.facebook.com/doananhquan.2607"><img src="https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white" alt="Facebook" /></a>
</p>

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:7B2FF7,100:00F7FF&height=110&section=footer" alt="" />
