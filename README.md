# Award-Winning Manga Visualisation (Find it [here](https://public.tableau.com/app/profile/shuane.telford/viz/MangaDashboardFINAL/MangaBeeswarm))

## Introduction

This project is a creative endeavour related to data analysis. Using data on award-winning manga through the My Anime List (MAL) database, this project focuses on the visual component of storytelling with data. Through simplistic visuals and guides, This project communicates a dense amount of data, such as popularity, scoring, manga information, and release years in a digestible and appealing format. As this is a creative project, it does not strictly adhere to the best principles of data analysis. Nonetheless, this project captures its fundamental ideas, whilst maintaining a creative approach.

## Project Overview 

- Produced a creative dashboard showcasing manga popularity, scoring, release year, demographics, genres, themes, and release year in an easily digestible and visually appealing format.
- Utilised SQL commands in Tableau to help filter and refine the raw dataset.
- Utilised Excel for further data refinement and ad-hoc data collection and input.
- Utilised built-in relation, join, and SQL functions in Tableau to enhance existing data and generate insightful measures such as genre, theme, and demographic counts, as well as custom informational tooltips.

## Skills Gained From Project

- Refined understanding of creating custom measures and filtering using Tableau.
- Refined understanding of Tableau’s relationship and join function and how they manipulate existing data.
- Refined ability to produce a meaningful but simple visual, doubling as an effective medium for storytelling through data.

## Data Description (Find the dataset [here](https://www.kaggle.com/datasets/andreuvallhernndez/myanimelist?select=manga.csv)

The MAL dataset contains manga registered (by staff or user consensus) on the MAL website, this particular dataset being up to date as of AUG 2023. The data set contains useful information related to users and the manga itself, including the title (in English, Japanese, and title synonyms), scored by user count, members, favourites, demographics, theme, genre, start data, pictures, and more.


## Tools Used
- Tableau
- Excel
- Canva

<details>
  <summary><h2>Methodology<h2></summary>

  1. **Data Acquisition and Initial Exploraion**
     - Acquire dataset from [Kaggle](https://www.kaggle.com/datasets/andreuvallhernndez/myanimelist?select=manga.csv). The dataset contains a single CSV file called ‘manga.csv’ containing up-to-date manga entries and information on the title as of AUG 2023.
     - Kaggle’s data explorer and the raw CSV file were examined to better understand the contents and structure of the data.

  2. **Importing Data to Tableau and EDA**
     - ‘manga.csv’ was imported into Tableau and basic visuals such as bar charts, scatter plots, histograms, and matrices were made to understand how data could be displayed.
     - Once EDA was complete. The following useful columns were noted and filtered: authors, author roles, demographics, titles, genres, picture, real start date, serialisations, status, synopsis, themes, favourites, members, scored by count.
     - The data was further filtered using the CONTAINS function and logical operators so that entries where the genre contained the string “award” and the score column had scores >0 were kept.

  3. **Beeswarm dataset generation**
     - Once data was appropriately filtered, a smaller dataset containing the scores, popularity (measured as taking the max per row of the scored by count, members, and favourites columns), and start date (formatted as an INT of the year) was exported from Tableau.
     - This data was then imported into the Beeswarm visual tool using x: year, y: score, and sizing as the popularity measure.
     - This generated Beeswarm CSV and the graphing template was downloaded for later use in Tableau.

  4. **Data refinement in Tableau**
     - Data usability issues appeared as the original data contained columns formatted as lists or nested lists, incompatible with Tableau.
     - First, text storage translation errors caused some strings for the titles (like those with accents) to be inappropriately stored. A custom filter was created that helped select between the English, Japanese, or first title within the synonym titles to be stored and used as the final title.
     - REPLACE and CONTAINS were used to check and eliminate extra list operators such as {} and () within columns.
     - Once problem columns were cleaned up, Tableau’s custom split function was used to split genres, themes, authors, and secondary authors into multiple columns.
     - The pivot function was used to condense the multiple generated columns into a singular genre, theme, author, and secondary author columns which are a useable format by Tableau.

  5. **Data recollection for missing values and relationship-building**
     - In total, there were now 2 datasets: (1) A custom Beeswarm visual dataset and (2) A meta-data dataset containing information about the manga and user info.
     - Missing data such as demographic and year were easily Googleable and were inputted manually into dataset (2).

  6. **Data import and relationship management in Tableau**
     - Datasets (1) and (2) were related through Tableau’s custom relationship tool.
     - The relationship was verified as working appropriately by generating a few bar charts and matrices for data like genres and themes.
     
  7. **Visual creation in Tableau**
     - Three Bar charts for genre, theme, and demographic counts were created to demonstrate the distribution of these data across the award winners.
     - The tooltip was modified so that as users would hover over a bar it would read as a prose description of the count and the genre.
     - E.g. “69 Manga contain a Comedy theme”.
     - Visual filters were also applied such as creating multiple sheets to demonstrate ongoing and on hiatus manga, as well as highlighting top manga in the colour red.

  8. **Visual creation in Canva**
     - The beeswarm plot is limited in customisability.
     - Canva was used to create a custom visual format meant to replicate a Manga panel.
     - Canva allowed the use of custom images like Manga characters, creating a custom legend format and including visuals to point towards data.
    
  9. **Interactivity and Usability**
      - Highlighters were embedded in the main dashboard to allow users to highlight specific genres, themes, demographics, and even specific titles as they desired Highlighters.
      - A custom tooltip was created so that when a user hovers over a dot on the Beeswarm plot it would display: the title, author(s), an image of the manga, MAL user score, MAL user popularity, genres, themes, and the initial release year.

</details>

## Final Dashboard (Please check out the interactable dashboard [here](https://public.tableau.com/app/profile/shuane.telford/viz/MangaDashboardFINAL/MangaBeeswarm)

<img src="https://github.com/ShuaneTelford/Award-Winning-Manga-Visualisation/blob/main/Images/Manga%20Beeswarm%20Final.png" />


## Conclusion

- This project resulted in the exploration of storytelling through data with an emphasis on creativity. In particular data principles such as showing dense amounts of relevant and informative data to users were adhered to whilst maintaining an air of creativity and stylishness, appealing to a wide array of potential viewers and users.
- The project allowed for the refinement of data filtering techniques using Tableau and the use of custom visuals and data manipulation to allow data to be useable for multiple tools.
- Lastly, this project was fun to create and informative on how and what data matters to an end user. Storytelling with data is a hard skill to learn and master but with this project, I hope I was able to show that I am heading along the right path :)
