# data-512-homework_1
## Goal
 To publish a dataset of monthly article traffic the Wikipedia API receives for certain pages. More importantly, to create a workflow that is easily accessible and reproducible. The workflow addresses the data acquisition, processing, and analysis of the Wikipedia API data from July 1, 2015 to September 30, 2024. 

## Licensing 
The license to the source data is the Wikimedia Foundation Terms of Use: 
https://foundation.wikimedia.org/wiki/Policy:Terms_of_Use

The API documentation is linked here: 
https://doc.wikimedia.org/generated-data-platform/aqs/analytics-api/reference/page-views.html

This page describes how the rest API can be accessed: https://www.mediawiki.org/wiki/Wikimedia_REST_API 

The list of rare diseases (article titles) was gathered from a database from the National Organization for Rare Diseases (NORD):
https://rarediseases.org 

I also used sample code in my notebookfrom Dr. David McDonald which is licensed through CC-BY, linked here:
https://creativecommons.org/licenses/by/4.0/

## Output Files 
My noteook creates three final output json files:
1. json file detailing monthly pageviews accessed through desktop
    - `data-512-homework_1/rare-disease_monthly_desktop_201507-202409.json`
2. json file detailiing monthly pageviews accessed through mobile
    - `data-512-homework_1/rare-disease_monthly_mobile_201507-202409.json`
3. json file detailiing monthly pageviews accessed through both mobile and desktop
    - `data-512-homework_1/rare-disease_monthly_cumulative_201507-202409.json`
### Data Schema
The data schema for the json files is as follows:

```
{
    "Klinefelter syndrome": [
        {
            "project": "en.wikipedia",
            "article": "Klinefelter_syndrome",
            "granularity": "monthly",
            "timestamp": "2015070100",
            "agent": "user",
            "views": 76237
        }, 
        ...
    ]
}
```
Each article title is a key and the value is a list of dictionaries where each dictionary is the monthly data. The access key value pair is omitted from the dictionary as it gets confusing in the cumulative json file. 

### Image Output
My notebook also creates 3 jpeg files for each graph. All of the graphs are time series of page views over monthly data from July 1, 2015 to September 30, 2024:
1. `min_max.png`: Time series for the articles that have the highest average page views and the lowest average page views for desktop access and mobile access.
2. `peak.png`: Time series for the top 10 article pages by greatest (peak) number of page views for mobile and desktop access. 
3. `fewest_months.png`: Time series for the 10 articles that have the fewest months of data available. 10 articles per acces type, so a total of 20 articles (10 for mobile access and 10 for desktop access).

## Issues and Special Consideration
There were some article titles with a slash in them, which threw an error when making the API call. I printed the titles in the notebook, so that users know which ones to look out for. Also, my analysis focuses only on page requests made from mobile or desktop, which may not be a holistic respresentation as some users might have accessed Wikipedia through playstation or satellite.