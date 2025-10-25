Overview

This project explores adaptive AI pathfinding in a dynamically changing environment—a spaceship on fire. The goal is to evaluate how different decision-making strategies handle uncertainty, risk, and survival when fire spreads unpredictably.

A 40x40 grid represents the ship’s layout, composed of walls, open paths, and key elements:

Bot (Start) – the agent navigating the grid

Fire (Hazard) – spreads each step based on flammability parameter (q)

Suppression Button (Goal) – ends the fire when reached

Each simulation generates 1,000 unique ship layouts, testing how bots perform across varying q values (fire spread probabilities).

The Bots
Bot	Strategy	Description
Bot 1	Static BFS	Precomputes the shortest path to the button once and follows it blindly, failing when fire spreads into its route.
Bot 2	Dynamic BFS	Recalculates the shortest path at every step to avoid fire, reacting to new obstacles but lacking foresight.
Bot 3	Fire-Buffer BFS	Avoids both burning and adjacent cells, prioritizing safety over speed but still without fire prediction.
Bot 4	Dijkstra’s + Fire Prediction	Uses Dijkstra’s algorithm weighted with fire risk prediction to anticipate danger, adapt dynamically, and select the safest, most efficient route.
Key Findings

Adaptability is essential. Static bots fail quickly as fire spreads.

Dynamic replanning improves survival, but prediction ensures long-term success.

Bot 4 consistently achieves the highest success rates, balancing safety and efficiency even in fast-spreading fires.

At high q values (rapid fire), only half of all scenarios remain winnable, emphasizing the need for predictive, risk-aware AI.

Technical Highlights

Ship Generation: Procedural maze creation ensuring solvable layouts.

Fire Simulation: Probabilistic spread model influenced by q and burning neighbors.

Bot Algorithms: BFS, dynamic replanning, Dijkstra with custom risk factor weighting.

Data Analysis: Performance comparison across 1,000 runs per bot and varying q.

Optimizations: Priority queues, early exit conditions, and precomputed fire danger maps for speed and scalability.

Applications

AI and machine learning research in dynamic environments

Robotics navigation in hazardous or unpredictable settings

Game AI and survival simulations

Emergency response algorithms for fire and disaster management

Final Conclusion

Dynamic pathfinding powered by risk prediction offers the most robust strategy in uncertain environments.
Bot 4, combining Dijkstra’s algorithm with fire risk prediction, proved to be the most reliable and adaptive solution—showing how intelligent agents can balance speed, safety, and situational awareness in real-time decision-making.
