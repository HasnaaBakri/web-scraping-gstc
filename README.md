# Web Scraping (GSTC PDF Downloader)

This project contains organized scripts for scraping PDF links from the [الأمانة العامة للجان الزكوية و الضريبية و الجمركية](https://gstc.gov.sa/ar/Decisions/Pages/decisions.aspx?year=2020&committee=&classification=&PageIndex=1)) website and downloading them into structured folders.

## 📁 Project Structure

```
web-scraping-collection/
├── data/                     # Stores scraped link files and downloaded PDFs
│   ├── gstc_pdf_links_2020.txt
│   └── gstc_pdf_links_2021.txt
├── scripts/                  # Contains Python scraping and downloading notebooks
│   ├── scrape_links.ipynb    # Step 1: Scrapes PDF links
│   └── download_pdfs.ipynb   # Step 2: Downloads PDFs from links
├── .gitignore
├── requirements.txt
└── README.md
```

## 🐍 Set Up Instructions

### 1. Create and activate a virtual environment

**Windows:**
```bash
python -m venv .venv
.venv\Scripts\activate
```

### 2. Install required packages

```bash
pip install -r requirements.txt
```

> Make sure you have Chrome and [ChromeDriver](https://sites.google.com/a/chromium.org/chromedriver/) installed and accessible in your PATH.

---

## 🚀 How to Use

### Step 1: Scrape PDF Links

Run `scrape_links.ipynb` notebook first. This will:
- Open GSTC website pages using Selenium.
- Collect all `.pdf` links.
- Save them to text files under the `data/` folder, like:
  - `gstc_pdf_links_2020.txt`
  - `gstc_pdf_links_2021.txt`

### Step 2: Download the PDFs

Run `download_pdfs.ipynb` notebook. It will:
- Read the saved link files.
- Create folders by year inside `data/`.
- Download each PDF in chunks with progress bars using `tqdm`.

---

## 📌 Notes

- The `data/` folder must be at the root of the project.
- All downloaded PDFs are saved inside `data/<year>/` folders.
- You can edit the list of years and number of pages in `scrape_links.ipynb`.
- URLs containing `"E-service-guideline"` are filtered out.

---
