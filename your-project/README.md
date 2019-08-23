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
There are several ways to measure this, there are a number of articles and studies using a wide range of creative attributes to measure innovation and technological advancement [see link for example](https://ourworldindata.org/technological-progress). I will, however, be focusing on industry indexes, taking the world banks indicators as a basis to technological measurements. 

The plan for this is to analyse the registrations of patents in manufacturing techniques and machinery across the world. This analysis will be divided in analysis by country, by field, and by company. 

From here, the aim is to see how trends have changed over time and make a prediction of what regions have the highest rate of innovation. 

**The goal of this is to see how many innovative ideas companies and universities in each country files.**

The second step is then to analyse several indices provided by the world bank. These include variables such as % of GDP invested in R&D, number of articles and journals published, number of technicians working in R&D, etc.  Aiming to formulate a **prediction as to which countries are expected to have the highest innovation rate.**

##### This section will be structured as follows:

-  Q1.1: The evolution of number of patents by country - a world map

-  Q1.2: How do we measure innovation? Innovation rate indices, their significance and world trends. 

-  Q1.3: The set up of a hypothesis: causality between patent trends and chose innovation indices

-  Q1.4: The creation of a dashboard - what countries are the most interesting? 

### The second step was to look more in depth into one of the industries. 

For this step, what would be great is to create a template so that, on the basis of this report, I could, in the future, code a search bar. This would allow me to easily find information on any industry and give me the initial insights on it, guiding the initiaition of a more in depth market analysis. 

What industries have a high innovation rate, and how is the market in that field?
I will look into the fields of industry with the highest innovation/ patent number filing, and I will carry out a market analysis in this field, looking into which companies are the strongest and invest the most in R&D in given field. I will try answering the following questions:
- What industries are the most innovative?

- How much are we spending on innovation?

- What companies are the most innovative in the market?

- What is the drop rate of companies appearing in the field?

##### This section is structured as follows:

- Q2.1: A market analysis: what field/industry has the biggest R&D investment/ highest growth in patents?

- Q2.2: In that field, what companies do we have, how much do they invest into R&D compared to their profits?

- Q3: Taking a start-up database, what is the drop rate of companies in that field (if last funding longer than 5 years ago = inactive)?


<a name="dataset"></a>

## Dataset

1. World bank

Data from 1960s to 2018.

Open database for World Development indicators, includes variables such as intellectual property, exports and imports, patent applications, R&D expenditures (% of GDP), etc. 

The World bank also contains a list for country code indexes and classification into financial groups, which will be used for the grouping of data. 

[World Bank](https://data.worldbank.org/topic/science-and-technology)

2. JRC-OECD COR&DIP database v.1, 2017 - European Parliament and OECD collaboration.

Database created 2017, latest information on patents from 2012 to 2014 (latest public version of data).

Open database that results out of the collaboration between the EU commission, JBC Directorate and the OECD Directorate. The database contains information about R&D activity and IP assets of the top 2000 corporate R&D performers worldwide. 

This database holds several sets of information, one on the company's financial situation (R&D investment, profit, employees, etc.), the other informs us on patents registered. 

To correctly interpreted the data, I also had to add an industry key, these will follow the Industry Classification Benchmark indices. 

[JRC-OECD](http://www.oecd.org/sti/intellectual-property-statistics-and-analysis.htm)

3. World intellectual property organisation. 

The WIPO has an open IP Statistic Data Centre with data from Dec. 2018 where information on the patent count of all countries can be found divided by industry. 

[WIPO](https://www.wipo.int/ipstats/en/)


4. Crunchbase

Database on Company creation and financing/ investments by sector and country, from mid 1980s to 2015. 
Rights to data can be found in the data folder. 

[Crunchbase](https://data.crunchbase.com/docs/open-data-map)

<a name="cleaning"></a>

## Cleaning
As most of the data comes from official sources, the cleaning process was not very complex. 

It consisted basically of filling in some missing values, dropping unnecessary columns and merging information from different tables into one data frame for future use. 

To see more details on the cleaning process, follow this [link.](./01_code/01_Data_warangling.ipynb)


<a name="analysis"></a>

## Analysis
The analysis was done following the questions defined above. 

Here is a summary from the paper for how I answered each question:

### Q1.1: The evolution of number of patents by country - a world map

To answer this question, I will use the dataset from the WIPO (world intellectual property organisation). 

This dataset includes a list of patents registered by each country in the WIPO over a timespan from 1980 to 2017. 

The idea is to **1. visualise the evolution of patent application volume over time for each country**, as well as finding the **2. global trend**. 

In this section you will find the following visualisations and conclusions:

1. <br>
    1.1. Patent distribution in the world in the 80s
    
    1.2. Patent distribution in the world in the 90s
    
    1.3. Patent distribution in the world in the 00s
    
    1.4. Patent distribution in the world in the 10s
 > **Mapping** <br>
For the map I will need to import the geolocations. The table is saved outside of the repo. due to its size. 
<br>
I will be using the normal table, not the transposed one, and I will be adding the number of patents for every 10 years, so that I obtain 4 different graphs, which will show the changes over time for each country. 


2. <br>
    2.1. Patent distribution over time for all countries (line, not stacked)
    
    2.2. Patent volume trend of top 5 innovative countries in the time range 2010-2017 (from 1980 to 2017) (bar plot)
    

### Q1.2:How do we measure innovation? Innovation rate indices and world trends. 

for this section I will be using data from the World Bank. 
The database contain information from the 90s to 2010 and encompasses a number of indicators of innovation for each country in the world. 


I will start the analysis with the graphing of some **1. overall global trends**. 

Visualisations and conclusions in section: 


1. <br>

    1.1. Changes in number of patent and trademark applications worldwide (bar graph, stacked, from 1991 to 2017)
    
    1.2. Worldwide trend in % of GDP invested into RnD (line graph, from 1991 to 2017)
    
    1.3. Number of people working in RnD worldwide (line graph, from 1991 to 2017)
    
    1.4. Pair plot for all variables - relationship graph
    
### Q1.3: The set up of a hypothesis: relationship between patent applications and indicators and choosing of variables    

For this part of the project, I will be using the same data as in the previous section. 

I will make the following assumption:
<h5 align="center"> Innovation is directly linked with the number of patents applied for in each country </h5>

This means that I can look for a relationship between innovation (patent application or residents and non residents) and the other indicators to make a prediction of which countries' innovation rate will continue growing. 

For this I will start looking at correlations between variables, followed by a PanelOLS and a BetweenOLS to see the relationship between variables. 


It is important to notice that this data is **panel data**, so I will be using specific functions for panel data. 

Visualisations and conclusions: 

1. <br>

    1.1. Correlation graphic for innovation indices (Pearson correlation model)
    
    1.2. Panel OLS 
    
PanelOLS uses fixed effect (i.e., entity effects) to eliminate the entity specific components. This is mathematically equivalent to including a dummy variable for each entity, although the implementation does not do this for performance reasons.
    
    1.3. Between OLS
    
BetweenOLS is somewhat more general than the other estimators and can be used to model 2 effects (e.g., entity and time effects).


### Q1.4: What countries are the most interesting?

This section continues the prediction of growth of countries to identify where innovation is leading us (i.e. to what regions) (same dataset used).

The first step for me was to group my data, I tired doing this through **1. correlations of the development of different countries**, but I soon realised that it was more time-intensive than I could allow myself. 

I therefore grouped by pre-determined groups (by income level and regions). 

From there I predicted ***2. max. expected growth** through a linear regression.

I then moved on to trying to predict innovation with a **3. regression model** using the variables chosen by the PanelOLS.
>> I tried a normal linear regression, then realised I have no data for the prediction. <br> A future development will therefore be predicting the innovation through an ANOVA model. 


Visualisations and conclusions: 

1. <br>

    1.1. Correlation between countries (Pearson correlation model)
    
    1.2. Current innovation ranking (by sorting)
    
    1.3. Predicted innovation growth ranking (by regression slope)
    
    1.4. Regression model (trial)

###  Q2.1: A market analysis: what field/industry has the highest growth in patents/ biggest R&D investment ?


Visualisations and conclusions:

1. <br>
    
    1.1. Total industry patents per year (line graph with sum of all patents from 80s to 2017)
    
    1.2. Max growth industries in last 5 years (sorted, in list format)
    
    1.3. Development trend of the top 3 most innovative industries (line graph, from 80s to 2017)
    
    1.4. # top 5 industries with highest RnD investment relative to profit:

2. <br>

    2.1. Top 5 industries with highest RnD investment relative to profit (list)
    
    2.2. Top 5 industries with highest patent count (list)
    
    
3. OVERALL OVERVIEW: 

    3.1. Pie chart for patent count per industry and company count per industry


#### 2.1.1. Biggest growth in patents

To analyse which market has seen the biggest innovation (measured through the number of patents registered) the WIPO dataset used in the main analysis. 

The WIPO dataset contains number of patents registered per industry per year and country.

#### 2.1.2. Biggest R&D investment

I will be using the patents by industry database form the RC-OECD COR&DIP database v.1, 2017 (European Parliament and OECD collaboration).

The RC-OECD COR&DIP database v.1 database was created 2017, and holds information on the top 2000 corporate RnD performers worldwide form 2012 to 2014. 

This database holds several sets of information, one on the company's financial situation (R&D investment, profit, employees, etc.), the other informs us on patents registered. 


For the biggest investments I will be using a table on company information.

### Q2.2: In that field, what companies do we have, how much do they invest into R&D compared to their profits?

(Using the same data as above)

Fields of study: ```Technology Hardware & Equipment``` and ```Electronic & Electrical Equipment```. 

As I have a larger percentage of companies in the ```Technology Hardware & Equipment``` sector in my data, I will a more in depth market analysis on this industry. 

Visualisations and conclusions:

1. <br>

    1.1. Market leaders by number of patents registered (sorted DF)
    
    1.2. Company with highest RnD investment (sorted DF)
    
    1.3. Company with highest RnD investment relative to their operational profit (sorted DF)
    
    
2. <br>

    2.1. Countries who hold the max. number of patents in industry over 4 years (sorted DF)
    
    2.2. Countries whose companies have invested the most in RnD (sorted DF)

### Q3: Taking a start-up database, what is the drop rate of companies in that field?

Lastly, I wanted to graph the drop rate of companies in the chosen industry. 
For this, I used the CrunchBase dataset form 2015. This set contains information on start-ups, their market, their status and when they where founded as well as their last funding. 

Visualisations:
- Drop rate diagram

<a name="conclusion"></a>

## Conclusion
#### Part 1:
##### When looking at the overall trend in innovation I obtained the following results:

We see is a clear trend in growth in East Asia, as well as Europe and the States. This comes to no surprise as these countries are known for their extreme growth. 
Looking at the now, as of 2017 (the latest year of my data), the region with max. number of patents and trademarks filed is East Asia, followed by North America and Europe.

##### Looking at the innovation indexes:
Surprisingly, when looking at the trends of some of the variables of measurement of innovation rate, we see that there is a stagnation in RnD across the board (form numbers of employees to investment) since 2016. It might be interesting to do some research on this to find the cause of this phenomenon. 

My conclusion form both the panel and the between OLS is that following variables should be used to explain the data when performing a regression: 

- Research and development expenditure (% of GDP)
- Technicians in R&D (per million people)
- Scientific and technical journal articles
- High-technology exports (current US$)

I managed to obtain a ```R-squared``` of **0.55** in the ```PanelOLS``` and of **0.94** in the ```BetweenOLS```. 

    *The R-squared indicates that the variables represent 92% of the data.

###### Predicting the future growth:
I obtained the following expected growth ranking: 
    1. East Asia & Pacific
    2. North America
    3. Latin America & Caribbean
    4. South Asia
    5. Europe & Central Asia and 
    5. Middle East & North Africa
    6. Sub-Saharan Africa
    
#### Part 2:
##### Most innovative market:
From the quick analysis carried out, we see that the "most innovative market" (that with the biggest increase in patent filing in the last years) is the **Electrical machinery, apparatus, and energy** industry.

This fits in well with my initial hypothesis and with my expertise, as I was hoping to do a market analysis on electrical machinery manufacturing as well as the chip production. 

When looking at the biggest RnD investors, we see, that overall, the industry where most companies register patent is similar to that analysed in the fastest innovating sector i.e. Electrical machinery, apparatus, and energy industry, or as it is called in this dataset: Technology Hardware & Equipment, and Electronic & Electrical Equipment.

It is interesting to see, however that relative to profit, the industries with highest investment in RnD are not the same as those with the highest number of patents. After running a quick regression between RnD investment and patent application, I got an ```R-value``` of 0.4, which proves little relationship. 

##### Most interesting locations and companies in the **Electrical machinery, apparatus, and energy** industry.
I retrieved the following suggestions from my data: 

The most interesting companies (as they have the highest investment in RnD in relation to their operational profit) are: 

- VIAVI SOLUTIONS (Hardware, US)
- XCERRA (Semicon, US)
- LOGITECH INTERNATIONAL (Hardware , CH)
- IMAGINATION TECHNOLOGIES (Semicon, UK)



##### The drop rate model
The results on this model were not as expected. It needs further work as the sample is not representative. I will therefore ignore it in my results and conclusion


<a name="future-work"></a>

## Future Work
- Timely prediction of innovation using time series

- Comparison of % growth development between countries 

- Code search bar for market analysis


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
    
    3.2. Jupyter Notebook for coding
    
    3.3. Consistent GitHub commits with comments and summaries of working steps


<a name="links"></a>

## To read more on this:

- A similar analysis, which inspired part of the research, analysing the digital economy can be found [here](http://www.oecd.org/sti/world-top-rd-investors.pdf). 

- For more information on the distribution of papers visit the [WIPO webpage.](https://www.wipo.int/edocs/infogdocs/en/ipfactsandfigures2018/)

- More reports on innovation, patents, and R&D [here](https://www.wipo.int/edocs/pubdocs/en/wipo_pub_941_2018.pdf)

## Links

[Repository](https://github.com/FHnt97/Project-Week-8-Final-Project)  
[Slides](https://docs.google.com/presentation/d/1FvAILtooPfkUU3_7fx-xLv4j2yqRXDIqy5rY450gI-w/edit?usp=sharing)  
[Trello](https://trello.com/invite/b/X4MiUR2u/04f26dfb6c9d61a9dc2a26f48cc6dcaa/project-5)  
