# 📦 My Dataset Repository

A centralized collection of datasets organized by type, each with its own documentation.

---

## 📂 Folder Structure

```
datasets-repo/
│
├── tabular/          → CSV, Excel, SQL-style structured data
├── images/           → Image datasets (classification, detection, etc.)
├── text-nlp/         → Text corpora, NLP datasets
├── audio-video/      → Audio clips, video datasets
├── mixed/            → Multi-modal or uncategorized datasets
│
└── CATALOG.md        → Quick-reference index of all datasets
```

---

## 📋 Dataset Catalog

| # | Name | Type | Description | Size | Subjects | Source |
|---|------|------|-------------|------|----------|--------|
| 1 | [HAPT](tabular/HAPT-smartphone-activities/README.md) | Tabular / Time-Series | Smartphone (waist) accelerometer + gyroscope from 30 subjects. 6 activities + 6 postural transitions. 561 features per window. | 75.9 MB | 30 | [UCI #341](https://archive.ics.uci.edu/dataset/341) |
| 2 | [PAMAP2](tabular/PAMAP2-physical-activity/README.md) | Tabular / Time-Series | 3 IMUs (wrist, chest, ankle) + heart rate monitor. 9 subjects, 18 activities. 3.8M raw readings at 100Hz. | 656.3 MB | 9 | [UCI #231](https://archive.ics.uci.edu/dataset/231) |
| 3 | [WISDM](tabular/WISDM-smartphone-smartwatch/README.md) | Tabular / Time-Series | Simultaneous phone + smartwatch (accel + gyro). 51 subjects, 18 activities × 3 min each. Also usable for biometric ID. | 295.9 MB | 51 | [UCI #507](https://archive.ics.uci.edu/dataset/507) |

> ✏️ Add a new row every time you add a dataset. Each dataset also has its own `README.md` inside its folder.

---

## 🗂️ How to Add a New Dataset

1. Pick the right folder (`tabular/`, `images/`, etc.)
2. Create a subfolder: `tabular/my-dataset-name/`
3. Put your data file(s) inside
4. Copy the template below and save it as `tabular/my-dataset-name/README.md`
5. Add a row to the catalog table above

---

## 📄 Dataset README Template

```markdown
# Dataset Name

## Summary
One or two sentences describing what this dataset is.

## Details
- **Type:** Tabular / Images / Text / Audio / Mixed
- **Format:** CSV / JSON / JPEG / MP3 / etc.
- **Size:** e.g. 50 MB
- **Rows / Samples:** e.g. 10,000 rows
- **License:** e.g. CC BY 4.0 / MIT / Public Domain

## Source
- Original source / paper / URL

## Columns / Labels
| Column | Type | Description |
|--------|------|-------------|
| id     | int  | Unique identifier |
| label  | str  | Target class |

## Use Cases
- What problems or tasks is this dataset good for?

## Notes
- Any quirks, missing values, or important preprocessing steps
```

---

## ⚙️ Large Files

For datasets **over 50 MB**, do NOT commit the raw file. Instead:
- Use **[Git LFS](https://git-lfs.com/)** for files up to ~2 GB
- Or add a `download.sh` script that fetches the data from its original source

```bash
# Example download.sh
wget https://source-url.com/dataset.zip -O data.zip
unzip data.zip
```
