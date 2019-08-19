<img src="https://bit.ly/2VnXWr2" alt="Ironhack Logo" width="100"/>

# How are the technological hubs of manufacturing evolving in the world? An analysis on the rate of innovation. 

*[Fabia Höhne Tarragona]*

*[Data Analytics, Barcelona, June 2019]*

## Content
- [Project Description](#project-description)
- [Hypotheses / Questions](#hypotheses-/-questions)
- [Dataset](#dataset)
- [Cleaning](#cleaning)
- [Analysis](#analysis)
- [Model Training and Evaluation](#model-training-and-evaluation)
- [Conclusion](#conclusion)
- [Future Work](#future-work)
- [Workflow](#workflow)
- [Organization](#organization)
- [Links](#links)

<a name="project-description"></a>

## Project Description

In this project I am looking to answer the question of how technology and RnD hubs are changing across the world. 
The project is divided into two research directions:

#### The first will be an innovation rate analysis. 
There are several ways to measure this, there are a number of articles and stuides using a wide range of creative attributes to measure innvoation and tehcnological advancement [see link for example](https://ourworldindata.org/technological-progress). I will however, be focusing on industry indexes, taking the world banks indicators as a basis to technological measurements. 

The plan for this is to analyse the registrations of patents in manufacturing techniques and machinery across the world. This analysis will be divided in analysis by country, by field, and by company. 
From here, the aim is to see how trends have changed over time and make a prediction of what regions/ fields/ companies have the highest rate of innovation. I will use a number of datasets to create an inofmrative dashboard presenting which countries and industries could be of most interest for R&D in technology. 

#### The second step of the analysis will then be to take a specific filed of interest (relating to previous research I have carried out on the fields of semiconductor manufacturing and solar panel production lines) and to analyse how companies in those fields are evolving.

For this I will query the data for questions such as: 
    - Are more companies appearing?
    - How much funding do they get?
    - What is the drop rate of companies appearing in the field?


<a name="dataset"></a>

## Dataset
* Where did you get your data? If you downloaded a dataset (either public or private), describe where you downloaded it and include the command to load the dataset.

* For all types of datasets, provide a description of the size, complexity, and data types included in your dataset, as well as a schema of the tables if necessary.

1. World bank

Data from 1960s to 2018.
Open database for World Develpment indicators, includes variables such as intellectual property, exports and imports, patent applications, R&D expenditures (% of GDP), etc. 

[world bank](https://data.worldbank.org/topic/science-and-technology)

2. JRC-OECD COR&DIP database v.1, 2017 - European Parliment and OECD collaboration.

Database created 2017, latest information on patents form 2012 to 2014 (latest public version of data).
Open database that results out of the collaboration between the EU commission, JBC Directorate and the OECDDirectorate. The database contains information about R&D activity and IP assets of the top 2000 corporate R&D performers worldwide. 

[JRC-OECD](http://www.oecd.org/sti/intellectual-property-statistics-and-analysis.htm)

3. World intelectual property organisation. 
The WIPO has an open IP Statistic Data Centre with data from Dec. 2018 where information on the patent count of all countries can be found divided by industry. 

[WIPO](https://www.wipo.int/ipstats/en/)


4. Crunchbase
Database on Company creation and financing/ investements by sector and contry, from mid 1980s to 2015. 
Rights to data can be found in the data folder. 

[Crunchbase](https://data.crunchbase.com/docs/open-data-map)

<a name="cleaning"></a>

## Cleaning
Describe your full process of data wrangling and cleaning. Document why you chose to fill missing values, extract outliers, or create the variables you did, etc, as well as your thinking process.

<a name="analysis"></a>

## Analysis
* Overview the general steps you will go through to analyse your data in order to test your hypothesis.
* Document each step of your data exploration and analysis.
* Include charts to demonstrate the effect of your work. 
* If you use ML in your final project, describe your feature selection process.

<a name="model-training-and-evaluation"></a>

## Model Training and Evaluation
*Include this section only if you chose to include ML in your project.*
* Describe how you trained your model, the results you obtained, and how you evaluated those results.

<a name="conclusion"></a>

## Conclusion
* Summarize your results. What do they mean?
* What can you say about your hypotheses?
* Interpret your findings in terms of the human-understandable question you try to answer.

<a name="future-work"></a>

## Future Work
Address any questions you were unable to answer, or any next steps or future extensions to your project.

<a name="workflow"></a>

## Workflow
The defined workflow follows different steps:

1. Topic choice and definition of tasks and questions.
2. Data acquisition 
3. Data cleaning and export to SQL 
4. Exploratory Data Analysis
5. Data Visualization
6. Answering of questions (prediction and drop rate machine learning)

<a name="organization"></a>

## Organization
##### The Project is organised using the following structure in the Repository:
- README.md file for general project overview, question definition and initial resources.
- Data folder divided into original and cleaned data. 
- Visualisation folder where you can find the graphics developed through the project. 
- Code folder containing the three codebooks for Database Creation, Data Wrangling, and Analysis *(the latter contains the conclusions, afterthoughts, and additional links to literature)*.
    - In each of the codebooks you will find the step by step explanations and reasoning of my workflow. 

##### The organization of the project has been carried out using the following: 
1. Time management: Trello (Kanban Board)
2. Code, data and folder management: GitHub
3. Good Practices:
    3.1. PEP 8
    3.2. Jupyer Notebook for coding
    3.3. Consistent GitHub commits with comments and summaries of working steps


<a name="links"></a>

## Links

[Repository](https://github.com/FHnt97/Project-Week-8-Final-Project)  
[Slides](https://docs.google.com/presentation/d/1FvAILtooPfkUU3_7fx-xLv4j2yqRXDIqy5rY450gI-w/edit?usp=sharing)  
[Trello](https://trello.com/invite/b/X4MiUR2u/04f26dfb6c9d61a9dc2a26f48cc6dcaa/project-5)  