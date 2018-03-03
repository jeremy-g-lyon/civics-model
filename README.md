# Civics Model
A NetLogo model that begins with the thesis that the structure of institutions and practices in civic society are more important to understanding and improving it than the disposition of the individuals who make it up. The ultimate goal of the model is to help understand which structures have the greatest effect on the quality of government and, eventually, the quality of life. That's a transparently hubristic goal: an interim goal is to help identify what questions to ask to understand the phenomena.

# Current Version
## Summary
The current version is still very simple. It generates citizens, politicians, parties, news sources and issues. It maps citizens, politicians, parties and news sources onto a grid where the x and y coordinates represent ideological positions (for example, social and economic). Every 4 ticks citizens vote for the politician nearest them. There are two parties made up of politicians in the top right quadrant (with postive x and y coordinates), and those in the bottom left quadrant (with negative x and y coordinates). The ideological positions of the parties are taken from the mean of its constituent politicians. The party with the most politicians is the majority party and makes up the government.

Every tick new issues are generated. The x and y coordinates of the issues represent the ideal mix of ideologies to solve those issues. The government addresses the issue by finding its vector and distance to the origin, then applying that vector and distance to the issue. (For example, if an issue is in the top right quadrant, but the government is in the bottom left quadrant, the issue worsens.) News sources report with some degree of accuracy modified by their ideologies how the government effected the issues, and their subscribed citizens modify their ideologies by a factor of the average of the reported effect they're aware of.

## To Do
* Bug fixes
  * Get the citizen satisfaction working properly as a percentage
  * Issues are stacking up too quickly, adjust to get to a better steady state
* Features
  * Reduce likelihood that citizens will vote for independents, either by forcing toward nearest left or right party (within tolerance range) or by implementing some kind of learning algorithm that penalizes politicians who don't end up in the left or right party
  * Report on elections
  * Implement a better way of dealing with issues by having parties adjust the vector they apply to the issue from within their party, and other parties within range of partisanship
* Refactor
  * Think about whether shifting citizens' ideology is the right model, or if there's a better way to represent choices citizens make in response to government action
  * Re-examine the factors that modify responses based on ideological alignment
  
# Next Version
Once the bugs and features described above have been addressed, I'll call this version done and start on a new version with the following vaguely defined goals in mind.
* Better abstractions to allow user control of things like election practices, party formation, etc.
* Generalize the model beyond American-style politics. This would include a more general party forming algorithm that clusters politicians and the ability to switch between election practices.
* Map citizens and politicians to some model of physical space, so that we can model the effects of local influence and geographically limited elections.
* Integrate economics so that not all citizens are the same.

# Contributing
This is currently a one person hobby project. I'm not a political scientist, software engineer or agent-based modeling expert, though I have aspirations on all three. If you're interested in contributing, download <a href="https://ccl.northwestern.edu/netlogo/">NetLogo</a>, branch off Master and have at it.
