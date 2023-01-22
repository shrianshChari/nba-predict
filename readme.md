# nba-predict
Here's how I grabbed NBA team statistics off the Internet and condensed them into CSV files for easy analysis.

#### Step 0: My goal
After reading articles about using machine learning to predict the winner of the NBA Finals, I wondered if I could create a predictive model using the four factors of basketball:
- Shooting
- Free throws
- Turnovers
- Rebounds

These are the four main ways possesions end in basketball, and I wanted to know if these statistics in particular could predict an NBA champion.

#### Step 1: Getting my data
I looked around online, and the data I found either didn't fit what I wanted, or was too much for me to use. I just required the four factors stats of each team in the regular season, and I realized that the best place to find that was on [nba.com](https://www.nba.com/stats/teams/four-factors/?sort=W_PCT&dir=-1&Season=2021-22&SeasonType=Regular%20Season). Of course, they didn't provide clean CSV files for me to use, so I had to make them myself.

After doing some testing with BeautifulSoup, here's what I ultimately did:
- Since using BeautifulSoup on the NBA website's URL would just yield the website before rendering, and I wanted the rendered table, I saved all the webpages in my browser using <kbd>Ctrl</kbd> + <kbd>S</kbd>.
- Then, I used BeautifulSoup to process these saved, rendered webpages and extract the table data into a second HTML document that would only contain the tables.
- Next, I parsed the data within the tables into a pandas DataFrame.
- Finally, I cleaned the data up by removing commas that the NBA includes in their four-digit numbers and I had a perfect dataset, ready for any analysis that I wanted to do.

#### Step 2: Playing with my data
Now that I had my data, I could explore it a bit and see what it looked like. I picked the statistics for the latest season and charted them in order from least to greatest. Then, I wanted to visualize all four graphs at once, so even though none of them were normal curves, I took their z-score and plotted them all on the same graph. All of these plots can be found within the Python notebook within the repo.

#### Step 3: Getting playoffs data
I replicated what I did in step 1, but instead of grabbing regular season data, I would grab playoff data. I didn't feel especially inspired to do any sort of data analysis for this playoff data, especially since most of the teams didn't play more than 5 or 6 games.

I also realize in hindsight that it would've been a lot easier to rip the data from Basketball Reference, or even just download it from Kaggle instead of ripping it from the NBA's website, but I'm also fine with what I did because it gave me good practice with using BeautifulSoup.
