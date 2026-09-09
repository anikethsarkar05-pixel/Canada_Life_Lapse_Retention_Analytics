[README.md](https://github.com/user-attachments/files/31976489/README.md)

# ☀️ Sun Life Insurance Analytics

### Policy lapse. Premium at risk. Real analyst workflow.

Every insurance company has the same quiet problem.

People buy a policy. Then some of them stop paying. That moment is called a **lapse** — and when it happens, the company loses future premium and the customer loses protection.

I built this project to explore that problem the way a data analyst would.

It started as preparation for the **Sun Life booth at the Regina career fair**. I wanted more than a resume bullet. I wanted a full workflow: gather public data, clean it, ask retention questions in SQL, and turn the answers into a dashboard someone can actually read.

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
| 📊 `Sunlife Analytics.twb` | Tableau workbook — open this to see the dashboard |
| 📂 CSV folder | SQL extracts for each business question |
| 📝 SQL notes | Formulas used to pull those extracts |
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

### 1️⃣ Start at the top
You’ll see:
- Total policies
- Lapse rate
- Retention rate
- Average premium
- Annual premium at risk

### 2️⃣ Then check the breakdowns
Product type • Province • Payment mode • Smoker status • Tenure

Saskatchewan is worth a closer look 🌾 — this project was built with Regina in mind.

### 3️⃣ Then look at the drivers
Missed payments, newer policies, and monthly billing tend to matter most.  
Those charts feel closest to real retention work.

### 4️⃣ OSFI context
Company-level public filings — not customer-level outcomes.  
They sit beside the policy analysis to show the work is grounded in real published data.

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

⭐ If you’re a recruiter or reviewer: open `Sunlife Analytics.twb` in Tableau, then skim the CSV folder to see the SQL-backed answers behind the charts.
