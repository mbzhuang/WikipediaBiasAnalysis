# Wikipedia Bias Analysis

### About the project
The goal of this project is to explore the concept of 'bias' through analyzing data on Wikipedia articles, which are on politicians from a variety of countries. By analyzing the existence and quality of these political articles, we are expecting to have a deeper understanding of Wikipedia's content.

### License of source data
#### API

Pagecounts API ([documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts), [endpoint](https://wikimedia.org/api/rest_v1/#!/Pagecounts_data_(legacy)/get_metrics_legacy_pagecounts_aggregate_project_access_site_granularity_start_end)) provides access to desktop and mobile traffic data from January 2008 through July 2016.

Pageviews API ([documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews), [endpoint](https://wikimedia.org/api/rest_v1/#!/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end)) provides access to desktop, mobile web, and mobile app traffic data from July 2015 through September 2017.

Both are licensed under the [CC-BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/) and [GFDL](https://www.gnu.org/copyleft/fdl.html) licenses.

#### Wikimedia's [Terms of Use](https://wikimediafoundation.org/wiki/Terms_of_Use) and [Privacy Policy](https://wikimediafoundation.org/wiki/Privacy_policy)

### Steps of the project
*Find the steps in BiasAnalysis.ipynb

1. Data acquisition: retrieve raw datasets from Pagecount API and Pageview API and save them as JSON files in the JSON_Data folder. Note that Pageview API excludes spiders/crawlers, while data from the Pagecounts API does not.

I combined a dataset of Wikipedia articles with a dataset of country populations, and use a machine learning service called Objective Revision Evaluation Service (ORES) to estimate the quality of each article. rtion of high quality articles about politicians.
    
2. Data processing: read the JSON files and process the raw data into a final csv file, bias_analysis_processed_data.csv
  
      The final csv file has 8 columns:

      | Column                 | Data Type | 
      | -----------------------|:---------:| 
      | country                | string    |
      | article_name           | string    | 
      | revision_id            | integer   |
      | article_quality        | string    |
      | population             | integer   |

3. Data analysis: read the csv file, analyze and visualize the article quality data.

I performed analysis on how the coverage of politicians on Wikipedia and the quality of articles about politicians varies between countries.
There will be a series of visualizations that show: the countries with the greatest and least coverage of politicians on Wikipedia compared to their population and the countries with the highest and lowest propo

### Organization of the project

The project has the following structure:

```
TrafficAnalysisEnglishWikipedia/
  |- JSON_Data/
     |- 0.json
     |- 1.json 
     |- 2.json
     |- 3.json
     ...
     |- 959.json
  |- LICENSE
  |- BiasAnalysis.ipynb
  |- HighestArticleQaulity.png
  |- HighestCountryArticlebyPopulation.png
  |- LowestCountryArticlebyPopulation.png
  |- README.md
  |- page_data.csv
  |- Population Mid-2015.csv
  |- bias_analysis_processed_data.csv
```
*This is an assignment for Data 512, University of Washington.

