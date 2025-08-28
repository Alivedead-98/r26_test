# R26_test
RA2511033010143
# Solution
## Understanding
The main task given here was the help a rover move from a start point to a goal point using GPS data that comes in a UBX format. I had to decode to find the latitude and longitude for the start and goal positions. Then I had to create a path ona  grid map and figure out how the rover should move with respect to time to follow the path. The code tells us to decode GPS at ``ublox_reader.cpp ``, plan a path at ``planning.cpp`` and making movement commands in ``odometry.cpp``. I also had to compile and test it with ``make build`` and ``make check``.

## Thought Process
I split the task into simple steps to make it easier for me to think

1. **Read GPS Data** → take UBX GPS data and turn it into latitude, longitude, and height.  
2. **Make a Grid Map** → change GPS points into a local grid and mark where obstacles are.  
3. **Plan the Path** → run the A* algorithm on the grid to find a route from the start to the goal.  
4. **Rover Movement** → turn the path into commands for the rover, figuring out the time and turning angle using wheel size and RPM.
   
For Task 1, I needed to fix the GPS decoding code to read UBX data correctly. I planned to check the u-blox datasheet to understand the NAV-POSLLH message format. For Task 2, I thought about using a pathfinding algorithm like A* to find a route on the grid. For Task 3, I wanted to calculate movement commands based on the path. Task 4 was about compiling and testing. I knew I’d need to use AI tools, internet search and the datasheet for help, but I took a while to understand the coding details

## Implementation
# Task 1
Tried to fix ``ublox_reader.cpp`` to decode ``UBX NAV-POSLLH`` messages. I pasted the code in ChatGPT to check for the mistakes that might occur in code and found some. Fixed those errors and went to run the code.
I Looked at the code and saw it reads a file with hex strings, converts to bytesand extracts latitude and longitude. Noticed ``NAV_POSLLH`` had wrong offsets and ``decodeUBX`` had wrong bytes .
I didn’t fully understand C++ byte handling or UBX format. Tried reading the datasheet (provided link) but got confused by byte offsets and checksums. I couldn’t fix the code properly due to limited coding knowledge.
# Task 2
I planned to implement A* algorithm in ``planning.cpp`` for finding a path on a grid. The starting coordinates were taken as origin (0,0) on the grid map. I googled “A* pathfinding C++” for ideas. Understood that Understood A* uses a grid (0 = free, 1 = obstacle) and a priority queue.
# Task 3
I had planned to write commands on ``odometry.cpp`` to calculate time and angles of the rover's path. I understood that it involved formulas for distance and angles. Searched for potential mathematical formulas that could be used here.
# Task 4
Planned on trying to compile ``make build`` and test using ``make test`` but couldn't do so due to unfinished code.


## Final thoughts
This test was a big challenge for me because i’m sti;; new to coding, especially in C++. I felt overwhelmed by the technical details like UBX message parsing and pathfinding algorithms, but I gave it my best shot.
Even tho i struggled understanding and finishing the task, I definitly learnt many new things about how GPS data works and what path planning involves. I am looking forward to learn new things and improve myself. 
I appreciate the opportunity i claimed and i’ll keep working to improve my skills for future challenges! Thank you!


