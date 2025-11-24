# LUGAN Repository Structure & Organization

To maintain clarity and ensuring that our research and resources remain accessible, LUGAN follows a strict file organization strategy. Please adhere to these guidelines when creating new files or repositories.

-----

## 1\. Documentation & Governance

**Where:** **`documentation`** (This repository)

This repository is the central archive for the organization's "bureaucracy" and identity. It is the single source of truth for how we operate.

  * **Content:**
      * Foundational files (Manifesto, Code of Conduct).
      * Policy documents and procedural guidelines.
      * Organizational structure and role definitions.
      * General "Join Us" and "Contributing" guides.

-----

## 2\. Events Management

**Where:** **`events`** repository

All information regarding our meetups, workshops, and gatherings, whether they are **past**, **in-progress**, or **future**, must be stored in the dedicated `events` repository.

  * **Structure:** inside the `events` repo, create a specific folder for each event (e.g., `YYYY-MM-DD_EventName`).

### 📂 Handling Event Materials

When organizing an event, we distinguish between **presentation materials** and **source code**:

#### A. Slides, PDFs, and Notes

**Location:** inside the specific folder in the `events` repository.

  * If you have a slide deck (`.pdf`, `.pptx`), a flyer, or a text summary of the meeting, upload it directly to the event's folder.

#### B. Code and Technical Workshops

**Location:** A **dedicated new repository**.

  * **Do not** upload complex codebases, software projects, or heavy workshop exercises directly into the `events` repo.
  * **The Workflow:**
    1.  Create a **new repository** for the code (e.g., `workshop-python-automation`).
    2.  Push the code there.
    3.  Go back to the specific folder in the `events` repo.
    4.  Add a `README.md` or a link file pointing to that new code repository.

-----

## 🔗 Visual Example

Here is how the organization looks in practice:

```text
github.com/Linux-User-Group-ANcona/
│
├── documentation/ (This Repo)
│   ├── MANIFESTO.md
│   ├── CODE_OF_CONDUCT.md
│   └── STRUCTURE.md
│
├── events/ (The History Log)
│   ├── 2025-10-15_IntroToLinux/
│   │   └── slides.pdf
│   │
│   └── 2025-11-20_AdvancedPython/
│       ├── presentation.pdf
│       └── README.md  -----> [LINK to 'workshop-python-code' repo]
│
└── workshop-python-code/ (Actual Code)
    ├── main.py
    └── requirements.txt
```

-----

## Summary Table

| Content Type | Destination Repository | Note |
| :--- | :--- | :--- |
| **Policies, Rules, CoC** | `documentation` | Keep this repo clean and text-focused. |
| **Event Slides/PDFs** | `events` | Inside a specific folder named by date. |
| **Event Source Code** | New Dedicated Repo | Link this new repo inside the `events` folder. |