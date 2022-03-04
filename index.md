# RStudio Visualizations of the CDC's Death Data for 2020
### By: Eythan Jenkins

## Introduction

In 2020, Heart disease was the leading cause of death for Americans. However, this doesn't mean that it was the leading cause of death for ALL Americans. Once you change the scope from wide to narrow, and break the population down into different demographics, you get to see how different people face different challenges. This is the core discovery that I made when looking at the CDC's Data for the Leading Causes of Death. Therefore, when looking at the leading causes of death, it can be beneficial to break it down into subsections. 

I support this discovery with the data visulaizations I created. They will show the leading causes of death as a whole, and then broken down by age, sex, and race; I will also break down sex and race into different age brackets. When broken into these different demographics, it becomes clear that while heart disease is a major issue (it is still the leading cause of death after all), putting all Americans under the umbrella of heart disease being their biggest obstacle, may be a bit misleading.

## Dataset

I acquired my data from the U.S. Government's Centers of Disease Control and Prevention's website. The CDC's Mission is "to protect America from health, safety and security threats, both foreign and in the U.S." [CDC, 2022](https://www.cdc.gov/about/organization/mission.htm) Therefore, it is their duty to collect information on how Americans are dying, as they need to take steps to mitigate these threats of death.

The data from them that I am using is their Leading Cause of Death Reports, whcih span from 1981 - 2020. I am interested in their 2020 data only, as it is the most recent available data that they have to show, and will be most representative of the current year, 2022. My interest for using the CDC's data is that it is very reliable: it is a trusted government source. Additionally, the official nature makes it less prone for needing "data wrangling" (although I still had to do a bit, which I will disclose later).

The CDC did not give a set of raw data straight out- they instead have a short form where I fill out the parameters of the data I am looking for. In here, I can choose the census region, years of data, race, sex, and how I want my age bins to be sized. I also select the number of top causes of death I want to observe, and I am given the ability to download the .csv of the data I want. While a system like this offers a lot of flexibility for me to create subsets of the data I want, it probably would have been better if they offered a whole sheet of data instead, and I could use R to break it into my desired subsets, especially since I found myself needing to create subsets in R anyways. The data was derived from here: [CDC, 2020](https://wisqars.cdc.gov/fatal-leading) I opted to download the top 15 causes of death, but in my visualizations, I never looked at more than the top 5 for an individual demographic to keep it concise. 

## Initial Questions

The reason I decided to do a project on the leading causes of death was because I had recently seen a social media post which claimed that the leading cause of death for individuals age 1-45 was drug overdose. This went against what I already though to be true: the leading cause of death for Americans was heart disease. Since this project focused on collecting data, I figured that I would look into the information myself. To start myself off, I created a few questions to guide where I wanted to go with my data:

    1) For causes of death in the U.S., which is the leading for 2020?
    2) Causes of death by age groups in 2020: which are their leading causes of deaths? 
    3) How does the leading cause of death vary by gender and race?
  
  I was able to get answers to all 3 of these questions, and visualize my answers. Additionally, I came up with a new question as well: What is the breakdown of Unintentional Injury for those under age 45? This was important to why I originally wanted to view this data: the claim was that those under age 45 were dying primarily by drug overdose, but the data showed the primary cause of death to be "unintentional injury." I then discovered when breaking down "unintentional injury" into its components, that "poisoning," i.e. a drug overdose, was the majority of unintentional injury deaths. While I didn't visualize this myself, the CDC had already created a visualization showing the breakdown of accidental injury (and despite it being a component of the leading cause of death, it still outnumbered the second leading cause of death number-wise): [CDC Visualization](https://www.cdc.gov/injury/wisqars/animated-leading-causes.html)
  
  While the data was mostly easy to work with, there were a few occasions where I had to fix a few things to make the .csv more compatible with how R wanted to visualize my data. For instance when plotting the age groups, R didn't put them in order of 1-4, 5-9, 10-14, 15-25 etc. Instead, it would order them by character, so ages 5-9 would go between 45-54 and 55-64. To fix this, I had to change the values 1-4 and 5-9 to be 01-04 and 05-09. This allowed the data to be sorted correctly. Another issue I had was when it made my number of deaths a character value, rather than a numeric value. However, the as.integer() function solved that fairly easily. The final bit of data wrangling I had to do was create subsets for my data. I created data subsets to get the top 5 leading causes of death only (out of the set of 15 I downloaded), as well as to make subsets of the specific age groups, and in one graph, I made a subset just comparing heart disease among all ages.

## Discoveries & Insights

I came up with a total of 16 visualizations:
Images should be large and easy to see and interperate. 
Captions underneath should be 20-70 words long.

## Conclusion

Final summary of the data and what you found during this project.

## Sources

In addition to using the CDC as my data source, I used a few sources to better understand how to plot using bar charts in R:
[To create better labels and to make bar charts in R's ggplots](http://www.sthda.com/english/wiki/ggplot2-barplots-quick-start-guide-r-software-and-data-visualization)
[Sorting a graph by greatest to least](https://sebastiansauer.github.io/ordering-bars/)
