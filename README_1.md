
What?

Building a personal, automated pipeline that scores and ranks startups by hiring momentum and growth signals.
_____
Why?

So I'll know exactly who to reach out to, before everyone else does. Most will probabaly be seed and Series A.
_____
Status 

Not started
_____
Goals (chronological)

Please Note: Each of these goals has steps included furtherdown 

1. Build an ETL pipeline
     — ingest and normalize data from WellFound, NewsAPI, LinkedIn job postings, and GitHub into a unified SQL database
2. Automate data collection 
    — schedule daily scraper runs via APScheduler so the pipeline stays fresh without manual effort
3. Engineer a momentum scoring model 
    — design a weighted scoring engine (0–100) using feature engineering across funding recency, job posting velocity, news mentions, and engineering activity
4. Surface actionable targets 
    — build a Streamlit dashboard with product analytics views (filters by stage, domain, score) to generate a weekly ranked outreach list
5. Track networking activity
     — embed a lightweight CRM log to record contacts, outreach status, and notes per company
6. Deliver weekly digests
     — automate a summary email of the top 10 highest-momentum startups each week using Python automation
7. Deploy to the cloud 
    — host on Render or Railway so the API integrations and scrapers run continuously without a local machine

__________
Tech Stack

For each project goal. Not sure what will actually be best for the task, just some ideas.


1. Python, BeautifulSoup, Playwright, pandas, SQLite
2. APScheduler
3. pandas, Python, NewsAPI, GitHub API, Crunchbase
4. Streamlit
5. SQLite → Postgres
6. Python, APScheduler
7. Render / Railway, Postgres

________________________
1. Build an ETL pipeline

    1. Company universe (name, location, founded date, stage, headcount) 
        -Crunchbase Basic free API or CSV export
        &
        Funding rounds (date, amount, round type, investors) 
        -Crunchbase + SEC EDGAR Form D filings
    3. Job posting volume over time 
        - JobSpy (open source Python, scrapes Indeed/LinkedIn)
    4. Job role types (engineering, sales, ops mix) 
        - parse job titles from the JobSpy pulls
    5. News mention counts and velocity 
        - NewsAPI free tier (100 req/day)
    6. Founder background (prior exits, accelerator alumni) 
        - Crunchbase people endpoints
    7. GitHub activity (commits, stars, contributor growth) 
        - GitHub API (free)
    8. Web traffic trends 
        - SimilarWeb free tier (manual, limited to top companies)
    9. LinkedIn headcount over time
        - LinkedIn via RapidAPI (~$10–20/mo)
