# India-Stocks-901-930-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 901 to 930)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-901-930-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (901 to 930)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 901 | `CPEDU` | Career Point Edutech Limited | `CPEDU.NS` |
| 902 | `CPL` | Captain Polyplast Limited | `CPL.NS` |
| 903 | `CRAMC` | Canara Robeco Asset Management Company Limited | `CRAMC.NS` |
| 904 | `CRAVATEX` | Cravatex Limited | `CRAVATEX.NS` |
| 905 | `CREATIVEYE` | Creative Eye Limited | `CREATIVEYE.NS` |
| 906 | `CREST` | Crest Ventures Limited | `CREST.NS` |
| 907 | `CRESTO` | CRESTO TECHNO LIMITED | `CRESTO.NS` |
| 908 | `CRIZAC` | Crizac Limited | `CRIZAC.NS` |
| 909 | `CROWN` | Crown Lifters Limited | `CROWN.NS` |
| 910 | `CRSL` | Cressanda Railway Solutions Limited | `CRSL.NS` |
| 911 | `CSBBANK` | CSB Bank Limited | `CSBBANK.NS` |
| 912 | `CSLFINANCE` | CSL Finance Limited | `CSLFINANCE.NS` |
| 913 | `CSM` | CSM Technologies Limited | `CSM.NS` |
| 914 | `CTE` | Cambridge Technology Enterprises Limited | `CTE.NS` |
| 915 | `CUBEXTUB` | Cubex Tubings Limited | `CUBEXTUB.NS` |
| 916 | `CURAA` | Cura Technologies Limited | `CURAA.NS` |
| 917 | `CYBERMEDIA` | Cyber Media (India) Limited | `CYBERMEDIA.NS` |
| 918 | `CYBERTECH` | Cybertech Systems And Software Limited | `CYBERTECH.NS` |
| 919 | `CYIENTDLM` | Cyient DLM Limited | `CYIENTDLM.NS` |
| 920 | `DAICHI` | Dai-Ichi Karkaria Limited | `DAICHI.NS` |
| 921 | `DALMIASUG` | Dalmia Bharat Sugar and Industries Limited | `DALMIASUG.NS` |
| 922 | `DAMCAPITAL` | Dam Capital Advisors Limited | `DAMCAPITAL.NS` |
| 923 | `DAMODARIND` | Damodar Industries Limited | `DAMODARIND.NS` |
| 924 | `DANGEE` | Dangee Dums Limited | `DANGEE.NS` |
| 925 | `DATAMATICS` | Datamatics Global Services Limited | `DATAMATICS.NS` |
| 926 | `DAVANGERE` | Davangere Sugar Company Limited | `DAVANGERE.NS` |
| 927 | `DBCORP` | D.B.Corp Limited | `DBCORP.NS` |
| 928 | `DBEIL` | Deepak Builders & Engineers India Limited | `DBEIL.NS` |
| 929 | `DBL` | Dilip Buildcon Limited | `DBL.NS` |
| 930 | `DBOL` | Dhampur Bio Organics Limited | `DBOL.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream CPEDU 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-901-930-Historical-Data/main/CPEDU/1m/2026/10/CPEDU_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
