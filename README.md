# NGN Studio

**Next Generation NCLEX Practice Environment**

NGN Studio is a desktop application for creating, managing, and taking Next Generation NCLEX (NGN) practice exams. It supports all six NGN question formats, AI-assisted exam generation, a hierarchical exam library with folder organization, and an immediate feedback mode for active learning.

---

## Features

- **All six NGN question types** — Multiple Choice, Select All That Apply, Ordered Response, Matrix/Grid, Drag & Drop, and Fill in the Blank (medication math)
- **AI exam generation** — built-in prompt for Claude, GPT-4o, or Gemini; paste JSON directly into the app
- **Manual exam creator** — build and edit exams question-by-question with a full GUI
- **Hierarchical library** — organize exams into nested folders mirroring your courses
- **Exam packages** — import a folder or ZIP archive of multiple exams at once; share packages via GitHub
- **Immediate feedback mode** — see the correct answer and rationale after each question before advancing
- **Score tracking** — results are saved per exam; retake or review past attempts any time
- **Timer** — configurable per exam; auto-submits when time expires
- **Question navigator** — color-coded sidebar shows answered, flagged, correct, incorrect, and partial-credit status at a glance
- **Study tools** — highlight question text, cross out answer options, flag questions for review

---

## Installation

Download the latest installer from the [Releases](../../releases) page.

- **Windows** — run the `.exe` installer. NGN Studio installs to `%LOCALAPPDATA%\ngn_studio` and creates a Start Menu shortcut.
- **macOS** — open the `.dmg` and drag NGN Studio to Applications.

No additional runtime or account is required.

---

## Getting Started

### 1. Pick an exam

The home screen shows two sections in the left sidebar:

- **Example Exams** — bundled exams shipped with the app, including a *Question Types Guide* that walks through every format with a real clinical scenario.
- **My Exams** — your personal library, organized in folders you create.

Click an exam card to select it, then use the buttons in the footer to start, retake, or review it.

### 2. Configure options

Two toggles sit at the bottom of the home screen:

| Toggle | Effect |
|---|---|
| **Scramble order** | Randomizes question order each time you start the exam |
| **Immediate feedback** | Shows the correct answer and rationale after each question before you advance |

### 3. Take the exam

The exam screen has four areas:

- **Top bar** — exam title, question counter, countdown timer, and Flag for Review button
- **Navigator** (left sidebar) — numbered buttons for every question; click any to jump to it
- **Viewport** — question stem and answer interface
- **Bottom bar** — Previous, Next, and Submit Exam buttons

### 4. Review your results

After submitting, the Results screen shows your total score, a per-type breakdown, and an expandable card for every question showing your answer, the correct answer, and the rationale.

Results are saved automatically. The next time you open that exam you will see your score and the option to **Review Results** (read-only replay of your last attempt) or **Retake Exam** (fresh attempt that overwrites the previous result).

---

## Question Types

| Type | Format | Scoring |
|---|---|---|
| **Multiple Choice (MCQ)** | Pick exactly one answer | 1 pt if correct, 0 if not |
| **Select All That Apply (SATA)** | Pick every correct answer | +1 per correct selection, −1 per incorrect, floored at 0 |
| **Ordered Response** | Drag all steps into the correct sequence | 1 pt for a perfect sequence, 0 otherwise |
| **Matrix / Grid** | For each row, select one column | 1 pt per correct row, scored independently |
| **Drag & Drop** | Drag only the correct items into the answer box | +1 per correct item, −1 per incorrect item, floored at 0 |
| **Fill in the Blank** | Type a numeric answer (medication math) | 1 pt if within the defined tolerance range |

---

## Managing Your Exam Library

### Creating folders

Click **+ New Folder** at the bottom of the left sidebar, or hover over any existing folder and click the **+** icon that appears. Folders can be nested to any depth — for example:

```
My Exams/
  Fundamentals/
    Week 1/
      vital_signs_exam.json
    Week 2/
  Med-Surg/
    Cardiovascular/
```

### Organizing exams

Drag any exam card and drop it onto a folder in the sidebar to move it. You can also delete individual exams or entire folders (you will be prompted to confirm before anything is deleted).

### Importing a single exam (AI-generated JSON)

Click **AI Import** in the footer, follow the three-step prompt, and either paste the JSON from your clipboard or open a `.json` file. The exam is saved into your currently selected folder automatically.

### Importing an exam package (folder or ZIP)

Click **Package** in the footer to import a whole collection at once:

- **From Folder** — select a local directory; its entire folder structure and all valid exam JSON files are copied into your library.
- **From ZIP** — select a `.zip` archive (e.g. downloaded from GitHub); the app extracts it and copies the contents.

The package is placed inside whichever folder you have selected in the sidebar.

### Creating exams manually

Click **Create Exam Manually** on the home screen to open the creator. You can add questions of any type, edit them with a full GUI, validate the exam, and save it as a `.json` file.

---

## AI Exam Generation

NGN Studio includes a ready-to-use prompt for any large AI model. The workflow:

1. Open the **AI Import** modal and copy the prompt.
2. In your AI chat (Claude, GPT-4o, Gemini, etc.), attach your lecture slides or notes, then paste the prompt. Fill in the number of questions before sending.
3. Copy the `json` code block the AI returns.
4. Back in NGN Studio, click **Paste from Clipboard** — the exam is imported and saved immediately.

> **Tip:** Use the most capable model available. Free-tier models often produce shallow questions that do not reflect true NGN difficulty.

The prompt instructs the AI to use all six question types, apply NGN-level clinical reasoning, write thorough rationales that explain why every distractor is wrong, and output valid JSON that the app can parse without modification.

---
