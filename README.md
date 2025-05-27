# Troubleshooting Common Issues – A DITA-Based Project

This project is a structured DITA-based documentation set that delivers solutions for common technical issues users frequently encounter. It showcases custom topic specialization, semantic troubleshooting structure, manual styling with CSS, and static HTML output publishing.

The goal is to provide a **realistic and reusable DITA solution** that emphasizes semantic content architecture, maintainability, and clarity—especially for technical writing and user support scenarios.

---

## Overview of DITA Structure and Elements

This project includes a total of **five DITA topics**, organized and authored using semantic DITA standards and specialization.

### Concept Topic
- `intro_troubleshooting.dita`  
  - A standard DITA **concept** topic that introduces the troubleshooting guide.
  - Uses:
    - `<title>` – Specifies the topic's name.
    - `<shortdesc>` – Provides a concise summary for quick understanding.
    - `<conbody>` – Holds the main content of the concept.
    - `<section>` – Used to segment related paragraphs logically.
    - `<p>` – For basic paragraphs of information.

### Specialized Troubleshooting Topics
These three topics are specialized using a custom `<troubleshooting>` element and its sub-elements:

- `issue_login_failure.dita`
- `issue_slow_performance.dita`
- `issue_sync_errors.dita`

Each topic uses:

- `<troubleshooting>` – A container element that encapsulates a structured description of the issue.
- `<problem>` – Defines what the user is experiencing (e.g., login failure).
- `<cause>` – Optionally explains the technical reason(s) behind the problem.
  - May contain paragraphs (`<p>`), unordered lists (`<ul>`), ordered lists (`<ol>`), and tables (`<table>`) for elaboration.
- `<remedy>` – Offers one or more solutions with steps or recommendations, using lists or paragraphs.

These topics also include:

- `<image>` with `alt` – To visually support the troubleshooting steps while ensuring accessibility.
- `<b>` – To emphasize keywords or labels.
- `<xref>` – To link to related content or sections.

Nested list support was also implemented:
- `<ul>` and `<ol>` with `<li>` allow for both unordered and step-by-step instructions.
- Sublists were used within remedies to handle multi-layered resolution steps.

### Reference Topic
- `troubleshooting_reference.dita`  
  - A **reference-type** topic that lists error codes, tools, or related support resources.
  - Makes use of:
    - `<table>` – For tabular data representation.
    - `<tgroup>`, `<colspec>`, `<thead>`, `<tbody>`, `<row>`, `<entry>` – For detailed table structure.
    - `<codeph>` – To highlight inline code snippets such as commands or error codes.

---

## 🛠Specialization Details

This project includes **manual domain specialization** to support structured troubleshooting use cases.

### Custom Elements Created

- `<troubleshooting>`: A new root element that organizes all information about a particular issue.
- `<problem>`: Defines the problem statement clearly.
- `<cause>`: Explains what led to the issue (optional).
- `<remedy>`: Provides step-by-step or summary solutions.

These elements were declared using:

1. **`.ent` File**  
   Contains DTD-compliant element and attribute declarations. Each element includes proper content models and class attributes needed for DITA-OT processing.

2. **`.mod` File**  
   Loads the `.ent` file and declares domain attribute extensions for integration into base DITA topics.

3. **`.dtd` File**  
   Integrates the specialized domain with the base topic DTD.

All specialization steps were completed **manually** to avoid using plugins and ensure deeper understanding of DITA architecture.

---

## CSS Styling

A minimal custom CSS file was developed to enhance the look and feel of the HTML5 output. Key goals included readability, consistent formatting, and clean visual hierarchy.

### Styled Elements:

- **Text & Structure**:
  - `body`, `p`, `.shortdesc`, `.ul`, `.li`, `.title` – Improved typography and spacing.
- **Headings**:
  - `h1`, `h2`, `h3`, `h4` – Unified font sizes and colors.
- **Tables**:
  - `table`, `td`, `th` – Styled borders and padding for improved legibility.
- **Images**:
  - `img` – Centered with responsive layout.
- **Code**:
  - `code` – Styled inline code with background and monospace font.

### CSS Application:

- CSS was manually linked to each output HTML file by editing the `<head>` section.
- This ensures consistent styling **without relying on DITA-OT plugins** or transformation overrides.

---

## Output and GitHub Deployment

- Final output was generated using **DITA Open Toolkit (DITA-OT)**.
- Output content was placed in a manually created `docs/` folder to enable GitHub Pages compatibility.
- The standard Git workflow was used to push the project:
  - Created `docs/`
  - Copied output files into `docs/`
  - Added, committed, and pushed files to GitHub

---

## Key Highlights

- **DITA Topic Types**: Demonstrates use of concept, reference, and custom specialized topics.
- **Manual Specialization**: No plugin used—entire troubleshooting domain was created manually.
- **Semantic Content**: Follows best practices for structured content and reuse.
- **CSS Styling**: Lightweight and user-friendly HTML5 presentation.
- **GitHub-Ready**: Organized output for static preview or GitHub Pages hosting.

---
