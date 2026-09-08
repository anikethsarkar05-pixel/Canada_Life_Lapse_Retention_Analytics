# Sun Life Insurance Analytics

This is a policy lapse and customer retention project I built for the Sun Life booth at the Regina career fair.

The idea is simple. I pulled public Canadian insurance and demographic data, built a policy-level dataset from those benchmarks, and put the results into a dashboard so someone can see who is more likely to lapse and how much premium that puts at risk.

Is this real-time data?

No. The scraper does not pull live Sun Life customer data.

What I used instead:

OSFI / Open Canada (LF1)
Historical quarterly regulatory filings for life insurers. I filtered for Sun Life rows. These filings are published after the fact, so they are not live. Local files: data/raw/osfi_sun_life_lf1.csv and the cleaned version data/raw/life_insurance_data.csv. In PostgreSQL this usually lands in the life_insurance_data table.

SOA / CIA Canadian term lapse study (2020)
Industry lapse benchmarks from a published research report, not a live feed. Local file: data/raw/lapse_benchmarks.csv. I used these rates to calibrate the synthetic policy book. The baseline steady-state lapse proxy came out around 5.7%.

Province age profile
Age distribution weights by province, based on 2021 census-style demographics (or a documented fallback if the census download failed). Local file: data/raw/province_age_profile.csv. The weight column is just the share of that age group in the province. So 0.08 means about 8%.

Career Fair Canada page
Sun Life's exhibitor blurb from the Regina fair page. Local file: data/raw/sun_life_employer_profile.txt. Useful for company context, not for analytics math.

policies.csv
About 5,000 synthetic policies built from the sources above. This is the main analysis table. Columns include policy_id, customer_id, age, province, product_type, payment_mode, smoker, premium_monthly, coverage_amount, years_active, missed_payments_12m, and lapsed. In PostgreSQL this is usually the policies table.

If someone asks at the fair, a clean answer is: I used publicly available regulatory and industry data, not live production data, then modeled policy-level lapse risk from those benchmarks.


What the dashboard is showing

The dashboard is telling one story: retention risk.

At the top you should see the snapshot numbers. Total policies, lapse rate, retention rate, average monthly premium, and annual premium at risk. Premium at risk is the monthly premium on lapsed policies multiplied by 12. Start here. If lapse rate or premium at risk looks high, dig into the charts below.

Next are the segment breakdowns. These show lapse rates by product type, province, payment mode, smoker status, and how long the policy has been active. Higher bars usually mean more risk. Saskatchewan is worth calling out since the fair is in Regina.

Then come the risk drivers. Missed payments in the last 12 months, new policies under 3 years, and monthly versus annual payment mode tend to show up as the clearest patterns. These are the kinds of signals a retention team would actually care about.

There is also a demographics section from the province age profile. Remember that weight is population share, not lapse rate. It just explains why certain ages show up more often in the book.

The OSFI section is company filing context. You can filter by fiscal year or quarter and search labels related to premiums, policies, or contracts. This is not individual customer lapse data. It sits beside the policy book to show I grounded the project in real public filings.

If the risk scoring layer is turned on, policies get Low, Medium, or High lapse-risk bands from a logistic model using age, premium, tenure, missed payments, smoker status, province, product, and payment mode. High risk is where you would prioritize follow-up.


How the pieces connect

Public websites go into src/scrape_data.py. That script writes the raw files under data/raw and builds data/policies.csv. From there the data goes into PostgreSQL through pgAdmin, and then into the dashboard through Power BI or SQL queries. The analysis helpers live in src/analysis.py.

To refresh the scraped data:

cd C:\Users\anike\Projects\sunlife-insurance-analytics
python src/scrape_data.py

After that, re-import the CSVs or refresh the dashboard. The last scrape details are in data/scrape_metadata.json.


Things to be honest about

This is not live Sun Life customer data.
OSFI numbers are regulatory aggregates, not policy-level outcomes.
If the census file was unreachable, the age profile may use documented fallback shares.
The dashboard conclusions are modeled. They are meant to show analyst workflow, not production underwriting decisions.


Conclusion

This dashboard looks at life insurance policy retention. I scraped public OSFI filings and industry lapse benchmarks, built a calibrated policy dataset, and visualized where lapse risk and premium at risk concentrate by product, province, payment behaviour, and tenure. Those are the same questions a data analyst would ask on a real book of business.
