## Read the data from [basketball reference](https://www.basketball-reference.com/leagues/NBA_2016_totals.html)
This data is aggregated for the entire season. The level of grain is player and team; if a player was traded to a different team midseason there will be a value in the team column of `TOT` which is an aggregate for that player's whole year. Those values will be removed to not double count stats


## Question 1 

**Which player played the third most minutes (MP) across the entire season, and how many minutes did he play?**

#### Answer:
  *James Harden, with 3,125 minutes played. I grouped the data by player and summed the minutes played, then sorted in descending order to get the player who played the most*


## Question 2

**Which team had the highest number of assists (AST) across all of its players?**

#### Answer 
*GSW -> Golden State had the most assists with 2,373. I reached this by grouping the data by team and summing the total number of assists then sorted the results in descending order.*


## Question 3

**Which team (TM) had the highest number of players that scored over 750 points (PTS) on the season?**

#### Answer:
  *Dallas, Denver, and Minnesota each had 6 players that scored over 750 points that season. I reached this by filtering to players who scored more than 750 points, then grouping by the team to then count the number of players with more than 750*


## Question 4 

**Which player scored the highest percentage of his team's total points (PTS)?**

#### Answer:
  *James Harden had that highest percentage of his team's total points. I reached this by using a window function to get the total per team, then got the ratio of each player to team's total points, then sorted in descending order*


## Question 5

**Among players with at least 20 3-point field goal attempts (3PA), which player's 3-point field goal percentage (3P%) was the furthest from the average 3-point field goal percentage of their position (POS)? What was the difference?**

#### Answer:
  The player with largest discrepancy between their three point percentage versus their position average was Dwayne Wade, who was 0.19 below the average of 0.35. I arrived at this by:

  - Filtering the data set to only include players who shot more than 20 three point shots
  - Grouping by position and applying a window function to get the total average by position
  - Finding the difference for each player of their three point percentage versus their position average
  - Sorting the results of the difference in descending order