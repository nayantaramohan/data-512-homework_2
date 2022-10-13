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
- [World population data sheet ](https://www.prb.org/international/indicator/population/table/): [population_by_country_2022.csv](https://docs.google.com/spreadsheets/u/0/d/1POuZDfA1sRooBq9e1RNukxyzHZZ-nQ2r6H5NcXhsMPU/edit) 
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
├── 
├── 
├── 
├── 
├── 
├── 
```
#### Description [WIP]
- **LICENSE** : a file that contains an MIT LICENSE for nayantaramohan/data-512-homework_2 repo.
- **README.md** : a file that contains information to reproduce the analysis, including data descriptions, attributions and provenance information, and descriptions of all relevant resources and documentation (inside and outside the repo) and hyperlinks to those resources. This also contains the goal and learning reflections of the project.
- [WIP] mention input and output files, along with those which are intermediate

## Special Considerations


## Snapshot of Analysis outputs
[Add the snapshots of the 6 tables]

## Research Implications
[WIP]
Write several paragraphs that you will include in your README.  Your README should include a section header called “Research Implications” after which you will include your write-up paragraphs. One of your paragraphs should reflect on what you have learned, what you found, what (if anything) surprised you about your findings, and/or what theories you have about why any biases might exist (if you find they exist). In addition to any reflections you want to share about the process of the assignment, please respond (briefly) to at least three of the questions below:
What biases did you expect to find in the data (before you started working with it), and why?
What (potential) sources of bias did you discover in the course of your data processing and analysis?
What might your results suggest about (English) Wikipedia as a data source?
What might your results suggest about the internet and global society in general?
Can you think of a realistic data science research situation where using these data (to train a model, perform a hypothesis-driven research, or make business decisions) might create biased or misleading results, due to the inherent gaps and limitations of the data?
Can you think of a realistic data science research situation where using these data (to train a model, perform a hypothesis-driven research, or make business decisions) might still be appropriate and useful, despite its inherent limitations and biases?
How might a researcher supplement or transform this dataset to potentially correct for the limitations/biases you observed?


## Best practices for documentation
- PEP 8 – Style Guide for Python Code. ([Reference link](https://peps.python.org/pep-0008/))
- Use of relative path addresses to help in reproducibility.
- Use of intuitive variable and function names to ease in understanding.
- Appropriate comments and documentation provided for the data aquisition, data processing and data analysis steps.
- Description of all data files present in the repository mentioned.
- Exception Handling taken care of in the code to avoid breaking the API loops.

## Author
[Nayantara Mohan](https://github.com/nayantaramohan) 
