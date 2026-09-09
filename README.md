[README.md](https://github.com/user-attachments/files/32028535/README.md)
# ☀️ Sun Life Insurance Analytics

### Policy lapse. Premium at risk. Real analyst workflow.

Every insurance company has the same quiet problem.

People buy a policy. Then some of them stop paying. That moment is called a **lapse** — and when it happens, the company loses future premium and the customer loses protection.

I built this project to explore that problem the way a data analyst would.

It started as preparation for the **Sun Life booth at the Regina career fair**. I wanted more than a resume bullet. I wanted a full workflow: gather public data, clean it, ask retention questions in SQL, and turn the answers into a dashboard someone can actually read.

---

## 📊 Lapse and Retention Dashboard

This is the main dashboard in `Sunlife Analytics.twb` / `.twbx`.

![Lapse and Retention Dashboard](Lapse%20And%20Retention%20Dashboard.png)

### 👀 What you are looking at

At the top are the book-level KPIs:

- 📦 **Total Policies:** 5,000
- 🔻 **Total Lapsed:** 577
- ⚠️ **Lapse Rate:** 11.54%
- ✅ **Retention Rate:** 88.46%
- 💵 **Average Premium:** 136.62
- 🔥 **Annual Premium at Risk:** about $949,471

📏 The dashed **Book 11.54%** line on the charts is the overall lapse rate.  
📈 Bars above that line = higher-risk segments.  
📉 Bars below it = doing better than the book average.

Then the charts break the story down:

1. ⏰ **Lapse Rate by Missed Payments** — more missed payments, higher lapse risk  
2. 🛡️ **Lapse by Product Type** — Term / Whole / Critical Illness / Universal Life  
3. 📅 **Lapse by Tenure Band** — new policies (1–3 years) lapse more than mature ones  
4. 🚬 **Lapse by Smoking Status** — smokers sit above the book average  
5. 💳 **Lapse Rate by Payment Mode** — monthly payers lapse more than annual  
6. 🇨🇦 **Lapse Rate by Province** — compare BC, Manitoba, Quebec, Saskatchewan, Alberta, Ontario  
7. 💰 **Premium at Risk by Product** — where the dollars sit if policies lapse  

✨ If you only glance at one image in this repo, make it this one.

---

## 🎯 What this project asks

- 👤 Who is most likely to let a policy lapse?
- 💰 Where does the premium risk sit?
- 🚨 Which signals show up early enough that a team could do something about them?

Those are practical questions. Not buzzwords.

---

## 📁 What’s inside this repo

| File / folder | What it is |
|---|---|
| 📊 `Sunlife Analytics.twb` / `.twbx` | Tableau workbook with the Lapse and Retention Dashboard |
| 🖼️ `Lapse And Retention Dashboard.png` | Screenshot of the main dashboard |
| 📂 CSV folder | SQL extracts for each business question |
| 🧾 `policies.csv` | Row-level policy book used by the workbook |
| 📝 `Sql notes.txt` | Formulas used to pull the extracts |
| 📘 `README.md` | You’re reading it |

---

## 📡 Where the data came from

> ⚠️ None of this is live Sun Life customer data. That matters, and I want that clear up front.

I used public sources:

- 🏛️ **OSFI quarterly filings** — life insurer returns, filtered to Sun Life
- 📉 **SOA / CIA lapse study (2020)** — Canadian industry benchmarks
- 🗺️ **Province age profiles** — keeps the population mix realistic
- 🏢 **Career Fair Canada page** — Sun Life exhibitor context

From those benchmarks I built a modeled book of about **5,000 policies**.  
Think of it as a practice book of business: realistic enough to analyze, honest enough to label as synthetic.

---

## 🧭 How to walk through the dashboard

### 1️⃣ 🏁 Start at the KPI banners
📦 Total policies • 🔻 Lapsed count • ⚠️ Lapse rate • ✅ Retention rate • 💵 Average premium • 🔥 Annual premium at risk

### 2️⃣ 🔍 Then check the breakdowns
🛡️ Product type • 🇨🇦 Province • 💳 Payment mode • 🚬 Smoking status • 📅 Tenure

Saskatchewan is worth a closer look 🌾 — this project was built with Regina in mind.

### 3️⃣ 🚨 Then look at the drivers
⏰ Missed payments and 🆕 newer policies are the clearest early-warning signals.

### 4️⃣ 💸 Then check premium at risk by product
This shows where lapse hurts financially, not just by rate.

---

## 🛠️ Why I built it this way

I wanted the project to look like the job:

1. 🕸️ Scrape and document sources  
2. 🗄️ Load data into PostgreSQL  
3. 🧮 Use SQL to answer specific questions  
4. 📤 Export clean extracts  
5. 📊 Build a Tableau dashboard a non-technical viewer can follow  

That pipeline matters more to me than one perfect chart.

---

## 🧾 Honest limits

- ❌ Not production Sun Life data  
- 🧪 Policy book is modeled from public benchmarks  
- 📄 OSFI values are regulatory aggregates  
- 🎯 Built for analysis practice and storytelling, not underwriting decisions  

---

## 🎤 If you only read one paragraph

This is a **retention analytics** project. I used public Canadian insurance and demographic data, built a calibrated policy dataset, answered the key questions in SQL, and visualized where lapse risk and premium at risk concentrate.

It is the kind of work a data analyst does when the business asks a simple question with expensive consequences:

### Who is leaving — and what is that costing us?

---

⭐ If you’re a recruiter or reviewer: look at the dashboard screenshot above first, then open `Sunlife Analytics.twbx` in Tableau (or the Tableau Public link if available), then skim the CSV folder for the SQL-backed extracts behind the charts.
