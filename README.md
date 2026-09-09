[README.md](https://github.com/user-attachments/files/32028810/README.md)
# 🇨🇦 Canadian Life Insurance Lapse & Retention Analytics

### 📉 Policy lapse. 💵 Premium at risk. 🧠 Real analyst workflow.

🚨 Every insurance company has the same quiet problem.

🧾 People buy a policy. Then some of them stop paying. That moment is called a **lapse** — and when it happens, the company loses future premium and the customer loses protection.

🛠️ I built this project to explore that problem the way a data analyst would.

🚀 I wanted more than a resume bullet. I wanted a full workflow: gather public Canadian insurance data, clean it, ask retention questions in SQL, and turn the answers into a dashboard someone can actually read.

---

## 📊 Lapse and Retention Dashboard

🖼️ This is the main dashboard in `Canada_Life_Lapse_Retention_Analytics.twb` / `.twbx`.

![Lapse and Retention Dashboard](Lapse%20And%20Retention%20Dashboard.png)

### 👀 What you are looking at

📌 At the top are the book-level KPIs:

- 📦 **Total Policies:** 5,000
- 🔻 **Total Lapsed:** 577
- ⚠️ **Lapse Rate:** 11.54%
- ✅ **Retention Rate:** 88.46%
- 💵 **Average Premium:** 136.62
- 🔥 **Annual Premium at Risk:** about $949,471

📏 The dashed **Book 11.54%** line on the charts is the overall lapse rate.  
📈 Bars above that line = higher-risk segments.  
📉 Bars below it = doing better than the book average.

🧩 Then the charts break the story down:

1. ⏰ **Lapse Rate by Missed Payments** — more missed payments, higher lapse risk  
2. 🛡️ **Lapse by Product Type** — Term / Whole / Critical Illness / Universal Life  
3. 📅 **Lapse by Tenure Band** — new policies (1–3 years) lapse more than mature ones  
4. 🚬 **Lapse by Smoking Status** — smokers sit above the book average  
5. 💳 **Lapse Rate by Payment Mode** — monthly payers lapse more than annual  
6. 🍁 **Lapse Rate by Province** — compare BC, Manitoba, Quebec, Saskatchewan, Alberta, Ontario  
7. 💰 **Premium at Risk by Product** — where the dollars sit if policies lapse  

✨ If you only glance at one image in this repo, make it this one.

---

## 🎯 What this project asks

- 👤 Who is most likely to let a policy lapse?
- 💰 Where does the premium risk sit?
- 🚨 Which signals show up early enough that a team could do something about them?

💬 Those are practical questions. Not buzzwords.

---

## 📁 What’s inside this repo

| File / folder | What it is |
|---|---|
| 📊 `Canada_Life_Lapse_Retention_Analytics.twb` / `.twbx` | Tableau workbook with the Lapse and Retention Dashboard |
| 🖼️ `Lapse And Retention Dashboard.png` | Screenshot of the main dashboard |
| 📂 `sql_extracts` | SQL extracts for each business question |
| 🧾 `policies.csv` | Row-level policy book used by the workbook |
| 📝 `sql_notes.txt` | Formulas used to pull the extracts |
| 📘 `README.md` | You’re reading it |

---

## 📡 Where the data came from

> ⚠️ This is not live insurer customer data. That matters, and I want that clear up front.

📚 I used public Canadian sources:

- 🏛️ **OSFI quarterly filings** — federally regulated life insurer returns from Open Canada
- 📉 **SOA / CIA lapse study (2020)** — Canadian industry lapse benchmarks
- 🗺️ **Province age profiles** — census-style demographics to keep the population mix realistic
- 📖 **Public insurer / industry context pages** — background on the Canadian life insurance market

🧪 From those benchmarks I built a modeled book of about **5,000 policies**.  
📦 Think of it as a practice book of business: realistic enough to analyze, honest enough to label as synthetic.

🏷️ Product types used here are common Canadian life-insurance categories:  
🛡️ Term Life • 🏡 Whole Life • 🌐 Universal Life • ❤️ Critical Illness

---

## 🧭 How to walk through the dashboard

### 1️⃣ 🏁 Start at the KPI banners
📌 Begin with the scoreboard at the top so you know the size of the problem before diving into charts.

📦 Total policies • 🔻 Lapsed count • ⚠️ Lapse rate • ✅ Retention rate • 💵 Average premium • 🔥 Annual premium at risk

### 2️⃣ 🔍 Then check the breakdowns
🧭 Split the book into segments and compare each one against the book average.

🛡️ Product type • 🍁 Province • 💳 Payment mode • 🚬 Smoking status • 📅 Tenure

🌾 Canadian provinces are included so the analysis feels local and practical, not abstract.

### 3️⃣ 🚨 Then look at the drivers
👀 These are the early-warning signals a retention team would actually watch.

⏰ Missed payments and 🆕 newer policies are the clearest red flags.

### 4️⃣ 💸 Then check premium at risk by product
💵 Rate alone is not enough. This step shows where lapse hurts the most in dollars.

📊 Use it to prioritize which product areas deserve attention first.

---

## 🛠️ Why I built it this way

💼 I wanted the project to look like the job:

1. 🕸️ Scrape and document sources  
2. 🗄️ Load data into PostgreSQL  
3. 🧮 Use SQL to answer specific questions  
4. 📤 Export clean extracts  
5. 📊 Build a Tableau dashboard a non-technical viewer can follow  

⭐ That pipeline matters more to me than one perfect chart.

---

## 🧾 Honest limits

- ❌ Not production insurer customer data  
- 🧪 Policy book is modeled from public benchmarks  
- 📄 OSFI values are regulatory aggregates  
- 🏷️ Product types are common industry categories, not one company’s catalog scrape  
- 🎯 Built for analysis practice and storytelling, not underwriting decisions  

---

## 🎤 If you only read one paragraph

📌 This is a **Canadian life insurance retention analytics** project.  
📡 I used public regulatory and industry data, built a calibrated policy dataset, answered the key questions in SQL, and visualized where lapse risk and premium at risk concentrate.

💡 It is the kind of work a data analyst does when the business asks a simple question with expensive consequences:

### ❓ Who is leaving — and what is that costing us?

---

⭐ If you’re a recruiter or reviewer: look at the dashboard screenshot above first, then open `Canada_Life_Lapse_Retention_Analytics.twbx` in Tableau (or the Tableau Public link if available), then skim the `sql_extracts` folder for the SQL-backed files behind the charts.
