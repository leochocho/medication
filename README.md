# Medication Tool

The **Medication Tool** is a lightweight, browser-based medication lookup interface designed for clinicians, students, and healthcare workers. It allows rapid lookup of medication names (including misspellings and trade names) with:

- 🔍 **Autocorrected drug name matching** (via Levenshtein distance + smart substring weighting)  
- 💊 **Generic + Australian trade names**  
- 🧾 **High-level clinical use summaries**  
- 👁 **Optional optometry mode** showing ocular side-effects  
- 🚨 **High-priority ocular risk warnings** (clearly highlighted in red)  
- 📋 **Copy-to-clipboard for drug names**  
- 📚 **A full medication list viewer**, grouped by system (e.g. Diabetes, Hypertension, ADHD, Women’s Health, Glaucoma, HIV/PrEP, etc.)  
- 🔍 **Filterable lists** (ocular side-effects only, or high-risk ocular meds only)

This tool is designed primarily for **clinicians who want fast access to medication information during consultations**, especially optometrists who need to evaluate systemic medications with ocular relevance.

It works **fully offline**, requires **no installation**, and runs entirely in the browser.


---

## 🚀 Features

### 🔍 Smart Drug Lookup
- Type any medication name (even badly misspelled)
- The tool finds the closest match using fuzzy string matching
- Shows generic name, category, clinical use, and aliases

### 👁 Optometry Mode
- Toggle ocular side-effects on/off  
- Highlights important warnings  
- Includes a filter for:
  - *All drugs with ocular effects*
  - *Only high-priority ocular risk drugs* (e.g. HCQ, tamoxifen, isotretinoin, ethambutol, topiramate, steroids)

### 📚 Full Medication List Viewer
- View entire database grouped by:
  - Diabetes  
  - Hypertension / Cardiovascular  
  - Mental Health  
  - ADHD  
  - Lipids / Cholesterol  
  - Women’s Health / Contraceptives  
  - HIV / PrEP  
  - Ocular medications  
  - Cancer / Dermatology  
  - And many more
- Filterable by ocular relevance

### 📝 Copy to Clipboard
- Quickly copy the generic drug name for clinical notes

---

## 🗂 How to Use

1. Open the HTML file in any modern browser (Chrome, Edge, Safari, Firefox).
2. Type a medication name:
    - "metfornin" → **Metformin**  
    - "liptor" → **Atorvastatin (Lipitor)**  
    - "ozampic" → **Semaglutide (Ozempic)**  
3. Turn **Optometry Mode ON** to display ocular info.
4. Click **View All Medications** to browse the full grouped list.

---

## 🧩 Code Structure

- **HTML**: Interface layout + results card  
- **CSS**: Styles, responsive layout, dark theme  
- **JavaScript**:
  - Drug database (`DRUG_DATABASE`)
  - Fuzzy matching algorithm
  - Rendering logic
  - Filters  
  - Ocular priority flag system  
  - Clipboard handling  

Everything is contained in a **single HTML file** for easy portability.

---

## 📦 Adding or Editing Medications

Inside the HTML, medications are stored in the `DRUG_DATABASE` array:

```js
{
  name: "Hydroxychloroquine",
  category: "DMARD",
  use: "Used for RA/SLE...",
  group: "Rheumatology / Immunology",
  aliases: ["Plaquenil"],
  ocular: "Retinal toxicity…",
  ocularPriority: true
}

