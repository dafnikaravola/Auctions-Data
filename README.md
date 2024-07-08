# Inside Eurobank's Pillar Portfolio: Are auctions disproportionately affecting Athens' poorer?

This is my first complete project for the LEDE Program 2024, at Columbia Journalism School.

Find the website [here](https://dafnikaravola.github.io/auctions/)

The project uses a dataset created by the Reporters United team (which I am part of) 
for the purposes of a two-part investigation: [Part 1](https://www.reportersunited.gr/12587/kokkinia-daneia-pillar-eurobank/) &  [Part 2](https://www.reportersunited.gr/13302/pillar-eurobank-pleistiriasmoi/)

The dataset can be found [here](https://docs.google.com/spreadsheets/d/1cKs3ohi3u7KOwbuqIXuTTaBjZv2A4PSZFQswlH1r8tE/edit?gid=1386900784#gid=1386900784)

Unfortunately, the dataset is in Greek, we hope that an English version is soon to follow.

## The goal:

**The analysis attempts to find out if the low-income population of Athens & Attica (the broader region around Athens) is disproportionately affected by auctions happening within Eurobank's Pillar portfolio of non-performing loans.** 

To do that, I analyse the dataset's aspects that are related to urban characteristics, such as property type, floor number, construction year and surface area. 
Moreover, I rely on the traditional horizontal and vertical class distribution characteristics of Attica's urban landscape, as explained in the article. 

## Important Findings

* 8 in 10 auctioned properties are residential houses
* 45% of them are located in Attica region
* There is an inversely proportional relationship between the number of auctions and the auction prices.
* Lower-income municipalities have more auctioned properties at lower prices and higher-income municipalities have fewer auctions at higher prices.
* Auctions affect households that are located within lower floor levels, a typical class indicator for Greece
* The most frequent residential property type auctioned is an apartment between 50 and 99 square meters, built from the '70s to the 90's

## Data Analysis & Visualisation

The following tools have been used: 

**Data Analysis**

* **Pandas Library and Jupyter Notebook:** Were used to calculate the concentration of property types for all of Greece and the region of Attica, to calculate the distribution with each of Attica's municipalities,
* to correlate the surface area range with the construction years range, to export database that would be imported into QGIS in the next step.
*see files: "JupNotebook_Auctions Dataset.ipynb", "Data_Attiki.csv", "Data_Attiki_Katoikia.csv", "Data_Attiki_Freq_Types.csv*

* **QGIS**: Was used to further analyse the datasets based on Attica's municipalities. To do that, I matched the existing municipal names with another shapefile polygon layer of Attica's municipalities.
* Then I used QGIS functions to calculate and visualise the number of auctions and the average auction price per municipality, resulting in two choropleth maps.

**Visualisation**
* **QGIS** : for the map bases
* **Flourish** : for the charts bases
* **Illustrator** : for processing maps and charts
* **ai2html** : for converting the map into html and the handle it with D3 

**Website**
* Soma's templates

## Files index

* **JupNotebook_Auctions Dataset.ipynb** : Jupyter Notebook
* **Data_Attiki.csv** : the original dataset filtered for Attica region, with the addition of the columns "year range" and "surface range"
*  **Data_Attiki_Katoikia.csv** : the dataframe of Attica's auctions filtered for only residential properties
*  **Data_Attiki_QGIS** : the dataframe processed in QGIS. Additions: standardised municipal names, avg price per municipality, number of auctions per municipality
*   **Visualisations.ai** : the Illustrator file will all my visualisations & ai2html script
*  **index 2.html** : the HTML file of the website
*  **scrolly-styles.css** : tehe CSS file of the website
*  **Auction_allmaps_nonresptxt.html** : the illustrator file converted in HTML through ai2html
*  **Auction_allmaps_nonresptxt-Artboard_1.png** : the base maps exported from QGIS and processed through Illustrator, for the scrolly part
* **Floor level, Heatmap, Property-Types-01, Ioannis_Dedes_2021** : the image files of the website

## Skills & Approaches

**Successes**

This project was focused more on learning new visualisation skills, and less on applying my data analysis coding skills. Most importantly, I successfully managed to learn how to use the ai2html Illustrator script. 
Additionally, I applied some of the basic Pandas we learned in class and managed to export the needed databases for QGIS. Finally, I learnt some new advanced analysis functions in QGIS.

**Yet to do**

I found out that I need to practice my Pandas skills more. Sometimes, I ended up doing calculations by hand, which would not have been possible if the database's size was not manageable. 
I would also like to learn how to include more than one interactive illustration by coupling ai2html and Soma's scrolly template. In my next project, I want to focus on scrapping and not use a ready dataframe.
