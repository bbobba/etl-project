# <center>ETL Project - Job Posting Data</center>

Team members:
Becky Bobba, Amro Elhag, Kelly Blumhagen

## Data sources
This project uses two data sets scraped from indeed.com. Each data set includes data for job postings on Indeed.com with the job title "Data Analyst" and located in Austin, TX. Data scraped for each set includes:

1. Job Posting Search Results
* Job Title
* Company
* Location (zip code)
* Job URL

2. Job Description
* Job URL
* Job Description Text

## Decisions you made to do cleanup (transform) and join (transform)
We cleanded the data during extraction. Processes included:
* Reformat job description links to include the entire URL
* Cleaned the job titles (originally extracted "/n" with the job title text)
* We made sure there was no missing data before extraction

## How you decided on database tech to store, and schema to store.
* Given our dataset, we wanted to use an object oriented database, and therefore chose to use MySQL to store it.
* We created a new schema, titled "jobs_db," to store it in MySQL.  

## Potential analysis to do on the newly formed dataset
* Which companies have the most openings?
* Where are the the most job openings located in Austin?
* Which skills appear the most often in job descriptions (i.e. SQL, Python, etc)? 

## Challenges you overcame.
* We wanted to scrape text for the entire job description. The first data set (Job Posting Search Results) included some of the text for each JD, but only the first few lines. We used the job's links to then scrape the full text from each individual URL. 
* It takes ~20 min to scrape the data. We tried to minimize the number of times we had to scrape the data so as to save time. We believe it might be more efficient to include the extraction in a different file so that it does not have to run each time we run the transform and loading code.
