# PathNode-Visualizer
A high-performance, vanilla JavaScript pathfinding visualizer. Features real-time A*, Dijkstra, BFS, and DFS animations on a dynamic CSS Grid with zero external libraries

#PathNode: Advanced Pathfinding Engine
PathNode is a high-performance, vanilla JavaScript visualization engine designed to demonstrate complex search algorithms in a real-time, interactive environment. Built with a focus on asynchronous execution and computational efficiency, it provides a cinematic look at how machines solve the "Shortest Path" problem.

#The "Engineering" Challenges
This project was built to master three specific "Hard Parts" of frontend engineering:
1. The Asynchronous Visualization LoopThe Problem:Traditional loops freeze the browser UI when performing 1,000+ calculations per second.The Solution: Implemented a custom Async/Await wrapper around setTimeout, allowing the algorithm to "yield" control back to the browser's main thread. This ensures the UI remains responsive (60fps) while the search frontier expands.
2. High-Density DOM PerformanceThe Problem: Managing 1,200+ individual Node objects can lead to massive memory leaks and slow re-renders.The Solution: Used CSS Grid with a single 1px gap to define grid lines (reducing border paint calls by 75%) and maintained a state-mapped JavaScript object array to avoid expensive constant DOM lookups.
3. Algorithm Accuracy (A* & Dijkstra)The Problem: BFS finds the shortest path but is inefficient; A* is fast but requires a perfect heuristic.The Solution: Implemented Manhattan Distance ($|x_1 - x_2| + |y_1 - y_2|$) as the heuristic for A* and a Priority Queue-style sorting logic to ensure $O(\log n)$ efficiency during node selection.

#Key Features
Real-Time Obstacle Drawing: High-frequency mouse event listeners for smooth "drag-to-draw" wall placement.

Interactive Node Placement: Dynamic repositioning of Start/End nodes with automatic path recalculation.

Recursive Maze Generation: (Optional Add-on) Algorithmically generates complex mazes using recursive backtracking.

Neon UI/UX: Advanced CSS @keyframes and filter: blur() effects for a modern "Bloom" aesthetic.
