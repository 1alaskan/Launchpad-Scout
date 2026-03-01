
## Startup Growth Radar

What?

Building a personal, automated pipeline that scores and ranks startups by hiring momentum and growth signals.
_____
Why?

So I'll know exactly who to reach out to, before everyone else does. Most companies will probabaly be seed and Series A.
_____
Status 

working on requirment one
_____
Requirments (chronological)

Please Note: Each of these requerests has steps included furtherdown 

1. Build an ETL pipeline
     — ingest and normalize data from WellFound, NewsAPI, LinkedIn job postings, and GitHub into a unified SQL database
2. Automate data collection 
    — schedule daily scraper runs via APScheduler so the pipeline stays fresh without manual effort
3. Engineer a momentum scoring model 
    — whip up a weighted scoring (0–100) using feature engineering across funding recency, job posting velocity, news mentions, and engineering activity, and whatever other data I end up collecting
4. Surface actionable targets 
    — build a Streamlit or Tabluea dashboard with product analytics views (eg filters by stage, domain, score) to generrate a weekly ranked outreach list
5. Track networking activity
     — embed log to record notes per company and if I talked to anyone there
6. Deliver weekly digests
     — automate a summary email of the top 10 highest momentum startups each week using Python automation
7. Deploy to the cloud?
    — host on Render or Railway so the API integrations and scrapers run continuously without a local machine
    

__________
Possible Tech Stack

For each project goal. Not sure what will actually be best for the task, just some ideas.


1. Python, BeautifulSoup, Playwright, pandas, SQL 
2. APScheduler
3. pandas, Python, NewsAPI, GitHub API, Crunchbase
4. Streamlit or Tableau
5. SQL
6. Python, APScheduler
7. Render / Railway, Postgres

________________________
Req 1. Build an ELT pipeline

Steps:

(C)    1. Company universe (name, location, founded date, stage, headcount) 
        -Crunchbase Basic free API or CSV export
        &
        Funding rounds (date, amount, round type, investors) 
        -Crunchbase + SEC EDGAR Form D filings
(C)    2. Job posting volume over time 
        - JobSpy (open source Python, scrapes Indeed/LinkedIn)
        &
        Job role types (engineering, sales, ops mix) 
        - parse job titles from the JobSpy pulls
(C)   3. News mention counts and velocity (dead end, turns our really small startups dont get alot of news coverage haha)
        - NewsAPI free tier (100 req/day)
(C)    4. Founder background (prior exits, accelerator alumni)   (didient work, cruncbase blocks scarping)
        - Crunchbase people endpoints
    5. GitHub activity (commits, stars, contributor growth) 
        - GitHub API (free)
    6. Web traffic trends 
        - SimilarWeb free tier (manual, limited to top companies)
    7. LinkedIn headcount over time
        - LinkedIn via RapidAPI (costs money)
