---
layout: default
title: Andrew Marsee, Data Scientist
sitemap: true
---

# Welcome, I'm Andrew Marsee

I'm a data scientist relatively new to the field.

I'll be adding to this website over the coming days and months

In the meantime check out an application I made below and [my resume](https://andrewmarsee.com/resume/).

-------------------------------------------------


<iframe id="nbaShinyDashboard"
    title="NBA Stats Dashboard"
    width="500"
    height="500"
    src="https://amarsee.shinyapps.io/nba-stats-shiny-dashboard/">
</iframe>


## Effect of NBA Scheduling on Game Outcomes

Midcourse Project for Nashville Software School Data Science Bootcamp

Interactive Shiny App for exploring how certain parameters affect team performance

Shinyapps link: [https://amarsee.shinyapps.io/nba-stats-shiny-dashboard/](https://amarsee.shinyapps.io/nba-stats-shiny-dashboard/)

## Goal

I sought to build an interactive web application to explore NBA stats. I've always been a big basketball fan and I've seen how data has transformed the game in the past decade or so. I created this shiny app as a way for somebody to explore some team level stats based on certain parameters. The three factors in this application are as follows:  
  * Days of rest  
    * For this purpose, days of rest means total time between games (e.g. 1 day of rest means games on back-to-back days because there is 1 total day between)  
  * Time Zone  
  * Home/Away  

## Data 

I used the [ballr package](https://cran.r-project.org/web/packages/ballr/ballr.pdf) to compile whole team schedules and results for the 2014 to present seasons.  

This package scrapes box scores from the [basketball-reference](https://www.basketball-reference.com/) website.

## Files 

 * nba_rest_effects_DataSetup  
   * Explores how the functions of ballr operate
   * combineYears is a function that combines the schedule from every team into one dataframe
   * Combines seasons from 2014 to present and writes to a csv file
     * Also combined 1985 to present, but was not used in Shiny App
 * nba_rest_effect_Exploration
   * Explores data set and writes out final data to rds file for the Shiny App
 * nba-stats-shiny-dashboard
   * Contains global, ui, and server files for the Shiny App
 * Data
   * Contains data files produced by setup file  
 * Proposal
   * PDF of project proposal

## Shiny App 

The Shiny App is split into 2 pages: League Wide Point Difference and Team Comparison

## League Margin of Victory
This page shows a graph with the average margin of victory for each team for a given set of parameters.

<img src="https://raw.githubusercontent.com/amarsee/nba-effects-of-rest-on-team-stats/screenshots/league.png" width="800" height="500" title="League Page">

 * Season
   * Select a season for stats. For this site the season will refer to the year in which the season finishes (e.g. 2018 is the 2017-18 season)
 * Team to Highlight
 
 <img src="https://github.com/amarsee/nba-effects-of-rest-on-team-stats/blob/screenshots/team_selection.png?raw=true" width="300" height="400" title="Team Selection">    
 
 * A team can be selected to focus on. This draws a box around the circle so that you can easily find the team as the bubble shifts when the parameters are changed.
   * Teams are shown by their abbreviations
   
 <img src="https://github.com/amarsee/nba-effects-of-rest-on-team-stats/blob/screenshots/radio_buttons.png?raw=true" width="300" height="250" title="Radio Parameters"> 
 
 * Time Slot
   * The time slot is the time at which the game is played. It is the typical weeknight time slot. Teams tend to play at either 7 or 7:30 local time, so a Pacific time slot game is one played at either 7 or 7:30 Pacific Time. Any game not played at a standard time falls into other. These are games typically on either weekends or holidays.
 * Days Rest
   * The days rest is the time from one game to the next. So, if a team plays one evening and plays again the next evening, that counts as one day of rest.
 * Home/Away
   * Choose stats for when a team plays on their home court or away. Either represents all games.  
   
  <img src="https://github.com/amarsee/nba-effects-of-rest-on-team-stats/blob/screenshots/league_table.png?raw=true" width="850" height="450" title="League Table Data"> 
   
 * There is a table below the plot with games that fit the paramters. Filters are at the top to search for certain team or stat.
  
## Team Comparison

Select two teams for comparison. The parameters are structured the same as the League Margin of Victory page.

<img src="https://github.com/amarsee/nba-effects-of-rest-on-team-stats/blob/screenshots/team_comp.png?raw=true" width="800" height="500" title="Team Comparison Page"> 

 * The side-by-side boxes show the average points scored, points against, and margin of victory. This can be used to see what might happen when those teams meet under the specified circumstances.  
 * Below the comparison is a table of games between those teams.
 
 <img src="https://github.com/amarsee/nba-effects-of-rest-on-team-stats/blob/screenshots/team_comp_table.png?raw=true" width="800" height="200" title="Table with Compared Teams"> 
 
 * One thing to note is for this site only games with 1, 2, or 3 days of rest are included. Notable games excluded are the first game of the season and the first game after the All Star Break. There is a small sample size of games with days of rest outside of 1 through 3, so they were excluded and will not show up in the data table of the Team Comparison page.

 
