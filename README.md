# AI-Crossy-Road
Code to play AI Crossy Road on PyGame


Crossy Road is a game where a Chicken (red circle) attempts to pick up reward Packages (yellow boxes) whilst avoiding the moving Cars (blue boxes)

This AI uses Deep Q-Networks for Reinforcement Learning. Initially, the chicken runs randomly, analysing its current state and seeing the reward from a random move from that state. The reward is positive if the Chicken collects a Package from this action, and negative if it hits a Car, adding to the current reward value for that action, with a slight decay. The reward is then recorded in a Q-table in excel, so the chicken is learning the result of the action in that space via exploration. 
Over time, as the Chicken sees more states and actions, the Q-table becomes sufficient to run from, so a period of elploitation can occur. Here, the Chicken analyses its current state, looks in the Q-table for the best rewarding action for that state and moves in this direction. Therefore, if enough training has occured, the Chicken should be able to traverse the game play picking up Packages and avoiding Cars.

------------------------
Running


To start to run the program, run 'main("new",1)' to initialize the qTable from scratch ("New" argument) and start with an epsilon of 1 (Exploration)
Once this has been run once, the second time you should run 'main("old",1)', in order to build on the qTable generated before. This still is in a period of Exploration.

Once a sufficient period of Exploration has occured (I would recommend up to 6 hours), you can then move to a period of Exploitation by running 'main("old",0)', so an epsilon value of 0. This will then cause the Chicken to choose the best move and hopefully be successfull!

-----------------------------
Dependencies

-The Q-table in stored in an excel file, so this location must be changed to a suitable file directory 
-Runs on Pygame, so this is a dependency. Intall via Pip for Python
-Requires Numpy for arrays
