{
 "cells": [
  {
   "cell_type": "markdown",
   "id": "d510df11-fdaa-4a11-86e6-3348224f17e7",
   "metadata": {},
   "source": [
    "# Inside Eurobank's Pillar Portfolio: Are auctions disproportionately affecting Athens' poorer?\n"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "cbc4d06a-0f50-45a6-9a52-911699a81169",
   "metadata": {},
   "source": [
    "This is my first complete project for the LEDE Program 2024, at Columbia Journalism School."
   ]
  },
  {
   "cell_type": "markdown",
   "id": "23f8fc78-d823-42e9-8c23-339e892df9e2",
   "metadata": {},
   "source": [
    "The project uses a dataset created by the Reporters United team (which I am part of) \n",
    "for the purposes of a two-part investigation: [Part 1](https://www.reportersunited.gr/12587/kokkinia-daneia-pillar-eurobank/) &  [Part 2](https://www.reportersunited.gr/13302/pillar-eurobank-pleistiriasmoi/)\n",
    "\n",
    "The dataset can be found [here](https://docs.google.com/spreadsheets/d/1cKs3ohi3u7KOwbuqIXuTTaBjZv2A4PSZFQswlH1r8tE/edit?gid=1386900784#gid=1386900784)\n",
    "\n",
    "Unfortunately, the dataset is in Greek, we hope that an English version is soon to follow."
   ]
  },
  {
   "cell_type": "markdown",
   "id": "2cf795b6-de1c-4d3c-a528-d7dba60a1fe3",
   "metadata": {},
   "source": [
    "## The goal:\n",
    "\n",
    "**The analysis attempts to find out if the low-income population of Athens & Attica (the broader region around Athens) is disproportionately affected by auctions happening within Eurobank's Pillar portfolio of non-performing loans.** \n",
    "\n",
    "To do that, I analyse the dataset's aspects that are related to urban characteristics, such as property type, floor number, construction year and surface area. Moreover, I rely on the traditional horizontal and vertical class distribution characteristics of Attica's urban landscape, as explained in the article. "
   ]
  },
  {
   "cell_type": "markdown",
   "id": "b5f4f83c-df9f-4c8a-b5cf-790e083bdb71",
   "metadata": {},
   "source": [
    "## Important Findings\n",
    "\n",
    "* 8 in 10 auctioned properties are residential houses\n",
    "* 45% of them are located in Attica region\n",
    "* There is an inversely proportional relationship between the number of auctions and the auction prices.\n",
    "* Lower-income municipalities have more auctioned properties at lower prices and higher-income municipalities have fewer auctions at higher prices.\n",
    "* Auctions affect households that are located within lower floor levels, a typical class indicator for Greece\n",
    "* The most frequent residential property type auctioned is an apartment between 50 and 99 square meters, built from the '70s to the 90's"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "9108212e-8b51-43c1-be36-6c2625d05449",
   "metadata": {},
   "source": [
    "## Data Analysis & Visualisation\n",
    "\n",
    "The following tools have been used: \n",
    "\n",
    "**Data Analysis**\n",
    "\n",
    "* **Pandas Library and Jupyter Notebook:** Were used to calculate the concentration of property types for all of Greece and the region of Attica, to calculate the distribution with each of Attica's municipalities, to correlate the surface area range with the construction years range, to export database that would be imported into QGIS in the next step.\n",
    "*see files: \"JupNotebook_Auctions Dataset.ipynb\", \"Data_Attiki.csv\", \"Data_Attiki_Katoikia.csv\", \"Data_Attiki_Freq_Types.csv*\n",
    "\n",
    "* **QGIS**: Was used to further analyse the datasets based on Attica's municipalities. To do that, I matched the existing municipal names with another shapefile polygon layer of Attica's municipalities. Then I used QGIS functions to calculate and visualise the number of auctions and the average auction price per municipality, resulting in two choropleth maps.\n",
    "\n",
    "**Visualisation**\n",
    "* **QGIS** : for the map bases\n",
    "* **Flourish** : for the charts bases\n",
    "* **Illustrator** : for processing maps and charts\n",
    "* **ai2html** : for converting the map into html and the handle it with D3 \n",
    "\n",
    "**Website**\n",
    "* Soma's templates"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "0c3391ea-d7a6-483e-ad43-4d4740ee0ba3",
   "metadata": {},
   "source": [
    "## File index\n",
    "\n",
    "* **JupNotebook_Auctions Dataset.ipynb** : Jupyter Notebook\n",
    "* **Data_Attiki.csv** : the original dataset filtered for Attica region, with the addition of the columns \"year range\" and \"surface range\"\n",
    "*  **Data_Attiki_Katoikia.csv** : the dataframe of Attica's auctions filtered for only residential properties\n",
    "*  **index 2.html** : the HTML file of the website\n",
    "*  **scrolly-styles.css** : tehe CSS file of the website\n",
    "*  **Auction_allmaps_nonresptxt.html** : the illustrator file converted in HTML through ai2html\n",
    "*  **Auction_allmaps_nonresptxt-Artboard_1.png** : the base maps exported from QGIS and processed through Illustrator, for the scrolly part\n",
    "* **Floor level, Heatmap, Property-Types-01, Ioannis_Dedes_2021** : the image files of the website"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "14dbbc83-031e-40e8-b8db-ecc3522136eb",
   "metadata": {},
   "source": [
    "## Skills & Approaches\n",
    "\n",
    "**Successes**\n",
    "\n",
    "This project was focused more on learning new visualisation skills, and less on applying my data analysis coding skills. Most importantly, I successfully managed to learn how to use the ai2html Illustrator script. Additionally, I applied some of the basic Pandas we learned in class and managed to export the needed databases for QGIS. Finally, I learnt some new advanced analysis functions in QGIS.\n",
    "\n",
    "**Yet to do**\n",
    "\n",
    "I found out that I need to practice my Pandas skills more. Sometimes, I ended up doing calculations by hand, which would not have been possible if the database's size was not manageable. \n",
    "I would also like to learn how to include more than one interactive illustration by coupling ai2html and Soma's scrolly template. In my next project, I want to focus on scrapping and not use a ready dataframe."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "ba14c886-1e5d-4cd5-9621-68c751ac2c71",
   "metadata": {},
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3 (ipykernel)",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.11.9"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
