# Multimodal Video Evaluator (MVE)

[![Version](https://img.shields.io/badge/version-v2.0-blue.svg)](./prompts/v2.0/)
[![Status](https://img.shields.io/badge/v3.0-In_Development-yellow.svg)](./prompts/v3.0-draft/)
[![Target_Platform](https://img.shields.io/badge/Platform-Google_Gem-green.svg)](https://gemini.google.com/)
[![License](https://img.shields.io/badge/License-MIT-lightgrey.svg)](LICENSE)

An automated instructional video evaluator built on Google Gemini. MVE analyzes videos against **127 design guidelines** across **23 principle-based frameworks** spanning four major research areas: **multimedia learning**, **video engagement**, **video production style**, and **visual scaffolding**—all grounded in empirical research. 

---

## 📌 Overview

The **Multimodal Video Evaluator (MVE)** acts as an automated instructional design expert. By processing parallel visual, text (OCR), and auditory data streams, MVE evaluates video lessons across four weighted pedagogical frameworks:

1. **Multimedia Learning Principles (50%)**: Assesses 19 multimedia learning principles across cognitive load management, social agency, and visual dynamics: *multimedia*, *redundancy*, *coherence*, *spatial contiguity*, *temporal contiguity*, *signaling*, *segmenting*, *modality*, *pre-training*, *personalization*, *voice*, *image*, *embodiment*, and *animation* (Principles 1–5).
2. **Video Engagement Rules (20%)**: Evaluates duration limits, optimal speaking rates (WPM), and instructor visual framing.
3. **Production Styles (10%)**: Validates macro-level production format appropriateness against learning objectives.
4. **Visual Scaffolding & Layout (20%)**: Analyzes data visualization, procedural flowcharts, and visual cues.

---

## 🗂 Version Roadmap & Matrix

| Version | Status | Primary Focus / Notes | System Prompt | Knowledgebase |
| :--- | :--- | :--- | :--- | :--- |
| **v1.0** | Legacy | Initial prompt prototype and core rules. | Archived | Archived |
| **v2.0** | **Current Stable** | Extended multimodal reasoning at 91% accuracy benchmark acvhieved. | [`/prompts/v2.0/`](./prompts/v2.0/) | [`/knowledgebase/v2.0/`](./knowledgebase/v2.0/) |
| **v3.0** | 🚧 In Development | Aiming at 95% accuracy benchmark and visual examples extensoion. | [`/prompts/v3.0-draft/`](./prompts/v3.0-draft/) | [`/knowledgebase/v3.0-draft/`](./knowledgebase/v3.0-draft/) |

---

## 🚀 Quick Start: Running MVE on Google Gemini

MVE is optimized and tested for **Google Gemini 3.1 Pro** due to its long-context multimodal window (fpr accuracy) and multi-stream reasoning capabilities.

### Method 1: Create a Custom "Gem" in Google Gemini (No-Code / Interactive)

The easiest way to use MVE without writing code is to set up a custom **Gem** inside Google Gemini Advanced:

1. Open [Google Gemini](https://gemini.google.com/) and navigate to the **Gem Manager** (or click **Explore Gems** > **Create new Gem**).
2. Set the Gem title to **Multimodal Video Evaluator (MVE)**.
3. Open `prompts/v2.0/system_prompt.md` from this repository and copy-paste its full contents into the **Instructions** text box.
4. Upload `knowledgebase/v2.0/multimedia_video_knowledgebase.md` directly from this repository as a **Knowledge File** attached to the Gem (using the repository's `.md` file ensures full version alignment with Git and optimal Markdown structure parsing for Gemini).
5. Click **Save**.
6. **To evaluate a video:** Open your new Gem, upload your target video file (`.mp4`, `.webm`, or `.mov`), and send your video context using this template:

   ```text
   Video Title: [Insert Video Title]
   Target Audience: [e.g., Novice / High School Students / Senior Engineers]
   Learning Objective: [e.g., Explain how a hydraulic brake system works]

   Please execute a full MVE v2.0 evaluation on the attached video using the context above.

---

### Method 2: Google AI Studio Web App (No-Code / This is still work in progress)

If you want to build a standalone web application for team or public use without writing code, use Google AI Studio's **Build Mode**:

1. Open [Google AI Studio](https://aistudio.google.com/) and switch to **Build Mode** (or click **Create New App** / **Build**).
2. **Prompt the App Builder:** Copy and paste the following prompt into the AI Studio prompt box:

   ```text
   Build a full-stack web application for the Multimodal Video Evaluator (MVE). 

   Requirements:
   1. UI Inputs: Allow users to upload a video file (.mp4, .webm) and enter three text fields: Video Title, Target Audience, and Learning Objective.
   2. Evaluation Logic: Use the Gemini 3.1 Pro model. Initialize the prompt with the system instructions from `prompts/v2.0/system_prompt.md` and reference knowledge from `knowledgebase/v2.0/multimedia_video_knowledgebase.md`.
   3. Output: Display the executive score, certification badge (Exemplary/Effective/Developing/Critical), detailed score breakdown table, red flags, and cross-modal timeline mismatches in a clean, responsive layout.
