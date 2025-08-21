# 📊 NSE Option Chain Data Fetcher – Max Pain Analysis

### 📌 Overview  
This Python project automates the **extraction, processing, and storage of NSE Option Chain (OC) data** for **equities** and **indices**. It calculates **Max Pain** (strike with minimum total loss for option writers) and organizes **expiry-wise summaries** for quick market insights.  

✅ **Equities:** Per-expiry Max Pain for all tracked stocks → `{Equity}_MaxPain_Summary.csv`  
✅ **Indices:** NIFTY & BANKNIFTY, per-expiry Max Pain + summary CSVs  
✅ **Automation:** Handles hundreds of equities, missing/malformed files, and consolidates expiry-wise reports  
✅ **Optional Visualization:** Max Pain distribution charts  

---

### 🏗️ Workflow
1. **Option Chain Reading** – Normalizes CSV columns: `Strike Price`, `Call OI`, `Put OI`  
2. **Total Loss Calculation** – Computes losses for option writers at each strike  
3. **Max Pain Detection** – Finds the strike with minimum total loss  
4. **Equity/Index Processing** – Generates per-symbol summary CSVs  
5. **Expiry-Wise Consolidation** – Aggregates Max Pain across equities: `Equity_MaxPain_{expiry}.csv`  
6. **Resilience** – Handles missing, empty, or malformed files gracefully  
7. **Optional Plotting** – Enable `ENABLE_PLOTS = True` for charts  

---

### 📂 Output Structure
```bash
monthly_options_view/
├── Equity_Expiry_MaxPain/              # ⚡ Consolidated expiry-wise Max Pain
│   ├── Equity_MaxPain_2025-08-28.csv
│   ├── Equity_MaxPain_2025-09-04.csv
│   └── Equity_MaxPain_2025-09-11.csv
│
├── NIFTY/                               # 📈 NIFTY option chains
│   ├── NIFTY_2025-08-28.csv
│   ├── NIFTY_2025-09-04.csv
│   ├── NIFTY_2025-09-11.csv
│   └── NIFTY_MaxPain_Summary.csv
│
└── BANKNIFTY/                            # 📈 BANKNIFTY option chains
    ├── BANKNIFTY_2025-08-28.csv
    ├── BANKNIFTY_2025-09-04.csv
    ├── BANKNIFTY_2025-09-11.csv
    └── BANKNIFTY_MaxPain_Summary.csv
