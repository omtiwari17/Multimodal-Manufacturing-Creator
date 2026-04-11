# Multimodal Manufacturing Creator

A Generative AI application that transforms a single manufacturing concept prompt into both a structured technical narrative and a high-fidelity visual prototype simultaneously by integrating a Large Language Model with an image generation model.

---

## Project Overview

This project demonstrates the synergy between two distinct AI model types working from a single input. The user enters any manufacturing concept and the system invokes Google Gemini 2.5 Flash to generate a professional five-section technical description while simultaneously calling the Flux diffusion model via Pollinations.ai to render an engineering-quality visual illustration of the concept.

The result is a multimodal output text and image produced from one prompt, displayed side by side in a clean Streamlit interface. No backend server, no database, no complex infrastructure. Just two AI APIs and a single Python file.

---

## What It Does

| Input | Model | Output |
|---|---|---|
| Manufacturing concept (text) | Gemini 2.5 Flash: Text-to-Text | Structured technical narrative (5 sections) |
| Manufacturing concept (text) | Flux via Pollinations.ai: Text-to-Image | Visual prototype / engineering illustration |

---

## Key Features

- Single prompt drives two completely different AI model types simultaneously
- Text output structured into Overview, Working Principle, Key Components, Applications, and Advantages
- Image generation with selectable visual styles blueprint, photorealistic, 3D render, or schematic
- Six built-in manufacturing concept examples for quick demonstration
- No image generation API key required Pollinations.ai is free and open
- Gemini API key entered at runtime only never stored in code or images
- Multimodal workflow diagram rendered inside the app explaining the pipeline

---

## Tech Stack

| Category | Technology |
|---|---|
| Frontend | Python, Streamlit |
| Text Generation | Google Gemini 2.5 Flash (LLM) |
| Image Generation | Flux model via Pollinations.ai |
| HTTP & Image Handling | requests, Pillow (PIL) |
| Version Control | Git, GitHub |

---

## Project Structure

```
Multimodal-Manufacturing-Creator/
│
├── app.py               # Complete Streamlit application
├── requirements.txt     # Python dependencies
├── README.md            # Project documentation
└── .gitignore           # Excludes cache, secrets, and env files
```

---

## How to Run Locally

**Prerequisites**
- Python 3.9 or above
- A valid Google Gemini API key (free tier works)

**Step 1 - Clone the repository**
```bash
git clone https://github.com/omtiwari17/Multimodal-Manufacturing-Creator.git
cd Multimodal-Manufacturing-Creator
```

**Step 2 - Install dependencies**
```bash
pip install -r requirements.txt
```

**Step 3 - Launch the app**
```bash
streamlit run app.py
```

**Step 4 - Use the app**

Open the browser at `http://localhost:8501`, paste your Gemini API key in the sidebar, type a manufacturing concept or pick an example, and click Generate.

---

## Example Concepts to Try

- Robotic welding arm for automotive assembly line
- CNC milling machine for aerospace precision parts
- Injection molding press for plastic enclosures
- Conveyor belt sorting system with vision sensors
- Industrial 3D printer for metal components
- Automated PCB soldering machine for electronics

---

## Multimodal GenAI Workflow

```
User Input (manufacturing concept prompt)
            │
            ├──────────────────────────────────────┐
            │                                      │
            ▼                                      ▼
  TEXT-TO-TEXT MODEL                    TEXT-TO-IMAGE MODEL
  Gemini 2.5 Flash                      Flux via Pollinations.ai
  (Google Gemini API)                   (HTTP GET — no key needed)
            │                                      │
            ▼                                      ▼
  Technical Narrative                   Visual Prototype
  (5-section structured text)           (Engineering illustration)
```

Both models receive the same prompt and run independently neither depends on the output of the other.

---

## API Reference

| API | Auth | Endpoint |
|---|---|---|
| Google Gemini 2.5 Flash | API Key (user-provided at runtime) | `generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash` |
| Pollinations.ai Flux | None: free and open | `image.pollinations.ai/prompt/{encoded_prompt}` |

---

## Group Members

| Sr No | Name | Enrollment Number |
|---|---|---|
| 01 | Om Tiwari | EN22CS301669 |
| 02 | Paridhi Shirwalkar | EN22CS301684 |
| 03 | Nitesh Chourasiya | EN22CS301660 |
| 04 | Mradul Jain | EN22CS301616 |

---

- **Institution**: Medicaps University, Datagami Skill Based Course
- **Academic Year**: 2025-2026
- **Industry Mentor**: Prof. Ajaj Khan