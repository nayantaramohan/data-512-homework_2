[![GitHub license](https://img.shields.io/github/license/nayantaramohan/data-512-homework_2)](https://github.com/nayantaramohan/data-512-homework_2/blob/main/LICENSE)

# DATA 512: Human Centered Data Science (Au 2022)
## Homework 2: Considering Bias in Data
## Goal

The goal of this assignment is to explore the concept of bias in data using Wikipedia articles. This assignment will consider articles on political figures from different countries. For this assignment, you will combine a dataset of Wikipedia articles with a dataset of country populations, and use a machine learning service called ORES to estimate the quality of each article.    

The expectation is to perform an analysis of how the coverage of politicians on Wikipedia and the quality of articles about politicians varies among countries. The analysis will consist of a series of tables that show:  
- The countries with the greatest and least coverage of politicians on Wikipedia compared to their population.
- The countries with the highest and lowest proportion of high quality articles about politicians.
- A ranking of geographic regions by articles-per-person and proportion of high quality articles.  

There is also a short reflection on the project that focuses on how both the findings from this analysis and the process to reach those findings helps one understand the causes and consequences of biased data in large, complex data science projects.

## Data Sources
The articles were webcrawled from the below websites and the output of those files are stored in the homework folder as stated below: -
- [Category:Politicians by nationality](https://en.wikipedia.org/wiki/Category:Politicians_by_nationality): [politicians_by_country.SEPT.2022.csv](https://docs.google.com/spreadsheets/u/0/d/1Y4vSTYENgNE5KltqKZqnRQQBQZN5c8uKbSM4QTt8QGg/edit)
- [World population data sheet ](https://www.prb.org/international/indicator/population/table/): [population_by_country_2022.csv](https://docs.google.com/spreadsheets/u/0/d/1POuZDfA1sRooBq9e1RNukxyzHZZ-nQ2r6H5NcXhsMPU/edit).   
**NOTE**: The .csv files were used as is without tweaking or making any edits.   

For getting the articles quality predictions, ORES (Objective Revision Evaluation Service) has been used.
These were learned based on articles in Wikipedia that were peer-reviewed using the [Wikipedia content assessment](https://en.wikipedia.org/wiki/Wikipedia:Content_assessment) procedures.

For using the ORES for making a page quality prediction, [API:Info](https://www.mediawiki.org/wiki/API:Info) is used.  

## API documentation sample document
The below sample codes were referenced for the following tasks and have been licensed under [License CC0](https://creativecommons.org/share-your-work/public-domain/cc0/). 
- [Making a page info request](https://drive.google.com/file/d/1Z8DqXpHmNUJ3RD7e-OOwx2WYJPIYjUPp/view?usp=sharing)
- [Making an ORES request](https://drive.google.com/file/d/1rZdBrtCe9XO4IkDWqm0A2RA-HfZCsqHh/view?usp=sharing)

## Data files

#### Repository tree [WIP]
```
.
├── LICENSE
├── README.md
├── data-512-hw2-nmohan.ipynb
├── error_log.txt
├── politicians_by_country_SEPT.2022.csv
├── population_by_country_2022.csv
├── request_ores_score_per_article_output.csv
├── request_pageinfo_per_article_output.csv
├── wp_countries-no_match.txt
├── wp_politicians_by_country.csv
```
#### Description
- **LICENSE** : a file that contains an MIT LICENSE for nayantaramohan/data-512-homework_2 repo.
- **README.md** : a file that contains information to reproduce the analysis, including data descriptions, attributions and provenance information, and descriptions of all relevant resources and documentation (inside and outside the repo) and hyperlinks to those resources. This also contains the goal and learning reflections of the project.
- **data-512-hw2-nmohan.ipynb** : The Jupyter notebook that consists of all the code with documentation of the preprocessing and data aggregation to calculate the given stated goals. 

#### Input files
- **politicians_by_country_SEPT.2022.csv** : The Wikipedia Category Politicians by nationality was crawled to generate a list of Wikipedia article pages about politicians from a wide range of countries.
- **population_by_country_2022.csv** : This dataset is drawn from the world population data sheet published by the Population Reference Bureau.  
**NOTE**: The .csv files were used as is without tweaking or making any edits.  

#### Output files
- **wp_countries-no_match.txt** : all countries for which there are no matches and output a list of those countries, with each country on a separate line
- **wp_politicians_by_country.csv** : Consolidating the remaining data as instructed into a single CSV file

#### Intermediate files
- **error_log.txt** : This log maintains the list of article titles for whom the page info was not retrieved.
- **request_ores_score_per_article_output.csv** : Storing the output of the API call for the ores score in this .csv
- **request_pageinfo_per_article_output.csv** : Storing the output of the API call for getting the page info for the articles

## Special Considerations
- The input .csv files have not been manipulated thus some articles were not captured as their respective names had quotes
- There are 6 countries whose population is zero, these have been excluded in the calculation of article per capita as this would yield an infinite result otherwise.
- Politicians with duplicate values have been eliminated.
- Regions with cumulative population values are dropped.
- Countries are mapped to the regions that are closest/lowest in the hierarchy of regions.
- Error log for page info request failing is handled using a .txt file whereas for the ORES score, it has been printed in the notebook. 

## Research Implications
 
**Reflection**
It is essential to understand a data science project quantitively and qualitatively. This project gives a good walkthrough of qualitative analysis by considering bias in the data. The biases are caused due to the inherent raw data having human bias based on various reasons like demographic, religion, culture, gender etc. From this exericse, it is revealed that the article per capita maynot be the best indicator for this exercise as these values are not proportional to the population of a country. There is also a bias in terms of article per capita being higher in native english speaking countries.   

**What biases did you expect to find in the data (before you started working with it), and why?**
I expected the highest quality of articles to be from the first world countries. But after the exericse, it was surprising to see that many first world countries like the Unites States, Australia wwere not present in the dataset. Similarly Japan is seen as the bottom 10 countries for high quality articles per capita.     
A major bias I feel is we are only accounting for articles in English which is very biased as populous regions like China, India would have majority of their high quality articles in their native languages.    

**What might your results suggest about (English) Wikipedia as a data source?**  
As mentioned above, I believe using only English articles as a data source creates a major bias. As per the internet ([Reference link](https://preply.com/en/blog/english-language-statistics/)) only 17% of the world's population speaks English. This number in itself shows that it is extremely biased to use only English articles for this exercise.   
Another anamoly is to rely on ORES for the quality of the article as this is more biased towards the structure of the article more than the quality of the content in it.   

**Can you think of a realistic data science research situation where using these data (to train a model, perform a hypothesis-driven research, or make business decisions) might create biased or misleading results, due to the inherent gaps and limitations of the data?**  
Reference: [Mixed Messages? The Limits of Automated Social Media Content Analysis.](https://cdt.org/wp-content/uploads/2017/12/FAT-conference-draft-2018.pdf) and [AI’s Islamophobia problem](https://www.vox.com/future-perfect/22672414/ai-artificial-intelligence-gpt-3-bias-muslim)
The above readings have a similar context along the lines of limitations of text classifiers in online content. The paper presented at the 2018 Conference on Fairness, Accountability, and Transparency dives deep into understanding the limitations of NLP and how it is essential to understand these drawbacks before policymakers can make decisions. The paper talks about the existing NLP research of text classifiers to address the gaps in policymakers' knowledge. The article supports the claims made by the paper by drawing a disturbing example of how AI has created an islamophobia problem.   

**How might a researcher supplement or transform this dataset to potentially correct for the limitations/biases you observed?**
There were several missing countries, it would be useful to be able to fetch data for these missing countries. Similarly the population of around 6 countries were shown as 0 cause of which they had to be excluded from the article per capita analysis, this could be due to the rounding error which needs to be checked correctly. There were several politicians whose articles were missing from the Wikipedia as well and some of them were represented in two countries. A researcher will have to go through the subject matter in depth to udnerstand these nuances. For Eg. one politician is shown in India and Pakistan and through data analysis his row was deleted cause of duplicate names but in reality this politician belonged to India before the country split in 1947 thus being taagged to both the countries being accurate. There could be many more such instances which needs to be corrected. 

## Best practices for documentation
- PEP 8 – Style Guide for Python Code. ([Reference link](https://peps.python.org/pep-0008/))
- Use of relative path addresses to help in reproducibility.
- Use of intuitive variable and function names to ease in understanding.
- Appropriate comments and documentation provided for the data aquisition, data processing and data analysis steps.
- Description of all data files present in the repository mentioned.
- Exception Handling taken care of in the code to avoid breaking the API loops.

## Author
[Nayantara Mohan](https://github.com/nayantaramohan) 
