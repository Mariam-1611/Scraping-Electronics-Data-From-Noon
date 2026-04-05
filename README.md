# Scraping-Electronics-Data-From-Noon
A project is focus on scrapping the data electronic data specifically using selenium library from python
A Python web scraper that extracts mobile phone product data from 
[Noon.com Egypt](https://www.noon.com/egypt-ar/electronics-and-mobiles/mobiles-and-accessories/mobiles-20905/)
across 18 pages and saves it into a structured dataset.

---

## 📦 Dataset Columns

| Column | Description |
|---|---|
| `product_name` | Full name of the mobile phone |
| `price` | Price in Egyptian Pounds (EGP) |
| `rating` | Average star rating (e.g. 4.4) |
| `review_count` | Number of customer reviews |
| `photo_url` | Direct URL to the product image |

---

## 🛠️ Technologies Used

- **Python 3.12**
- **Selenium** — browser automation to handle JavaScript rendering
- **webdriver-manager** — auto-downloads the correct ChromeDriver
- **pandas** — data manipulation and CSV/Excel export
- **openpyxl** — saving to Excel format

---

## ⚙️ Setup Instructions

### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/noon-scraper.git
cd noon-scraper
```

### 2. Create a virtual environment
```bash
python -m venv noon_env
```

### 3. Activate the environment

On Windows:
```bash
noon_env\Scripts\activate
```

On Mac/Linux:
```bash
source noon_env/bin/activate
```

### 4. Install dependencies
```bash
pip install selenium webdriver-manager pandas openpyxl ipykernel
```

### 5. Run the notebook
Open `scraping_noon.ipynb` in VS Code and run all cells from top to bottom.

---

## 📁 Project Structure
noon-scraper/
│
├── scraping_noon.ipynb       # Main Jupyter notebook
├── noon_products.csv         # Output dataset (CSV)
└── README.md                 # Project documentation
---

## 🔍 How It Works

1. **Selenium** opens a real Chrome browser and navigates to Noon
2. For each of the **18 pages**, the scraper:
   - Waits for the page to fully load
   - Scrolls down to trigger lazy-loaded images
   - Extracts all product names, prices, ratings, review counts, and photo URLs
3. All lists are **aligned** to the same length to handle missing data
4. Duplicates are removed and the price column is cleaned to a numeric format
5. The final dataset is saved as both `.csv` and `.xlsx`

---

## ⚠️ Notes

- Noon uses **JavaScript rendering (React/Next.js)** so simple `requests` scraping
  won't work — Selenium is required
- Add `time.sleep()` delays are included between pages to avoid getting blocked
- CSS class names on Noon may change over time — if the scraper stops working,
  inspect the page in Chrome DevTools and update the selectors in Cell 13
- Output CSV uses `utf-8-sig` encoding so Arabic text displays correctly in Excel

---

## 👩‍💻 Author

Made by **Mariam Mohamed Goda**  
DEPI
