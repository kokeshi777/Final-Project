# Final-Project
The spread is the amount added or subtracted to a teams final score.
If the line is negative the line is subtracted from the team you bet on
If it is positive the line is added to the score of the team you bet on
Examples: if the team you are betting on a team at a line of -3.5 they need to win by at least 4 points to win the bet.  On the other side if you are betting a team that is plus 7  if the lose by 6 or less points you win the bet and  with a differential of 7 you push meaning you get your money back.
The spread is designed to be to have equal action on both sides.
The sportsbook makes their money on having equal bets from the public on both sides of the line.
The amount of you you get back on average for each dollar you bet on either side of the line is approximately 91 cents so if there is the same money on each side of the bet the sportsbook cannot lose.
What this mean practically is you have to wager on average on $1.10 to get back $1 in a win. Because of this discrepancy risk vs reward you have to be accurate at predicting the winner 52.4% of the time to break even

The goal of the model is to predict the correct side of a side of team to bet on vs the spread for every NFL game is a particular week of NFL games

While achieving a 53% success ratio seems relatively easy it is deceptively hard when there are millions of dollars at stake in setting the spread at a level to not allow the general public to reach that threshold. 

The model will only be run for games in the second half of every season for the last 15 years.
15 years because that is the time period I could get pregame spread results for and also because the game has changed a lot over time and data from farther back would be less reliable.
Only the second have of the season because the features use for prediction are based on accrued stats throughoutt the season and early season statistics would have less of a correlation with the result of the game.
Unfortunately this means this model cannot be used to predict games in the early season

The prediction model was created out of combing  a total of 451 different spreadsheets.
One spreadsheet with the scores  and lines for all games back to 2006
3 spreadsheets for every week of games that the model is run for in that time period.
One spreadsheet for Total DVOA rating, offensive DVOA rating, Defensive DVOA rating, and special teams DVOA rating
One spreadsheet for in depth offense DVOA statistics
One spreadsheet for in depth defensive Dvoa ratings
Combing these spreadsheets into one dataframe may have been the hardest part of this entire task, but I ended up finding python code to combine them, making it far easier in the future to add more results.

I ended up using the Linear Regression, Random Forrest, and Support Vector Regression models for my predictions.
To implement the model I ran to separate regression models on to predict the score of team and one to predict the opponents score.
I modified the predicted scores manually by a point if a team was strong in passing or rushing offense and the opponent was weak in the corresponding defensive metric.
Then I took the differential of those those two models and compared it to the line that was set for the game and based on that information predicted whether the team covered or not.
I ran on accuracy test the ratio between my predictions on whether the spread was covered and whether the team actually covered the spread.
I created a subset of the predictions where the model predicted a certain threshold of difference between the two teams adjusted for the lines.

