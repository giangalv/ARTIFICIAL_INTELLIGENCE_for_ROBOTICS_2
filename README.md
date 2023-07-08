# ARTIFICIAL_INTELLIGENCE_for_ROBOTICS_2 #

# coffee shop with robots as waiters and baristas - 1 ASSIGNMENT 
To run a coffee shop, the barista robot needs to prepare the drinks ordered by the costumers. Cold drinks are faster to prepare than warm drinks. The waiter robot is then in charge of serving customers, and to clean tables where customers have already left the shop. The waiter robot can decide to grasp a drink with its gripper, or to use a tray to carry more drinks at once. When using the tray, the robot is moving slower to improve balance.

### Details 
In the coffee shop, there are two robots: one barista and one waiter. The barista is in charge of preparing drinks. Orders are placed by customers by using a dedicated interface at the entrance of the shop. You don’t need to model that, and you can assume that, at the start of your planning problem, all the orders are known. The customer that put the order is of course known, as it is the place where she sits.  It takes the barista robot 3 time units to prepare a cold drink, and 5 time units to prepare a warm drink.   Once ready, the drinks are put on the bar, where the waiter can pick them up. The waiter robot can grasp a single drink using one of its grippers, and bring it to the table where the corresponding customer is seated. The waiter is not able to grasp one drink per each gripper, but can only bring a drink at a time if it is not using a tray. If it decides to use a tray, then the waiter can carry up to 3 drinks at the same time, but its moving speed is reduced – for ensuring everything is balanced. When using a tray, the waiter cannot carry any additional drink, beside the 3 on the tray. The tray can be taken from the bar, and must be returned there after use. The waiter is not allowed to leave the tray on a table. The waiter moves at 2 meters per time unit; 1 meter per time unit if it is using the tray.  Finally, the robot has to clean tables: it takes 2 time units per square meter to clean a table. The robot cannot clean a table while carrying the tray. 

![Alt text](https://github.com/giangalv/ARTIFICIAL_INTELLIGENCE_for_ROBOTICS_2/tree/main/picture/robotDrink.jpg)

### Extensions 
  1. Warm drinks cool down, so you need to serve the customer before the drink gets too cold. A warm drink takes 4 time units to become cold. A customer will not accept a warm drink delivered more than 4 time units after it was put on the bar by the barista.
  2. There are 2 waiters. The coffee shop is doing well, so the owner decided to buy a second waiter. This is of course making things a bit more complicated: only one waiter can be at the bar at a given time; further, the owner does not want that a table is served by both the waiters: only one waiter can deal with the orders of a given table.
  3. Finish your drink. After receiving the drink, a customer will finish it in 4 time units, and will leave after that. When all the customers of a table have left, the waiter robot can clean it. The waiter robot is required to clean all the tables to complete the problem.
  4. We also serve food. The coffee shop is also serving delicious biscuits. They need no preparation, and can be picked up by the waiter at the bar counter. All the customers with cold drinks will also receive a biscuit, but only after having received their drink. The waiter can not bring at the same time the drink and the biscuit, but must deliver the drink, and then go back to the counter to take a biscuit for the customer.  For the sake of moving biscuits around, the same limitations as for drinks apply (see above).

![Alt text](https://github.com/giangalv/ARTIFICIAL_INTELLIGENCE_for_ROBOTICS_2/tree/main/picture/barConfiguration.png)

The coffee shop layout is shown in the figure above. It has the bar counter on the very top, and 4 tables for costumers. Each table is 1-meter apart from any other (let’s assume Euclidean geometry does not apply here, so also tables 1 and 4 are 1 meter from each other). The bar is 2 meters away from tables 1 and 2. Table 3 is the only table of 2 square metres, all the others are of 1 square metre.  

### Problems to be encoded
• Problem 1: There are 2 customers at table 2: they ordered 2 cold drinks. Tables 3 and 4 need to be cleaned.  

• Problem 2: There are 4 customers at table 3: they ordered 2 cold drinks and 2 warm drinks. Table 1 needs to be cleaned.  

• Problem 3: There are 2 customers at table 4: they ordered 2 warm drinks. There are also 2 customers at table 1: they ordered 2 warm drinks. Table 3 needs to be cleaned.  

• Problem 4: There are 2 customers at table 4 and 2 customers at table 1: they all ordered cold drinks. There are also 4 customers at table 3: they all ordered warm drinks. Table 4 needs to be cleaned. 

# Task and Motion Planning - 2 ASSIGNMENT
Consider the 2D environment shown at end. There are four student groups, each assigned to regions 1-4, working on their assignments. Robot R is responsible for collecting the assignment reports and delivering them to the submission desk (red in figure). The dimension of the environment is 6m × 6m. R is initially at (0, 0) and the submission desk is at (3, 0). For the sake of simplicity, assume each region is of size 1m × 1m and associate a single way-point (x, y) to each region. Randomly sample 24 way-points (x, y) from the environment, outside the regions. The sampled way-points are connected to form edges. You can choose a k such that each way-point is connected to a maximum of k other way-points. This results in a roadmap with way-points as nodes. Finally, the 4 way-points associated with each region, the initial location of R, and the submission desk are to be connected to the nearest nodes in the roadmap.

![Alt text](https://github.com/giangalv/ARTIFICIAL_INTELLIGENCE_for_ROBOTICS_2/tree/main/picture/enviroment_2D.png)
