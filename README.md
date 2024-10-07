# data-512-homework_1
Goal: To publish a dataset of monthly article traffic the Wikipedia API receives for certain pages. More importantly, to create a workflow that is easily accessible and reproducible. The workflow addresses the data acquisition, processing, and analysis of the Wikipedia API data from July 1, 2015 to September 30, 2024. 

The license to the source data is the Wikimedia Foundation Terms of Use: 
https://foundation.wikimedia.org/wiki/Policy:Terms_of_Use

The API documentation is linked here: 
https://doc.wikimedia.org/generated-data-platform/aqs/analytics-api/reference/page-views.html

The license of the sample code (CC-BY) is linked below:
https://creativecommons.org/licenses/by/4.0/


My noteook creates three final output json files:
1. json file detailing monthly pageviews accessed through desktop
    - data-512-homework_1/rare-disease_monthly_desktop_201507-202409.json
2. json file detailiing monthly pageviews accessed through mobile
    - data-512-homework_1/rare-disease_monthly_mobile_201507-202409.json
3. json file detailiing monthly pageviews accessed through both mobile and desktop
    - data-512-homework_1/rare-disease_monthly_cumulative_201507-202409.json

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

My notebook also creates 3 jpeg files for each graph. 