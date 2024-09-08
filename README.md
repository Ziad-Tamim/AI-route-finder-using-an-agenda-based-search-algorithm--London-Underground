# AI-route-finder-using-an-agenda-based-search-algorithm--London-Underground
Building an AI route finder for the London Tube system using an agenda-based search mechanism.

![London-tube-map](https://github.com/user-attachments/assets/bdfd38d7-e129-4ad7-88b6-23d9ce079c98)

## Summary of the Project
- **Objective**: To build an AI route finder for the London Tube system using an agenda-based search mechanism.
- **Purpose**: Understand and implement agenda-based search techniques.
- **Project involves** implementing various search algorithms and comparing their performance.

## Deliverables
- **AI Route Finder**: Implement DFS, BFS, UCS, and a heuristic search mechanism for route finding.
- **Report**:
    - Description of state representation.
    - Comparison of DFS, BFS, and UCS performance.
    - Extension of UCS to include line-changing time.
    - Implementation and explanation of heuristic Best-First Search (BFS).
- **Code Implementation**: Python code using libraries like Pandas for data handling and possibly NetworkX for visualization (optional).

## Dataset Description (tubedata.csv)
- Contains information about the London Tube map.
E.g., ...

Harrow & Wealdstone, Kenton, Bakerloo, 3, 5, 0 

Kenton, South Kenton, Bakerloo, 2, 4, 0

· · · 

Bank/Monument, Waterloo, Waterloo & City, 4, 1, 0

Each row in the CSV file represents a Tube “step” and is in the following format: 
[StartingStation], [EndingStation], [TubeLine], [AverageTimeTaken], [MainZone], [SecondaryZone], where:
- **StartingStation**: Starting tube station.
- **EndingStation**: Directly connected tube station.
- **TubeLine**: Line connecting the stations.
- **AverageTimeTaken**: Time (in minutes) to travel between the two stations.
- **MainZone**: Zone of the starting station.
- **SecondaryZone**: Secondary zone of the starting station (0 if none).
Data loaded using Pandas in Python.

## Implementation
### Agenda-based Search Setup
**Data Preprocessing**:
- Read data using Pandas (`read_csv` with `header=None`).
- Use `defaultdict` to store station connections and zone information.
- Process data row-by-row to build:
  - **Station dictionary**: Lists of directly connected stations and travel times.
  - **Zone dictionary**: Zones for each station, considering main and secondary zones.

### Implementing Search Algorithms
- **DFS (Depth-First Search)**:
    - Explore all possible routes depth-wise before backtracking.
- **BFS (Breadth-First Search)**:
    - Explore all neighboring stations level-wise.
- **UCS (Uniform Cost Search)**:
    - Explore paths based on the lowest cumulative cost (average time taken).
 
### Comparison of Search Methods
- Test and compare DFS, BFS, and UCS based on:
    - **Path**: List of stations on the route.
    - **Cost**: Time taken.
    - **Nodes Expanded**: Number of stations visited during the search.
- Routes for comparison:
    - Euston to Victoria (recommended for testing).
    - Canada Water to Stratford, New Cross Gate to Stepney Green, etc.
- Comparison metrics:
    - Is any method consistently better?
    - Compare node count and time for direct/inverse order of node processing.

### Extending UCS (Adding Line-Changing Time)
- Modify UCS to account for a **2-minute penalty** for switching lines.
- Compare new results for the extended cost function using one of the test routes.

### Heuristic Search (Best-First Search, Not A*)
- Use station zone data to guide search direction.
- Implement and explain the heuristic function.
- Compare results with UCS in terms of time efficiency using test routes.
