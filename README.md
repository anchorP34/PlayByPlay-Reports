# PlayByPlay-Reports
This repository is to pull and analyze play by play results from D2 baseball and softball games.


# PlayByPlay-Reports/FullGamePull
This script is for the web scraping python algorithm for most D2 baseball and softball games. The example that is used in the script is for http://www.kstatesports.com/boxscore.aspx?id=2417&path=baseball, so games that have this format should work correctly.

The first thing that the alorithm does is pull back the string HTML of the link. It looks for the "Play by Play" section of the HTML and pulls every play by play result into a dataframe. With all of the records loaded, iot then looks for different pieces of the HTML body to get information like the date, home and away team, and any other "title" information that can be used for details about the game that will be the same for every record. 

Columns like Inning, Count, Result, BIP (Ball in Play) Location, Pitch Sequence, and other variables are just derived off of the Play By Play string. 

By putting the link in the test_1 method at the bottom of the script, you will see the final dataframe of the game.

This is the easiest way to get all of the information necessary to do any data analysis without needing to know the actual players in the game. 

# PlayByPlay-Reports/Data Science Results

CSV that takes the play by play results of 6 different conferences from the last 4 seasons.

# PlayByPlay-Reports/What Counts Are Most Important In An At Bat
This is the analysis for determing what counts are most important in determinig the outcome of someone successfully getting on base. If a team can figure out what are the main factors that lead to a successful at bat, they are more likely to teach their hitters to adapt those ideas and to also teach their pitchers what factors will help get opposising hitters out.

The imports that are necessary are pandas to handle the dataframes, matplotlib and seaborn for visualizations, and scikitlearn for machine learning.

The data that was pulled came from thousands of results pulled FullGamePull script and loaded to the Data Science Results CSV. Once it was loaded into a pandas dataframe, I removed records that did not have a pitch sequence available or were not 0-0 count results since they only had 1 pitch in the at bat. I did not try to infer what the pitch sequence was since there are multiple permutations of how an at bat can go, and these records hold the most information that can be pulled from an at bat.

From the information in the Pitch Sequence column and the result column, I was able to create functions that determine if an at bat had one of the 12 different counts at some point in the at bat. I could also determine the finishing ball and strike count of the at bat, and the number of pitches seen in the at bat. 

From there, you can see on base percentages of different counts experienced in the at bat, the different counts that have the biggest swing of impact from a ball or strike on the next pitch, and machine learning algorithms to predict if an at bat will result in a success or not. Evaluations of the results can be viewed in the blog post https://medium.com/@paytonsoicher/the-mathematicians-guide-to-arguing-with-an-umpire-bbf1dd30812b.


