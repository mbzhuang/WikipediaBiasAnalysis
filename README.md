# Wikipedia Bias Analysis

### About the project
The goal of this project is to explore the concept of 'bias' through analyzing data on Wikipedia articles, which are on politicians from a variety of countries. By analyzing the existence and quality of these political articles, we are expecting to have a deeper understanding of Wikipedia's content.

### License of source data
#### API

ORES, Objective Revision Evaluation Service ([documentation](https://www.mediawiki.org/wiki/ORES), [endpoint](https://ores.wikimedia.org/v3/scores/{project}/?models={model}&revids={revids})) provides machine learning as a service that generates content quality data for Wikipedia projects.

#### Wikimedia's [Terms of Use](https://wikimediafoundation.org/wiki/Terms_of_Use) and [Privacy Policy](https://wikimediafoundation.org/wiki/Privacy_policy)

#### Population Reference Bureau's [Privacy Policy](http://www.prb.org/DataFinder/Topic/~/link.aspx?_id=11A2A1677D184053936CE705FAEDEC1D&_z=z)

### Steps of the project
*Find the steps in BiasAnalysis.ipynb

1. Data acquisition: combined a [dataset of Wikipedia articles with a dataset of country populations](https://figshare.com/articles/Untitled_Item/5513449) (page_data.csv, csv file read into dataframe) and used a machine learning service called Objective Revision Evaluation Service (ORES) to estimate the quality of each article. The data of article quality are saved in JSON_Data folder, loaded from the folder, and then saved into a dataframe. The population data is on the [Population Research Bureau website](http://www.prb.org/DataFinder/Topic/Rankings.aspx?ind=14) (Population Mid-2015.csv, csv file read into a dataframe).
    
2. Data processing: merged the three dataframes and process the final data into a csv file, bias_analysis_processed_data.csv
  
      The final csv file has 8 columns:

      | Column                 | Data Type | 
      | -----------------------|:---------:| 
      | country                | string    |
      | article_name           | string    | 
      | revision_id            | integer   |
      | article_quality        | string    |
      | population             | integer   |

3. Data analysis: read the csv file, analyzed and visualized the article quality data. There are a series of visualizations in png format that show: the countries with the greatest and least coverage of politicians on Wikipedia compared to their population and the countries with the highest and lowest proportion of high quality articles on politicians.  
    * HighestArticleQaulity.png
    * HighestCountryArticlebyPopulation.png
    * LowestCountryArticlebyPopulation.png
   
### Results and Discussion:
   
1. The countries with the greatest and least coverage of politicians on Wikipedia compared to their population

    Most countries appear on top of the list in terms of number of articles divided by population are the countries of least population. Similarly, most countries on the bottom of the list in terms of number of articles divided by population are the countries of highest population, for instance, China, India, Indonesia, and Bangladesh. Given the above findings, I found this analysis is not as informative as expected. 
    
2. The countries with the highest and lowest proportion of high quality articles about politicians.

    The top 10 countries with highest proportion of high quality articles are: North Korea, Romania, Saudi Arabia, Central African Republic, Qatar, Guinea-Bissau, Vietnam, Bhutan, Ireland, and United States. The most interesting finding is that North Korea being on the very top of this list. While for the countries with poorer articles quality, there are more than 10 countries having 0% of FA and GA level articles.

### Organization of the project

The project has the following structure:

```
TrafficAnalysisEnglishWikipedia/
  |- JSON_Data/
     |- ORES_quality_data_0.json
     |- ORES_quality_data_1.json 
     |- ORES_quality_data_2.json
     |- ORES_quality_data_3.json
     ...
     |- ORES_quality_data_943.json
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

