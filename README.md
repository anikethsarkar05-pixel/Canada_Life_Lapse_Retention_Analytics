[README.md](https://github.com/user-attachments/files/31976232/README.md)
# Sun Life Insurance Analytics

Every insurance company has the same quiet problem.

People buy a policy. Then some of them stop paying. That moment is called a lapse, and when it happens, the company loses future premium and the customer loses protection.

I built this project to explore that problem the way a data analyst would.

It started as preparation for the Sun Life booth at the Regina career fair. I wanted more than a resume bullet. I wanted a full workflow: gather public data, clean it, ask retention questions in SQL, and turn the answers into a dashboard someone can actually read.


## What this project asks

Who is most likely to let a policy lapse?
Where does the premium risk sit?
Which signals show up early enough that a team could do something about them?

Those are practical questions. Not buzzwords.


## What is inside this repo

Book1.twb is the Tableau workbook. Open it in Tableau to see the dashboard.

The CSV folder holds the extracts I pulled with SQL. Each file is basically one business question already answered, like lapse rate by product, payment mode, tenure, or province.

The SQL notes show how those extracts were carved out of the database.

The data and source notes below explain what is real, what is modeled, and how to read the dashboard.


## Where the data came from

None of this is live Sun Life customer data. That matters, and I want that clear up front.

I used public sources:

OSFI quarterly life insurer filings, filtered to Sun Life.
A published SOA / CIA Canadian lapse study for industry benchmarks.
Province age profiles to keep the population mix realistic.
The Career Fair Canada Sun Life exhibitor page for company context.

From those benchmarks I built a modeled book of about 5,000 policies. Think of it as a practice book of business: realistic enough to analyze, honest enough to label as synthetic.


## How to walk through the dashboard

Start at the top. You should see total policies, lapse rate, retention rate, average premium, and annual premium at risk.

Then move into the breakdowns. Product type, province, payment mode, smoker status, and tenure usually tell the real story. Saskatchewan is worth a closer look because this project was built with Regina in mind.

After that, look at the drivers. Missed payments, newer policies, and monthly billing tend to matter. Those are the charts that feel closest to real retention work.

The OSFI pieces are company-level context from public filings. They are not customer-level outcomes. They sit beside the policy analysis to show the work is grounded in real published data.


## Why I built it this way

I wanted the project to look like the job.

Scrape and document sources.
Load data into PostgreSQL.
Use SQL to answer specific questions.
Export clean extracts.
Build a Tableau dashboard that a non-technical viewer can follow.

That pipeline matters more to me than one perfect chart.


## Honest limits

This is not production Sun Life data.
The policy book is modeled from public benchmarks.
OSFI values are regulatory aggregates.
The dashboard is for analysis practice and storytelling, not underwriting decisions.


## If you only read one paragraph

This is a retention analytics project. I used public Canadian insurance and demographic data, built a calibrated policy dataset, answered the key questions in SQL, and visualized where lapse risk and premium at risk concentrate. It is the kind of work a data analyst does when the business asks a simple question with expensive consequences: who is leaving, and what is that costing us?
